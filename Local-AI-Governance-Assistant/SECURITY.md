# Security and Privacy Notes

## Project status

This is a local educational prototype under active development. It has not undergone an independent security assessment, penetration test, or formal privacy review. Do not use it with sensitive, regulated, employer, customer, or production data.

## Public-repository exclusions

Never commit:

- The real `memory.json` file or any copy/backup of it.
- Personal conversation histories, prompts, logs, or exported records.
- API keys, access tokens, passwords, SSH keys, certificates, or credentials.
- Employer documents, customer data, PHI, PII, confidential records, or proprietary code.
- Local configuration files containing machine-specific paths or private settings.
- Backup files such as `*.bak`.

The repository's `.gitignore` is a safety net, not a guarantee. Review `git status --ignored`, staged files, and the final commit contents before every push. If a secret is committed, deleting it in a later commit does not make it safe; revoke or rotate the exposed credential and follow GitHub's sensitive-data removal guidance.

## Runtime boundaries

The intended design uses:

- Local Ollama inference at a loopback address.
- Read-only project-file tools restricted to an approved project directory, selected extensions, and a maximum file size.
- A separate memory function that writes only to the local memory file.

These are intended boundaries, not independently verified security guarantees. Before relying on them, test path traversal, symbolic links, file replacement races, unexpected encodings, malformed JSON, oversized input, and tool argument manipulation. Confirm that no tool can read outside the intended directory or write arbitrary files.

## Model and prompt-injection risks

Local models can produce incorrect output and can be manipulated by untrusted content in prompts or files. Treat all file contents, tool arguments, model output, and recalled notes as untrusted data. Do not let the model's natural-language claims override the actual tool permissions or application checks. Never execute model-generated shell commands or code automatically.

## Memory handling

The local memory file may contain sensitive information if the operator saves it. Keep it out of version control, restrict filesystem permissions, avoid sensitive content, and delete it locally when no longer needed. The sample file in this repository contains only placeholder data.

## Reporting

Do not publish exploit details containing real credentials or personal data in public issues. For a security concern, first remove sensitive material from the report and contact the repository owner through an appropriate private channel.
