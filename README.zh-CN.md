<div align="center">

# Nobel Poster Generator

**把人物照片与产品图标，变成自定义诺贝尔公告风格海报。**

[English](README.md) · [简体中文](README.zh-CN.md)

`Codex Skill` · `Photo → Portrait` · `Logo → Character`

</div>

---

## 给日常中的智慧颁个奖

把人物照片、团队成员或 AI 助手变成一张自定义诺贝尔公告风格海报。生成前先查看实际参考图，分析头部大小、姿态、裁切、人物间距和文字比例，让整张海报的构图更贴合参考。

**照片决定人物身份，参考图决定构图。**

<p align="center">
  <img src="examples/nobel-si-2026.png" alt="Muse、Grok Bot、Cue、Dots 四位助手的自创超级人工智能奖海报" width="640">
</p>

<p align="center"><em>2026 年自创 Superintelligence（SI）奖，扩展为四位角色同框。</em></p>

## 能做什么

| 输入 | 输出效果 |
| :--- | :--- |
| 全身照、半身照、头像 | 保留人物辨识度，按参考重新适配头部尺寸、姿态及裁切 |
| 多位人物 | 统一肖像布局，并明确姓名与左右位置的对应关系 |
| 产品 logo、应用图标、吉祥物 | 保留原轮廓和表情特征，再转换为海报插画角色 |
| 自定义姓名、奖项、年份、获奖理由 | 按参考的文字层级和比例编排 |

可指定历史年度，也可让 Skill 在线核验最近已完整公布六类奖项的年度。支持自创奖项和人数扩展，并明确标为构图改编。

## 安装

将仓库克隆到 Codex 的技能目录：

```sh
git clone https://github.com/wangbh030722/nobel-poster-generator.git \
  ~/.codex/skills/nobel-poster-generator
```

如果设置了自定义 `CODEX_HOME`，请安装到其 `skills` 目录。目标目录已经存在时，先备份或选择其他位置；私有仓库需要 GitHub 访问权限。

**运行条件：** Codex 中有可用的图像生成工具、能够查看参考图，并提供清晰照片或可辨识的图标。这是一套生成流程 Skill，不是独立应用，也不附带图像模型。

## 马上试试

上传一张照片，然后发送：

```text
使用 $nobel-poster-generator，生成一张诺贝尔公告风格海报。
姓名：陈晓
奖项：诺贝尔日常巧思奖
年份：2026
获奖理由：将日常难题转化为出人意料的优雅解决方案
```

也可以为 AI 助手做一张集体海报：

```text
使用 $nobel-poster-generator，生成四位角色同框的海报。
从左到右：Muse、Grok Bot、Cue、Dots。
奖项：Nobel Prize in Superintelligence
年份：2026
获奖理由：for solving the problems of everyday life and work,
and helping humanity reach new heights
请先核验各产品的 logo 或应用图标，
再保留原本的轮廓和表情特征进行拟物化。
```

提示和海报文字都可使用中文或英文。提供准确的姓名与获奖理由；缺少信息时，Skill 会集中询问。想更贴合特定版式，可以指定参考年度、奖项，或直接上传目标海报。

## 从参考图到海报

1. **寻找并查看参考**：记录来源与模板年度。
2. **分析构图比例**：用归一化坐标记录人物和文字区域。
3. **适配人物或角色**：保留五官身份，或 logo/icon 的辨识特征。
4. **生成并复核**：针对具体偏差，最多修订两轮。

上方示例由内置图像工具生成。Grok Bot 的倾斜胶囊眼睛、Cue 的圆角轮廓与眨眼表情，均根据实际图标修正；身体为自定义补绘。该示例采用第三方转载的 2025 年公告构图进行改编，尚未核验为官方原图的精确复刻。

## 质量与署名

- 追求视觉上的高贴合，不保证像素级一致。验收指南中的约 3% 构图偏差是目标，不是模型精度承诺。
- 姓名、理由和人物辨识度需要实际看图检查。复杂姿态、过小人脸和过长文字，可能需要更清晰输入或精简文案。
- 生成结果是自定义作品，不是官方获奖公告或官方背书。不会把原画家的签名、原作署名作为新作品署名。

## 文件导航

| 文件 | 用途 |
| :--- | :--- |
| [SKILL.md](SKILL.md) | 输入、参考选择、生成与交付流程 |
| [构图测量与照片适配](references/composition-and-photo-adaptation.md) | 比例测量、照片处理与视觉验收 |
| [agents/openai.yaml](agents/openai.yaml) | Codex 展示信息与自动发现配置 |

Skill 操作指令目前以中文编写，使用示例与项目说明提供中英双语版本。
