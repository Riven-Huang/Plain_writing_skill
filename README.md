# Plain Writing

`plain-writing` 是一个 Codex Skill，用于起草、润色和审阅中英文正式文稿，适用于技术报告、规格书、申报书、论文和项目 README。完整规则见 [SKILL.md](plain-writing/SKILL.md)。

## 1 写作规则

1. 禁止强行制造逻辑关系
2. 默认删除无必要的防御性话语
3. 规范标题与章节命名
4. 禁止修改痕迹污染，暴露写作与修改过程
5. 拒绝重复表达，车轱辘话，提高信息密度
6. 保持正式书面表达，避免设问与过度口语化
7. 理清内容关系，组织论述逻辑
8. 调整句式结构，保持自然的行文节奏

## 2 安装

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

## 3 使用

在 Codex 中用 `$plain-writing` 指定 Skill，并提供文稿、提纲或材料。只修改语言时，可在请求中明确改稿范围。

> 用 $plain-writing 润色这份测试报告。保留原有章节、试验数据和结论，检查重复说明与防御性话语。

## 4 改写示例

| 对应规则 | 原句 | 改写 |
| --- | --- | --- |
| 1 逻辑关系 | 本系统不仅采集端口电压，更能记录飞控复位时刻。 | 本系统采集端口电压，并记录飞控复位时刻。 |
| 2 防御性话语（前文已交代试验条件） | 需要指出的是，在上述端口与夹具条件下，试验记录到飞控复位。该现象不代表其他试验条件下也会发生复位。 | 试验记录到飞控复位。 |
| 3 标题命名 | 如何布置驱动板的电源走线？ | 驱动板电源布线 |
| 4 修改痕迹 | 根据修改意见，现改为从电源端口注入干扰。 | 试验从电源端口注入干扰。 |
| 5 信息密度 | 本文比较三种控制策略下的稳态纹波。通过比较，可以获得三种策略在稳态纹波上的差异。 | 本文比较三种控制策略下的稳态纹波。 |
| 6 书面语体 | 先看看电源电压有没有掉下来，再看看飞控还能不能跑。 | 先检查电源电压是否跌落，再确认飞控能否继续运行。 |
| 7 论述顺序 | 试验采用端口注入。项目需要比较不同端口的响应，端口注入可限定激励位置。 | 项目需要比较不同端口的响应。端口注入可限定激励位置，因此试验采用该方法。 |
| 8 句式节奏 | 控制器上电后完成自检并在电源轨稳定且通信链路建立后进入待机状态，随后在收到启动指令且各项联锁检查通过后使能功率级。 | 控制器上电后完成自检。电源轨稳定且通信链路建立后，控制器进入待机状态。收到启动指令且各项联锁检查通过后，控制器使能功率级。 |
