# Architecture (current intended design)

## Components

1. **Command-line interface** — accepts a user prompt and displays model responses.
2. **Ollama API** — serves the locally installed `llama3.2:3b` model through `http://localhost:11434/api/chat`.
3. **Tool dispatcher** — receives model tool calls and routes approved function names to Python functions.
4. **Project-file tools** — intended to list and read a bounded set of files inside the approved project directory.
5. **Memory store** — local JSON file used for explicitly requested project notes.

## Data flow

```text
User prompt
    |
    v
Python command-line agent
    |
    v
Local Ollama chat API <----> Model
    |
    | tool call (if requested)
    v
Python tool dispatcher
    |                         |
    v                         v
Read-only project tools   Memory functions
    |                         |
    v                         v
Approved project files    local memory.json
    |                         |
    +---------- tool result --+
                 |
                 v
          Model response
```

The diagram represents the intended flow. The memory recall path is currently under investigation because the Python function returns saved data when called directly, while the model has not reliably used the tool result in the conversation cycle.

## Intended tool surface

- `list_project_files`: list permitted files in the approved project directory.
- `read_project_file`: read an approved file within the configured size limit.
- `remember_information`: store a bounded text note in the local memory file.
- `recall_memory`: return saved notes from the local memory file.

The memory write tool is a narrow exception to the read-only project-file boundary. It should not grant arbitrary filesystem write access.

## Trust boundaries and limitations

- The model is not a trusted policy enforcement point.
- Python-side validation must enforce tool names, argument types, path restrictions, and file limits.
- Local model hosting reduces reliance on a remote inference API but does not guarantee complete privacy.
- Tool results must be passed back to the model in the API format expected by the installed Ollama version.
- Tool-call loops must have a strict maximum number of iterations and handle malformed or repeated calls.
- No automated execution of shell commands is part of the intended design.
