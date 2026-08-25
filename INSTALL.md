# Install / 安装

One folder, `academic-deslop`, works in Claude Code and Codex. The release zip contains that folder at its root.

同一个 `academic-deslop` 文件夹兼容 Claude Code 和 Codex；发布包解压后顶层即为该文件夹。

## Claude Code

Personal installation / 个人安装：

```text
~/.claude/skills/academic-deslop/SKILL.md
```

Project installation / 项目安装：

```text
<project>/.claude/skills/academic-deslop/SKILL.md
```

macOS or Linux:

```bash
mkdir -p ~/.claude/skills
unzip academic-deslop-v1.0.0.zip -d ~/.claude/skills/
```

Windows PowerShell:

```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\skills" | Out-Null
Expand-Archive .\academic-deslop-v1.0.0.zip -DestinationPath "$HOME\.claude\skills" -Force
```

Invoke explicitly with `/academic-deslop`, or describe a matching academic-editing task and allow automatic discovery. Claude Code watches existing skill directories for changes; restart once if the top-level skills directory was created after the session started.

显式调用使用 `/academic-deslop`；也可以直接描述任务让 Claude 自动触发。如果当前会话启动时 `~/.claude/skills` 尚不存在，新建后重启一次 Claude Code。

## Codex

Current personal installation / 当前个人安装路径：

```text
$HOME/.agents/skills/academic-deslop/SKILL.md
```

Repository installation / 项目安装路径：

```text
<repo>/.agents/skills/academic-deslop/SKILL.md
```

macOS or Linux:

```bash
mkdir -p ~/.agents/skills
unzip academic-deslop-v1.0.0.zip -d ~/.agents/skills/
```

Windows PowerShell:

```powershell
New-Item -ItemType Directory -Force "$HOME\.agents\skills" | Out-Null
Expand-Archive .\academic-deslop-v1.0.0.zip -DestinationPath "$HOME\.agents\skills" -Force
```

Invoke explicitly with `$academic-deslop`, or use a matching natural-language request. If Codex does not discover a newly installed skill, restart it. Older Codex builds may still use `~/.codex/skills`; prefer the current `.agents/skills` location unless your installed build documents the legacy path.

显式调用使用 `$academic-deslop`。如果安装后未出现，重启 Codex。旧版 Codex 可能仍读取 `~/.codex/skills`，但新安装应优先使用当前官方 `.agents/skills` 路径。

After the GitHub repository is public, Codex users can also ask the built-in `$skill-installer` to install `academic-deslop` from `https://github.com/BobbyMorgan/turing-pass-scholar`.

## Verify / 验证

Start a new session and use:

```text
This is an original research paper excerpt. Use paragraph-approval mode and assess its AI flavor: <paste text>
```

Expected behavior: the skill immediately assesses the excerpt because both genre and mode are explicit. If either is missing, it asks once for the missing choice and stops before editing.

预期行为：文体和模式都明确时直接开始；缺少任一项时，只集中询问一次，然后在用户选择前停止编辑。
