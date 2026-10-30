# Local AI Governance Assistant

<sub><strong>Status: Work in progress · Local prototype · Not production-ready</strong></sub>

A locally hosted, command-line AI governance assistant built around Ollama and a small language model. The project explores how a local model can support governance and IT/security work while using narrowly scoped tools to inspect project files and maintain explicitly requested project notes.

This is a separate project from the portfolio's **AI Governance Engineering Lab**, which uses Open Policy Agent (OPA) and Rego to express and test governance rules. This assistant is an application prototype that uses a local LLM.

## Current status

The project is under active development. The Python application has been edited and tested locally, but the end-to-end tool workflow is not yet reliable.

| Component | Current evidence | Status |
|---|---|---|
| Ollama local model | `llama3.2:3b` was installed and used locally | Tested |
| Python syntax | `python3 -m py_compile local_agent.py` completed without errors after recent edits | Passed at that point in development |
| Persistent memory write | A test memory was saved into local `memory.json` | Tested |
| Direct memory read | `python3 -c "import local_agent; print(local_agent.recall_memory())"` returned the saved entry | Tested |
| Model-driven memory recall | The model called `recall_memory` but responded as if no memory was returned | **Unresolved** |
| Project-file tools | Read-only file listing and reading functions were restored after accidental removal during editing | Restored; regression test still needed |
| Security review | Repository exclusions and safe-publication guidance are documented here | Documentation in progress |

These statuses describe observed development tests, not a security certification or production validation.

## Intended capabilities

- Run a local language model through Ollama.
- Provide narrowly scoped, read-only project-file listing and reading.
- Keep explicitly requested project notes in a local JSON memory file.
- Recall saved project notes as context in a later session.
- Support learning and analysis of GRC, IT controls, security, and AI governance topics.

The application is not intended to make compliance decisions, approve access, change infrastructure, or replace human review.

## Design and safety boundaries

- **Local inference:** The prototype sends prompts to the local Ollama service at `http://localhost:11434/api/chat`. Local inference does not by itself guarantee that all data stays private; users must also review their machine, model, logs, backups, and any future integrations.
- **Read-only project access:** File tools are intended to list and read only approved project files with approved extensions and a maximum file size. These restrictions must be tested against path traversal, symlinks, unexpected file types, and oversized files before relying on them.
- **Separate memory write path:** The memory tool is intended to write only to the assistant's own local `memory.json`. This is a limited write capability; it does not mean the rest of the project is writable by the assistant.
- **No secrets in prompts or memory:** Do not provide passwords, API keys, tokens, personal identifiers, private records, customer data, PHI, or confidential employer information.
- **Human review:** Treat model output as untrusted suggestions. Verify technical claims, control mappings, and recommendations independently.

See [Security and privacy notes](SECURITY.md), [Architecture](docs/architecture.md), and [Troubleshooting and development log](docs/troubleshooting.md).

## Project structure

```text
Local-AI-Governance-Assistant/
├── README.md
├── SECURITY.md
├── .gitignore
├── memory.json.example
└── docs/
    ├── architecture.md
    └── troubleshooting.md
```

The Python source is intentionally not included in this documentation-only commit. It will be added after the actual local file is reviewed and the unresolved tool-response behavior is tested. Do not treat this documentation as proof that a runnable release is present.

## Local setup (development notes)

1. Install Ollama using its official installation instructions.
2. Download the model used by this prototype: `ollama pull llama3.2:3b`.
3. Ensure the Ollama service is running and reachable at the configured local endpoint.
4. Place the reviewed Python source and configuration files in the project directory.
5. Create a local memory file from `memory.json.example` if the application requires it.
6. Run Python syntax checks and the manual test plan in the troubleshooting document before using the assistant.

Exact setup commands may change as the code and configuration are finalized.

## Roadmap

- [ ] Resolve model/tool response handling for `recall_memory`.
- [ ] Add automated unit tests for memory read/write and tool dispatch.
- [ ] Regression-test read-only file access and path restrictions.
- [ ] Review prompt instructions and tool permissions for least privilege.
- [ ] Add robust JSON/API error handling and bounded tool-call behavior.
- [ ] Add a sanitized, runnable source release after local review.
- [ ] Add documented setup instructions and reproducible test results.
- [ ] Consider memory deletion/editing controls and user confirmation behavior.
- [ ] Perform a security review before considering any broader use.

## Scope disclaimer

This is an educational prototype and an ongoing engineering exercise. It is not a certified governance product, security tool, audit platform, or production-ready agent. No claim of regulatory compliance, confidentiality, or resistance to prompt injection is made.
