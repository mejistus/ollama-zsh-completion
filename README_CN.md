# Ollama Zsh 补全插件

为 [Ollama](https://ollama.com) 提供丰富的 Zsh Tab 补全支持，覆盖所有命令、参数和模型名称。

## 功能

- 补全全部 Ollama 子命令（`run`、`stop`、`pull`、`show`、`launch` 等）
- 从 `ollama list` 动态获取模型名称进行补全
- `stop` 命令从 `ollama ps` 获取正在运行的模型
- `launch` 命令补全集成名称（claude、cline、codex、droid 等）
- 每个子命令的完整 flag 补全
- `help` 命令补全子命令名称

### 支持的命令

| 命令 | 模型补全 | 说明 |
|------|---------|------|
| `run` | 所有模型 | + thinking 模式、图像生成参数等 |
| `stop` | 运行中的模型 | 仅显示当前已加载的模型 |
| `show` | 所有模型 | + `--license`、`--template` 等 |
| `pull` | 所有模型 | |
| `push` | 所有模型 | |
| `cp` | 所有模型 | 源模型和目标模型 |
| `rm` | 所有模型 | 支持多个模型 |
| `create` | - | + `--file`、`--quantize` |
| `launch` | 集成名称 | + `--model`、`--config`、`-y` |
| `help` | - | 补全命令名称 |

## 安装

### Oh My Zsh

将插件克隆到自定义插件目录：

```bash
git clone https://github.com/<your-username>/ollama-zsh-plugin \
  ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/ollama
```

在 `~/.zshrc` 中将 `ollama` 添加到插件列表：

```zsh
plugins=(... ollama)
```

重启终端或执行 `exec zsh` 即可生效。

### 手动安装

将 `_ollama` 和 `ollama.plugin.zsh` 复制到 `$fpath` 中的任意目录，然后重启终端。

## 依赖

- 启用了补全功能的 Zsh
- [Ollama](https://ollama.com) 已安装且在 `$PATH` 中
- Ollama 服务运行中（用于动态模型补全）

## 许可证

MIT
