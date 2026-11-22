# Network Automation Engineer
## From Cisco CLI to Python and Ansible

Source code for the interactive course console created in ChatGPT Pages.

## Included

- Three restricted terminal simulations: Linux Fundamentals, Linux Administration, and SSH Fundamentals.
- Thirty quiz questions with automatic grading, an 80% passing score, and unlimited retries.
- Lab completion checks, quiz attempt history, and resume notes.
- A static OpenSSH configuration exercise.
- Pages widget-state integration with an editable progress-record fallback.

Lessons 1 and 2 were previously delivered but have **not** been verified as completed. Lesson 3 is the next lesson. No test results in this repository count as learner progress.

## Files

| File | Purpose |
| --- | --- |
| learning-console.html | HTML fragment containing the interactive console and question bank |
| test-course-logic.cjs | Dependency-free Node.js tests for simulator, grading, and state behavior |
| README.md | Usage and course links |

## Use in Pages

The HTML is an embeddable fragment intended for the Pages visualization sandbox. Its appearance uses the host's form and layout utilities. When available, it saves through `window.openai.setWidgetState` and restores `window.openai.widgetState`. It handles incoming `openai:set_globals` state updates.

Outside Pages, the fragment can run in a browser, but host styling and persistent saved state are not provided. The console reports session-only mode when the host state API is unavailable. Use **Show progress record** and copy the record into the editable Progress Tracker as a fallback.

The state size guard stops sending updates once course state exceeds 14,000 UTF-8 bytes and asks you to copy the complete record. It does not delete quiz history. Do not treat a save submission as confirmation of cross-session synchronization.

## Run tests

Install a current Node.js release supporting `structuredClone`, then run:

```bash
node test-course-logic.cjs
```

Tests cover all three lab success paths, incomplete quiz rejection, 70% failure, 80% passage, the SSH configuration checker, attempt retention, saved-state restoration, incoming state synchronization, and avoiding default-state writes on load. They use a minimal DOM stub and mocked Pages host API; they do not verify browser layout or live Pages synchronization.

## Course pages

- [Course dashboard](https://chatgpt.com/space/page_8ad155322ddc819197f1849f0d792e80)
- [Lesson 1 Linux Fundamentals](https://chatgpt.com/space/page_939297d8d93c8191b7925a39dbfb9ef2)
- [Lesson 2 Linux Administration](https://chatgpt.com/space/page_e700ea6035a08191af028c7b1a9a4c96)
- [Lesson 3 SSH Fundamentals](https://chatgpt.com/space/page_5e6a8d2b94688191a843ee6126ab19ad)
- [Interactive practice and progress](https://chatgpt.com/space/page_759f8c0469948191a7872fc408f54774)

Page access depends on your ChatGPT account permissions. GitHub does not host or automatically synchronize those Pages or learner progress.

## Roadmap

1. Linux Fundamentals — prepared
2. Linux Administration — prepared
3. SSH Fundamentals — prepared
4. Python Fundamentals — outline
5. Python Programming — outline
6. Python for Networking — outline
7. YAML and JSON — outline
8. Ansible Installation — outline
9. Ansible Inventory — outline
10. Ansible Playbooks — outline
11. Advanced Ansible — outline
12. Network Configuration Backups — outline
13. Network Configuration Changes — outline
14. NETCONF, RESTCONF and YANG — outline

Later lesson content and assessments are prepared one lesson at a time in Pages. The full instructional text and capstone remain in the course Pages; this repository currently contains the interactive console source.

## Lab scope

The terminal implements only the commands listed by `help`. Reports and SSH sessions are simulated; no shell programs run and no network devices are contacted. The configuration checker checks required text patterns, not the full OpenSSH grammar. All addresses and identities are fictional. Python execution and Ansible execution are introduced in later lessons.

## Official references

- [GNU Coreutils](https://www.gnu.org/software/coreutils/manual/coreutils.html)
- [Ubuntu OpenSSH](https://ubuntu.com/server/docs/how-to/security/openssh-server/)
- [OpenSSH client configuration](https://man.openbsd.org/ssh_config)
- [Python tutorial](https://docs.python.org/3/tutorial/)
- [Ansible network_cli](https://docs.ansible.com/projects/ansible/latest/collections/ansible/netcommon/network_cli_connection.html)
- [Ansible libssh](https://docs.ansible.com/projects/ansible/latest/collections/ansible/netcommon/libssh_connection.html)
