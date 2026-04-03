# Ollama Zsh Plugin

A Zsh completion plugin for [Ollama](https://ollama.com), providing rich tab-completion for all commands, flags, and model names.

## Features

- Complete all Ollama subcommands (`run`, `stop`, `pull`, `show`, `launch`, etc.)
- Dynamic model name completion from `ollama list`
- Running model completion for `stop` (from `ollama ps`)
- Integration name completion for `launch` (claude, cline, codex, droid, etc.)
- Full flag completion for every subcommand
- Help topic completion

### Supported Commands

| Command | Model Completion | Notes |
|---------|-----------------|-------|
| `run` | All models | + thinking mode, image gen flags, etc. |
| `stop` | Running models | Only shows currently loaded models |
| `show` | All models | + `--license`, `--template`, ... |
| `pull` | All models | |
| `push` | All models | |
| `cp` | All models | Source and destination |
| `rm` | All models | Multiple models supported |
| `create` | - | + `--file`, `--quantize` |
| `launch` | Integrations | + `--model`, `--config`, `-y` |
| `help` | - | Completes command names |

## Installation

### Oh My Zsh

Clone into the custom plugins directory:

```bash
git clone https://github.com/mejistus/ollama-zsh-plugin \
  ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/ollama
```

Then add `ollama` to your plugin list in `~/.zshrc`:

```zsh
plugins=(... ollama)
```

Restart your shell or run `exec zsh`.

### Manual

Copy `_ollama` and `ollama.plugin.zsh` to a directory in your `$fpath`, then restart your shell.

## Requirements

- Zsh with completion enabled
- [Ollama](https://ollama.com) installed and available in `$PATH`
- Ollama server running (for dynamic model completion)

## License

MIT
