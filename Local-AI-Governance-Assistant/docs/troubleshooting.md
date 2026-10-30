# Troubleshooting and Development Log

This document records observed work on the local prototype. It intentionally distinguishes confirmed test results from hypotheses and work still required.

## Environment observed during development

- Operating system: Pop!_OS.
- Local model runner: Ollama.
- Model: `llama3.2:3b` (reported local model size approximately 2.0 GB).
- Project directory used on the developer's machine: `~/Documents/Ollama`.
- Python entry point: `local_agent.py`.
- Memory store: `memory.json`.
- Ollama chat endpoint configured in the prototype: `http://localhost:11434/api/chat`.

The developer's local username, home directory, and machine-specific configuration are deliberately not included in the public project.

## Issues encountered and work completed

### 1. Project-file functions were accidentally removed during editing

**Symptom:** The read-only project-file functions were missing after edits.

**Action taken:** The `list_project_files()` and `read_project_file()` functions were restored. The intended implementation restricts access to the configured project directory, selected extensions (`.py`, `.json`, `.md`, `.txt`), and files no larger than 200,000 bytes.

**Current status:** Functions were restored, but a complete regression test has not yet been recorded. Path traversal, symlink handling, and access outside the approved directory still require explicit testing.

### 2. Indentation error in the memory tool dispatch branch

**Symptom:** The `save_memory(data)` conditional was indented incorrectly inside the `remember_information` dispatch branch.

**Action taken:** The branch was corrected so that the success response is returned only when `save_memory(data)` succeeds, and an error response is returned otherwise.

**Validation:** `python3 -m py_compile local_agent.py` completed without output after the correction, indicating that Python compilation succeeded at that point.

### 3. Persistent memory write test

**Test input:** The operator explicitly asked the assistant to remember that the project uses `llama3.2:3b` and stores persistent memories in `memory.json`.

**Observed output:** The tool log showed `[TOOL REQUESTED] remember_information`, followed by `[MEMORY] Memory saved.`.

**Direct evidence:** The local JSON file contained the saved test sentence in its `memories` array.

**Result:** The memory write path worked in this test.

### 4. Direct Python memory recall test

**Command used:**

```bash
python3 -c "import local_agent; print(local_agent.recall_memory())"
```

**Observed result:** The function returned the saved memory as a JSON-formatted array containing the exact test sentence.

**Result:** The Python-level memory load/recall function worked when called directly.

### 5. Model-driven recall failed despite successful direct recall

**Test sequence:**

1. Save a test memory through the running assistant.
2. Exit the program.
3. Start the assistant again.
4. Ask: `What do you remember about this project?`
5. The model requested `recall_memory`, but replied that there were no saved project memories.
6. Inspect `memory.json`; the saved sentence was still present.
7. Run the direct Python recall command; it returned the saved sentence.
8. Ask the model to call `recall_memory` and report exactly what it returned; it again claimed that no information was returned.

**What this establishes:** The JSON memory was present and the Python recall function returned it outside the model interaction. The end-to-end tool-call exchange is therefore the current failure point to investigate.

**What this does not establish:** It does not yet prove whether the problem is the Ollama tool-message schema, message ordering, tool-result serialization, the model's interpretation of the result, or another issue in the agent loop.

**Current status:** Unresolved. Do not describe model-driven persistent recall as working.

## Next diagnostic steps

1. Log the exact Python tool output immediately after `execute_tool(name, arguments)`, before appending it to the message list. Avoid logging private memory content in a public or shared environment.
2. Inspect the complete assistant tool-call message and the tool-result message sent back to Ollama.
3. Confirm the required tool response message structure for the installed Ollama API/version.
4. Verify that the tool result is appended after the assistant tool-call message and before the next API request.
5. Test with a harmless fixed string returned by a temporary diagnostic tool, then test the memory result.
6. Add a test that asserts the tool dispatcher returns the saved memory and a separate integration test that verifies the model receives it.
7. Re-test startup memory loading, while ensuring that the same memory is not injected repeatedly or incorrectly treated as instructions.
8. Once fixed, rerun the test after a full program restart and document the exact output.

## Other work still required

- Confirm that file listing and reading work after restoration.
- Review the system prompt so it accurately explains the narrow memory-write permission while keeping project-file access read-only.
- Require explicit user intent before storing notes; reject secrets and sensitive personal information.
- Add memory deletion/editing controls and safer file permissions.
- Add automated tests for malformed JSON, duplicate notes, oversized notes, invalid tool arguments, and failed writes.
- Test maximum tool-call rounds and malformed Ollama responses.
- Review the complete source and configuration before publishing them.

## Current development assessment

The prototype has a working local model connection and demonstrated Python-level memory persistence. Syntax compilation passed after recent fixes. The model-driven memory recall integration remains unresolved, and the restored file tools still need regression testing. This is an active prototype, not a completed or production-ready agent.
