# 北京邮电大学物理实验报告 Skill

**专门面向北京邮电大学（BUPT）物理实验报告的 Agent Skill。** 按北邮报告本的栏目组织内容，为七项物理实验分别提供预习、真实数据处理、报告写作、排版和审阅指引。

> 非官方学生学习工具。当前教师要求、当次讲义、报告本和本人原始记录优先；不代表北京邮电大学或物理实验中心发布的统一规范。

An unofficial Agent Skill specifically for **Beijing University of Posts and Telecommunications (BUPT) physics lab reports**, with seven experiment-specific routes, report-form guidance, traceable data processing, and editable Markdown templates.

## 覆盖的七项实验

| 分流 | 实验 | 主要针对的问题 | 可填模板 |
|---|---|---|---|
| 01 | [等厚干涉](references/01-equal-thickness.md) | 牛顿环/劈尖辨认、读数与级次、曲率或厚度 | [模板](assets/01-equal-thickness.md) |
| 02 | [转动惯量](references/02-moment-of-inertia.md) | 装置与转轴、空载与标准件、周期及惯量模型 | [模板](assets/02-moment-of-inertia.md) |
| 03 | [自搭电桥](references/03-self-built-bridge.md) | 实际接线、平衡关系、交换法及不确定度 | [模板](assets/03-self-built-bridge.md) |
| 04 | [简谐振动](references/04-simple-harmonic-motion.md) | 触发与周期计数、质量—周期关系、有效质量 | [模板](assets/04-simple-harmonic-motion.md) |
| 05 | [模拟静电场](references/05-electrostatic-field.md) | 类比条件、等势点、电极边界与场线 | [模板](assets/05-electrostatic-field.md) |
| 06 | [霍尔元件](references/06-hall-effect.md) | 四次换向、工作/励磁电流、测场与附加效应 | [模板](assets/06-hall-effect.md) |
| 07 | [测量声速](references/07-speed-of-sound.md) | 多方法分表、半波长/整波长判别、温度条件 | [模板](assets/07-speed-of-sound.md) |

数字示波器、LabVIEW、分光计、几何光学等不属于当前七路正式报告范围。上述范围对应本项目已核对的课表，不表示北邮所有学生的课表都相同。

## 两阶段完成，按模板分点

1. **预习**：完成当前报告本前两页的实验目的、仪器名称（型号参数）、实验原理和操作步骤。
2. **实验后报告**：取得实测数据后续写数据处理与讨论、思考题和总结；按“数据计算 → 不确定度 → 结果表示与讨论”组织。

当前模板的栏目与留白优先；关键计算保留公式、带单位代入和结果，详细核算按需另附，避免反复堆叠同一规则。课堂不确定度和修约约定见 [第一节课要点](references/measurement-basics.md)。

## 针对北邮报告本的结构

正文默认按以下五栏组织，不强加论文式摘要、长目录或背景综述：

1. 实验目的。
2. 实验仪器名称：型号、主要参数。
3. 实验原理和操作步骤：内部区分原理与步骤，解释公式及所需装置、电路或光路图。
4. 实验数据处理与讨论：数据依据、计算、所需不确定度、结果表示与讨论。
5. 回答问题与实验总结。

“任课教师指导意见”留空。原始数据单作为证据保留；历史报告中的任务、免做题、数值、仪器设定和个人经历不会自动继承。

详见 [栏目与排版](references/report-form.md)、[共用数据处理规范](references/common.md)、[北邮范文的借鉴与修正](references/exemplar-lessons.md)。

## 数据展示与计算过程

所有分流强调“原始读数 → 处理量 → 平均/逐差/拟合 → 最终结果”的对应关系。图表保留原始依据、编号、转换定义和单位，并区分实测点、派生点及拟合/理论线。

每种必要计算和关键最终量列出 **符号公式 → 带单位的实际数值代入 → 结果**。重复计算可用完整实例加可追溯的逐行表格；不能只有公式或只有最终数字。具体写法和教师声速示例见 [数据关系与计算呈现](references/data-presentation.md)。

## 安装与使用

这是一个文件夹形式的 skill，入口为 [SKILL.md](SKILL.md)。基础版本不要求 API Key、特定连接器或联网服务；生成 Word/PDF 和计算图表的能力取决于使用它的 agent 环境。

### Codex

可以让内置 skill-installer 从本仓库安装，说明仓库根目录就是 skill：

```text
使用 $skill-installer，安装 https://github.com/lhr20060515-nb/bupt-physics-lab-report ，skill 位于仓库根目录。
```

也可以手动安装到官方文档列出的用户技能目录：

```bash
git clone https://github.com/lhr20060515-nb/bupt-physics-lab-report.git ~/.agents/skills/bupt-physics-lab-report
```

Windows 可将完整仓库文件夹放入用户目录下 `.agents/skills/bupt-physics-lab-report/`。如果你现有 Codex 配置使用其他技能目录，沿用该目录；避免重复安装同名 skill。当前路径与加载方式参见 [OpenAI 官方技能文档](https://learn.chatgpt.com/docs/build-skills)。

安装后可这样使用：

```text
使用 $bupt-physics-lab-report。
本次实验是霍尔元件测磁场。请先核对我的讲义和四方向原始电压读数，
按北邮报告本完成“实验数据处理与讨论”，保留计算依据并检查单位和不确定度。
```

只写预习时，说明“只完成实验目的、仪器名称、原理和步骤”；只检查某个计算时，说明检查范围。完整报告请同时给出当次讲义、任务/思考题、真实数据、空白模板以及目标格式。

### 其他 agent

支持 Agent Skills 格式的工具可按其官方方式加载完整文件夹。只会读取文件的 agent，也可先读取 `SKILL.md`，再按路由读取共用规则、所选实验参考和模板。不要只复制入口文件而遗漏 `references/` 与 `assets/`。

`agents/openai.yaml` 是可选的 Codex 界面元数据；主体指引和模板采用 Markdown。其他 agent 的安装方式和工具能力需要自行验证，不承诺所有平台自动兼容。

## 资料与准确性

本项目比较北邮公开历史报告、北邮教师研究及校方课程信息，原始链接、实际已读范围和证据缺口列在 [来源与核验](references/sources.md)。优先借鉴可追溯的数据组织、带单位代入、多方法比较和有依据的讨论，不复制成品作业。

- 电桥、霍尔、声速已有北邮完整历史报告用于比较。
- 等厚干涉有北邮教师研究；研究装置不自动等于课堂装置。
- 转动惯量已有作者提供并授权公开的 [90+扭摆报告](examples/02-torsion-report-90plus.pdf)，并附 [生成与采纳稿的写作取舍](references/user-torsion-example.md)；90+为作者说明，旧参数仍需核对。简谐振动的公开历史同题完整范文仍有缺口。
- 模拟静电场的排版 JSON 不算完整优秀报告，相关说法经过重新核对。
- 历史文件的“90/A”等名称没有被独立核验为成绩保证。

没有真实数据时，只能生成预习、空白表或草稿。未知的读数、型号、图像、签名和实验经历不编造；演示数据必须明确标注，不能混入提交稿。

除作者明确授权的自有扭摆范例外，公开版不分发空白扫描件、课程讲义全文或他人完整报告。范例原件保留原样，版权归属及适用范围见 [说明](examples/README.md)；使用者仍需提供自己的当次数据与模板。

## 仓库内容

```text
bupt-physics-lab-report/
├── SKILL.md
├── agents/openai.yaml
├── references/               # 共用规则、报告本、范文取舍、来源及七路参考
├── assets/                   # 七份原创可填 Markdown 模板
├── examples/                 # 作者授权的扭摆原件及归属说明
├── README.md
├── LICENSE
├── THIRD_PARTY_NOTICES.md
└── .gitignore
```

当前发行的是指引和模板，没有独立的图形界面、报告计算引擎或 Word/PDF 渲染器；也未以七组本学期真实数据完成端到端行为评测。内容、公式和排版仍需按实际任务核对。

## 版本与更新

行为变化及原因记录于 [CHANGELOG.md](CHANGELOG.md)，具体文件差异见 GitHub 提交历史。每次更新使用独立提交；日志日期不等于已创建版本 Tag 或 Release。

## 参与改进

欢迎提交北邮同题资料链接、公式问题、装置差异和模板改进。请说明适用学年/课程、实验完整名称、原始依据及复现条件；示例数据标明为演示或脱敏。只提交有权公开的材料，去除姓名、学号、签名、联系方式和个人记录。

## 许可证

本仓库原创 skill 指令、整理文字和模板采用 [MIT License](LICENSE)。外部参考资料的版权与许可归原作者，本许可不授予对其教材、报告、图片或学校标识的再分发权，详见 [第三方资料说明](THIRD_PARTY_NOTICES.md)。
