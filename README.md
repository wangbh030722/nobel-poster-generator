# Nobel Poster Generator

诺贝尔年度公告海报生成 Skill：依据实际参考图，将照片或产品角色转换为自定义获奖肖像海报，重点匹配人物尺度、姿态及文字比例。

## 安装与使用

```sh
git clone https://github.com/wangbh030722/nobel-poster-generator.git ~/.codex/skills/nobel-poster-generator
```

目标目录已存在时，先备份或选择其他目录，避免覆盖已有 Skill。私有仓库需要拥有访问权限。

在 Codex 中调用：

```text
使用 $nobel-poster-generator，依据我的照片生成诺贝尔年度公告风格海报。
姓名：…
奖项：…
获奖理由：…
```

附上人物照片；年份可选，默认在线核验最新完整年度。支持全身照、半身照、头像、多人及产品拟物角色。需要可用的图像生成工具和可查看的参考素材。

## 工作方式

- 查看并测量参考中的人物、文字区域与留白比例。
- 照片控制身份，模板控制姿态、裁切及尺度。
- 产品角色先核验官方 logo/icon，再保留辨识特征进行插画化。
- 检查姓名和理由原文，针对偏差最多修订两轮。

约 3% 的主要区域几何偏差是验收目标，不是模型精度保证。自创奖项与人数扩展属于构图改编，生成结果不是官方获奖公告。

## 示例

2026 年自创 Superintelligence（SI）奖，Muse、Grok Bot、Cue、Dots 四人同框。由内置图像工具生成；Grok Bot 与 Cue 根据实际图标修正，身体为拟物补绘。

![SI 示例](examples/nobel-si-2026.png)

## 文件

- [SKILL.md](SKILL.md)：完整工作流程。
- [构图测量与照片适配](references/composition-and-photo-adaptation.md)：比例、适配与验收规则。
- `agents/openai.yaml`：中文入口及自动发现配置。
