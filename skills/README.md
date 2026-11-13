# 技能库

按类别整理的 AI 短剧创作技能，来源为 [awesome-short-drama-skills](https://github.com/UnderleveledBuilder/awesome-short-drama-skills) 收录的公开项目。

> **这不是市场条目。** 本目录下的内容是 Claude / WorkBuddy 规范的 `SKILL.md` 技能包，ArcReel 的「市场」页面只显示 `endpoints/` 下的调用端点定义，**不会显示这里的任何内容**。要用技能，请按下文「安装」一节手动放置。

## 目录

| 类别 | 目录 | 技能 | 作用 |
|---|---|---|---|
| 分镜与镜头设计 | `storyboard/` | `seedance-shot-design` | Seedance 2.5 镜头设计：4—30 秒、超长视频、延长、局部替换、多宫格分镜、白模、绿幕 |
| | | `cinematic-director` | 导演与预演：潜台词拆解、节拍、镜头清单、关键帧，内置 20 种导演风格 |
| | | `h3-storyboard` | MiniMax H3 拆镜与表演设计，附实测数据（语速、对白标签、表情节拍上限） |
| 提示词与模型语法 | `prompt/` | `seedance-2-5-prompting` | 30 种运镜定义与冲突规则、参考素材角色绑定、R2V / 白模、局部编辑与延长 |
| | | `universal-video-prompt-skill` | 一份模型无关的提示词 spec，再编译到具体模型，适合多模型并行 |
| | | `seedance-2-5-video-director` | Seedance 2.5 能力边界、提示词蓝图、人物锁定、失败诊断 |
| 剧本诊断 | `review/` | `screenplay-review-checklist` | 37 条判据的对抗式审查，只挑毛病，输出踩雷报告 |
| 动作戏 | `action/` | `fight-prompt-director` | 动作差异化、交锋因果链、跨镜连续性，适配 Seedance 与 H3 |
| 文风与去 AI 味 | `writing/` | `humanizer` | 按「Signs of AI writing」清单去除 AI 痕迹，打磨对白与旁白 |
| 工具 | `tooling/` | `short-drama-skill-finder` | 拉线上目录，按阶段 / 模型 / 许可证筛候选技能 |

## 安装

技能目录名即调用名，`SKILL.md` 的 frontmatter 里 `name` 必须与目录名一致。

> 例外：`review/screenplay-review-checklist` 的目录名为了可移植性保持 ASCII，其 frontmatter 的 `name` 是 `编剧审查清单`。调用时用中文名，或把目录一并改名。

**WorkBuddy**（用户级，所有项目可用）

```bash
git clone --depth 1 https://github.com/l1366956839-a11y/arcreel-market.git
cp -r arcreel-market/skills/storyboard/h3-storyboard ~/.workbuddy-ai/skills/
```

Windows 下的用户级目录是 `C:\Users\<用户名>\.workbuddy-ai\skills\`。

**ArcReel 内嵌 Agent**（项目级）

```bash
cp -r arcreel-market/skills/prompt/seedance-2-5-prompting \
      <ArcReel 项目目录>/.claude/skills/
```

**Claude Code**：放进 `.claude/skills/` 即可。

新增技能后当轮即可按名字点名调用；要出现在技能列表里，需重开会话。

## 来源与许可

| 技能 | 上游仓库 | 许可 |
|---|---|---|
| `seedance-shot-design` | [woodfantasy/Seedance-ShotDesign-Skills](https://github.com/woodfantasy/Seedance-ShotDesign-Skills) | MIT-0 |
| `cinematic-director` | [wuwangzhang1216/DirectorSKILL](https://github.com/wuwangzhang1216/DirectorSKILL) | MIT |
| `h3-storyboard` | [phileiny/h3-storyboard-skill](https://github.com/phileiny/h3-storyboard-skill) | MIT |
| `seedance-2-5-prompting` | [babicat4242-svg/seedance-2-5-prompting](https://github.com/babicat4242-svg/seedance-2-5-prompting) | MIT |
| `universal-video-prompt-skill` | [AtlasCloudAI/awesome-seedance-2.5-prompts-skills](https://github.com/AtlasCloudAI/awesome-seedance-2.5-prompts-skills) | CC-BY-4.0（保留署名） |
| `seedance-2-5-video-director` | [liyue-aigc/seedance-2-5-video-director](https://github.com/liyue-aigc/seedance-2-5-video-director) | MIT |
| `screenplay-review-checklist` | [zhlmi/screenplay-review-checklist](https://github.com/zhlmi/screenplay-review-checklist) | MIT |
| `fight-prompt-director` | [irenerachel/fight-prompt-director](https://github.com/irenerachel/fight-prompt-director) | MIT |
| `humanizer` | [blader/humanizer](https://github.com/blader/humanizer) | MIT |
| `short-drama-skill-finder` | [UnderleveledBuilder/awesome-short-drama-skills](https://github.com/UnderleveledBuilder/awesome-short-drama-skills) | CC0-1.0 |

各技能版权归原作者所有，此处仅作转载整理。如原作者有异议，请开 issue，我们会立即移除。

## 未收录

以下项目质量较高，但**上游未声明许可证**（默认保留所有权利），为避免公开转载的授权风险，本仓库不收录，请直接访问上游获取：

| 项目 | 内容 | 上游 |
|---|---|---|
| `ai-video-continuity-director` | H3 多镜连续性总控：180° 轴线、肢体与道具状态锁、双轨时长引擎、尾帧接力 | [MIKA6941/Comfy-H3-Director](https://github.com/MIKA6941/Comfy-H3-Director) |
| `h3-prompt-writing` | H3 五种模式（T2VA / I2VA / FL2VA / L2VA / Ref2VA）的提示词结构 | 同上 |

如作者补充许可证，欢迎提 PR 收录。
