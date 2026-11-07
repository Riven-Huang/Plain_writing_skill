# Plain Writing

`plain-writing` 是一个 Codex Skill，用于起草、润色和审阅中英文正式文稿，适用于技术报告、规格书、申报书、论文和项目 README。

写作时，按内容之间的实际关系安排章节，用准确的标题和术语交代工作。改稿时，删除防御性声明、同义复述和修订痕迹，保留支撑结论所需的证据、条件和推导。完整规则见 [SKILL.md](plain-writing/SKILL.md)。

## 安装

克隆仓库并进入项目目录。

```bash
git clone https://github.com/Riven-Huang/Plain_writing_skill.git
cd Plain_writing_skill
```

将 `SKILL.md` 复制到 Codex 用户级技能目录。

**Windows PowerShell**

```powershell
$codexDir = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE '.codex' }
$skillDir = Join-Path $codexDir 'skills/plain-writing'
New-Item -ItemType Directory -Path $skillDir -Force | Out-Null
Copy-Item -LiteralPath './plain-writing/SKILL.md' -Destination (Join-Path $skillDir 'SKILL.md')
```

**macOS / Linux**

```bash
skill_dir="${CODEX_HOME:-$HOME/.codex}/skills/plain-writing"
mkdir -p "$skill_dir"
cp plain-writing/SKILL.md "$skill_dir/SKILL.md"
```

## 使用

在 Codex 中用 `$plain-writing` 指定 Skill，并提供文稿、提纲或材料。只修改语言时，可在请求中明确改稿范围。

> 用 $plain-writing 润色这份测试报告。保留原有章节、试验数据和结论，检查重复说明与防御性话语。

## 改写示例

前文已交代测试端口与夹具时，结果段可以直接报告观测结果。

| 原句 | 改写 |
| --- | --- |
| 需要指出的是，在上述端口与夹具条件下，试验记录到飞控复位。该现象不代表其他试验条件下也会发生复位。 | 试验记录到飞控复位。 |
