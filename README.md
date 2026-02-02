# Martin Original Agent (Oct 2023)

Mission Learning Statement
- Mission: Ship an early, working local agent that turns prompts into executable system actions.
- Learning focus: prompt-to-action loops, command extraction, and safety guardrails.
- Project start date: 2023-10-01 (original release window)

Early CLI agent that turns prompts into executable system commands, with a simple repl loop and guardrails.

## Features

- Prompt-to-command extraction using OpenAI chat completions
- Command execution with basic success/failure tracking
- Error-driven re-run flow with suggested fixes
- Optional local env.txt loader for API keys

## Installation

### Requirements

- Python 3.8+
- `requests`
- `tqdm`

### Setup

- Set `OPENAI_API_KEY` in your environment or create a local `env.txt` next to `martin.py`.

## Quick Start

```bash
python martin.py
```

## Usage

- Type a request, receive a response, and run suggested commands.
- Enter `quit` to exit the loop.
- Use the re-run prompt to retry failed commands with suggested fixes.

## Architecture

```
User Prompt
    |
    v
Prompt Builder (context + directives)
    |
    v
OpenAI API (chat completions)
    |
    v
Command Extractor
    |
    v
Execution Engine
    |
    +--> Success -> next prompt
    |
    +--> Failure -> suggested fix -> re-run
```

## Project Structure

```
martin.py   # Main CLI loop, API calls, command execution
env.txt     # Local-only API key (gitignored)
```

## Building

No build step required. Run directly with Python.

## Contributing

Historical artifact. If you want to experiment, fork the repo and make changes there.

## License

No license file is included in this repository.
