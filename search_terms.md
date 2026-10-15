# AI4S 检索词与政策来源说明

**版本：V3.1-R3（化工补词试检版）　文档日期：2026-10-15　数据库：Web of Science Core Collection**

## 1 修订范围与基线

当前启用**V3.1-R3（化工补词试检版）**，直接基线为用户已执行并报告11,582篇的V3.1-R2。本轮在第二逻辑块的TS领域组中恢复`"reactor design"`、`"transport phenomena"`、`"multiphase flow"`，补充`"membrane distillation"`、`"extractive distillation"`，共增加5项OR表达。

数学维持R2的12项，其中numerical analysis和inverse problem*已在R2恢复；原有其他领域42项、AI方法词、AB科研任务词、三个逻辑块、字段和全局限制均不改变。化工由11项增至16项，第二块领域表达合计70项。R3实际WoS命中数尚待用户执行，不使用11,582或本地匹配增量冒充R3实测。

| 版本 | 数学 | 化工 | 原有其他领域 | 第二块领域合计 | 执行记录 |
| --- | ---: | ---: | ---: | ---: | --- |
| 原V3.1 | 22 | 19 | 42 | 83 | 历史截图报告11,654篇 |
| V3.1-R1 | 10 | 11 | 42 | 63 | 用户报告11,443篇；收到211条减少记录 |
| V3.1-R2 | 12 | 11 | 42 | 65 | 用户报告11,582篇；收到实际剩余72条 |
| **V3.1-R3（当前）** | **12** | **16** | **42** | **70** | **待执行和反馈** |

仓库此前发布的V3.2是采用对象与邻近条件的另一条修订方案，不是本轮R3的直接基线；其11,684条及本地回查数据保留为历史记录，不与R1/R2/R3合并计数。原文可查[历史search_terms.md](https://github.com/lingfyou-code/AI4S-database/blob/774a78c7e4bd146056072c244a6ec048b2bed763/search_terms.md)。

## 2 三个逻辑块与字段

```text
[显式AI4S in TS]
OR [(AI方法 in TI OR AK) AND (科研任务 in AB)
    AND ((原有领域 OR 数学 OR 化工) in TS)]
OR [(SciML in TS) AND (方程或物理约束 in AB)]
整体 AND PY=(2010-2026) AND LA=(English) AND DT=(Article)
```

TI为标题，AK为作者关键词，AB为摘要；TS覆盖标题、摘要、作者关键词和Keywords Plus。字段配置旨在提高相关性，但同篇共现不能证明AI与某项科研任务存在实际执行关系，仍须筛选。领域门槛仅作用于第二块。

V3拆分为主式、数学补充式和化工补充式的方案，在词表、字段、全局限制及数据库快照相同的条件下，取并集与将新增领域直接OR并入主式在布尔逻辑上等价。拆分可以测量各领域增量，不能阻止合并结果规模扩大。本版采用一条正式完整检索式，并保留集合对照的记录方法。

## 3 词项来源分级

| 级别 | 定义 | 使用规则 |
| --- | --- | --- |
| A | 官方来源直接点名的概念，允许标准中英翻译 | 注明来源是政策正文、部署信息还是学科资助范围，不声称英文词逐字出现在中文原文 |
| B | 将官方上位概念或研究活动操作化为英文检索表达 | 说明转换关系，如传递现象到transport phenomena |
| C | 代表性文献或领域惯用语补充 | 明确这是补词，不将其写成政策直接列出的词 |

AI方法词来自方法学和论文用语；政策主要用于支持科研领域与任务范围。官方部署信息、学科资助范围、政策正文和政策解读不能相互冒充。P5、P6的年份早于V2优先选择的2024—2026年政策，系V3.1为补足数学依据而新增的回溯来源，本轮沿用；政策来源年份不改变文献检索的2010—2026年范围。

## 4 政策与官方资助依据

P1—P10的来源信息沿用附件V3.1，原记录访问日期为2026-10-14；本轮于2026-10-15重新核对P7、P9的官方页面。P7、P9无独立发布日期，按访问日期记录。本轮不声称其他来源已重新逐一核验。

| 编号 | 来源与链接 | 机构及时间 | 文件类型 | 用途 |
| --- | --- | --- | --- | --- |
| P1 | [国家重点研发计划颠覆性技术创新重点专项2025年度人工智能驱动的科学研究领域项目申报指引](https://service2.most.gov.cn/kjjh_tztg_all/20250515/5682.html) | 京津冀国家技术创新中心；国家科技管理信息系统公共服务平台公开；2025-05-13落款；2025-05-15发布 | 项目申报指引 | 原有四类方向及发现、验证、设计、仿真等任务的主要依据。 |
| P2 | [国务院关于深入实施“人工智能+”行动的意见](https://www.gov.cn/zhengce/zhengceku/202508/content_7037862.htm)；[官方转载](https://www.mee.gov.cn/zcwj/gwywj/202508/t20250827_1126207.shtml) | 国务院；国发〔2025〕11号；2025-08-21成文 | 国务院政策文件 | 支持AI驱动科学发现；生产工艺优化属于产业行动，需与科研用途区分。 |
| P3 | [Launching the Genesis Mission](https://www.whitehouse.gov/presidential-actions/2025/11/launching-the-genesis-mission/) | The White House；Executive Order 14363；2025-11-24 | 美国联邦行政令 | 原有先进制造、生物技术、关键材料、核能、量子信息及微电子方向的依据。 |
| P4 | [Energy Department Announces 26 Genesis Mission Science and Technology Challenges to Accelerate AI-Enabled American Innovation and Leadership](https://www.energy.gov/undersecretaryforscience/articles/energy-department-announces-26-genesis-mission-science-and) | U.S. Department of Energy；2026-02-12 | 官方挑战部署公告 | 对原有领域进行交叉校验；使用固定日期公告，不据此推定数学或化工被单独列为优先领域。 |
| P5 | [关于加强数学科学研究工作方案](https://www.cas.cn/zcjd/201909/t20190918_4715042.shtml) | 科技部、教育部、中科院、自然科学基金委；2019-07-12成文；国科办基〔2019〕61号 | 四部门数学研究政策 | 支持基础数学、应用数学、科学与工程计算、计算机数学等方向。其数学支撑AI的表述不能倒置为AI用于数学研究。 |
| P6 | [科技部启动“人工智能驱动的科学研究”专项部署工作](https://kw.beijing.gov.cn/xwdt/kcyx/xwdtcyfz/202303/t20230328_3817948.html) | 北京市科委、中关村管委会官网转载新华社部署报道；2023-03-28页面发布日期 | 官方部署信息，非独立政策正文 | 专项部署直接提到数学，提供将数学纳入AI4S范围的直接部署依据。 |
| P7 | [数学科学处资助范围与联系方式](https://www.nsfc.gov.cn/p1/2851/3082/3089/sxkxc.html) | 国家自然科学基金委员会；页面无独立发布日期；访问于2026-10-14 | 官方学科资助范围，非独立AI4S政策 | 提供代数几何、分析、微分方程与动力系统、统计与运筹、计算数学等词簇边界。 |
| P8 | [原材料工业数字化转型工作方案（2024—2026年）及附件1石化化工行业数字化转型实施指南](https://www.miit.gov.cn/jgsj/ycls/wjfb/art/2024/art_df31d4ff7a794bb3a29826e1bf33e3e1.html)；[官方转载](https://www.hunan.gov.cn/zqt/zcsd/202401/t20240126_32635403.html)；[完整附件PDF](https://www.hunan.gov.cn/zqt/zcsd/202401/32635403/files/5fb304e4c4434dc184ff6af1cd3fe9b6.pdf) | 工业和信息化部等九部门；2024-01-16成文；工信部联原〔2023〕270号 | 部门工作文件及行业指南 | 附件1专栏7涉及反应条件优化、催化剂结构生成及性能和反应动力学预测。仅提取与科研设计有关的内容。 |
| P9 | [化学科学五处资助范围与联系方式](https://www.nsfc.gov.cn/p1/2852/3164/3178/hxkxwc.html) | 国家自然科学基金委员会；页面无独立发布日期；访问于2026-10-14 | 官方学科资助范围，非独立政策文件 | 界定化学工程与工业化学B08，并明确AI驱动的化工研究方向；支持传递、反应、过程强化和生物制造等词簇。 |
| P10 | [石化化工行业数字化转型实施指南解读材料](https://www.miit.gov.cn/zwgk/zcjd/art/2024/art_46958ce3847a4c208a21f744c9b20331.html)；[官方转载](https://policy.mofcom.gov.cn/claw/policyInfo.shtml?id=6055) | 工信部原文；商务部全球法规网转载；2024年；商务部转载页日期2024-02-27 | 官方政策解读，非指南正文 | “三传一反”出现在该解读中；不能将其误记为已核实的指南正文措辞。 |

### 4.1 数学的依据链

P6的专项部署信息将数学纳入基础学科问题范围，直接支持数学作为AI4S研究领域。P5提供数学研究的政策基础，P7用于细分学科词簇。P5中数学支撑人工智能的内容不能反向证明人工智能用于数学研究；这一方向性证据由P6及L1、L2的实际研究补足。

### 4.2 化工的依据链

P9将化学工程与工业化学界定为物质转化中流动、传递、反应及其关系的研究，并明确人工智能驱动的化工研究方向。P8附件1的“人工智能应用场景发掘工程”见PDF第21—22页，可支持反应条件优化、催化剂结构与性能研究的科研语境。领域词据此覆盖过程、反应、分离与跨尺度工程。

P8同时包括设备维护、安全预警等产业场景，这些内容不自动满足本研究的AI4S纳入标准。“三传一反”措辞核实于P10解读材料，不将其误记为P8指南正文的直接摘录。

## 5 原有领域词

以下42项原样保留，仅为阅读分组，各组在实际领域块中均用OR连接。原有化学与材料主要覆盖分子、反应和材料对象；新增化工强化过程、装置、单元操作和跨尺度研究。二者可以重叠，不能作为互斥分类。

| 词簇 | 词项数 | 检索词 |
| --- | --- | --- |
| 原有化学与材料 | 10 | `"materials science"`；`"materials informatics"`；`"material* design"`；`"material* discover*"`；`"critical material*"`；`"chemical science*"`；`"chemical synthesis"`；`catalys*`；`"reaction predict*"`；`retrosynthes*` |
| 原有物理与量子核科学 | 9 | `"quantum physics"`；`"quantum information science"`；`"nuclear physic*"`；`"particle physics"`；`"high energy physics"`；`"fusion energy"`；`"nuclear fusion"`；`"nuclear fission"`；`"plasma physics"` |
| 原有天文与空间 | 3 | `astrophysic*`；`astronom*`；`"space science*"` |
| 原有地球与气候 | 3 | `"earth science*"`；`geoscience*`；`"climate science*"` |
| 原有生命与健康 | 9 | `biotechnology`；`genomic*`；`proteomic*`；`"protein design"`；`"protein structure"`；`"drug discover*"`；`"drug design"`；`"biomedical science*"`；`"medical science*"` |
| 原有能源系统 | 3 | `"nuclear energy"`；`"energy system*"`；`"power grid"` |
| 原有工程与先进制造 | 5 | `"advanced manufacturing"`；`semiconductor*`；`microelectronic*`；`"engineering design"`；`"complex engineering system*"` |

## 6 数学领域词（12项）

沿用R2的12项数学表达，不再调整；numerical analysis与inverse problem*为R2已恢复的两项。下表与第12节完整检索式逐项一致。词项仍可能服务其他科学工程对象，领域归属须依据研究内容判断。

| 序号 | 检索词 | 级别 | 依据 | 保留或调整理由 |
| --- | --- | --- | --- | --- |
| 1 | `mathematics` | A | P6 | 数学学科总称；亦可在短语中匹配applied mathematics、computational mathematics |
| 2 | `"mathematical science*"` | B | P5 | 保留mathematical sciences这一常用名称变体，不假设系统必然将其等同于mathematics |
| 3 | `"numerical analysis"` | B | P7；211条复核 | R2已恢复数值方法与科学计算覆盖，本轮保留 |
| 4 | `"differential equation*"` | A | P7 | 保留方程研究主线；在686条审查中对应较多数学及科学计算候选 |
| 5 | `"inverse problem*"` | B | P7；211条复核 | 恢复科学反问题与反演设计覆盖；命中不等于数学领域归属 |
| 6 | `"dynamical system*"` | A | P7 | 保留动力系统研究对象 |
| 7 | `"nonlinear dynamics"` | C | P7上位范围及既有题录 | 与dynamical system*并非字符串等价，保留已有相关记录支撑的表达 |
| 8 | `"graph theory"` | A | P7 | 保留图论这一离散数学方向 |
| 9 | `combinatorics` | A | P7 | 保留组合数学方向 |
| 10 | `"number theory"` | A | P7 | 保留数论方向；不只依据686条增量样本决定是否保留整个方向 |
| 11 | `"symbolic computation"` | C | P5上位范围及既有题录 | 保留符号计算研究路径 |
| 12 | `"computer algebra"` | C | P5上位范围及既有题录 | 计算机代数与symbolic computation用语不完全相同，保留已有数学候选支撑的表达 |

## 7 化工领域词（16项）

保留R2的11项，恢复3项、补充2项。新增表达分别服务反应器、传递、多相流及具体蒸馏对象；不同领域的词项数量不要求相同。政策提供上位范围，具体短语及本次恢复依据另列，不能写成政策逐字列出的英文检索词。

| 序号 | 检索词 | 级别 | 依据 | 保留或调整理由 |
| --- | --- | --- | --- | --- |
| 1 | `"chemical engineering"` | A | P9 | 化学工程学科总称，沿用R2 |
| 2 | `"process systems engineering"` | C | L3 | 规范的过程系统工程名称，沿用R2 |
| 3 | `"chemical process*"` | B | P8、P9 | 以chemical限定过程对象，沿用R2 |
| 4 | `"reaction engineering"` | A | P9 | 反应工程主线，沿用R2 |
| 5 | `"chemical reactor*"` | C | 反应工程领域惯用语 | 明确化学反应器对象，沿用R2 |
| 6 | `"reactor design"` | C | L3；72条中的44、49号 | 本轮恢复反应器设计与放大覆盖；也可能覆盖核工程，内容领域另行判断 |
| 7 | `"process intensification"` | A | P9 | 过程强化主线，沿用R2 |
| 8 | `"transport phenomena"` | B | P9传递研究范围；72条中的38、46、50号 | 本轮恢复传热传质和跨尺度传递研究覆盖 |
| 9 | `"multiphase flow"` | C | P9流动与传递上位范围；72条中的51、55、59号 | 本轮恢复多相流、CO2迁移及气固流规律发现覆盖 |
| 10 | `"separation process*"` | C | 化工单元操作惯用语 | 分离过程上位对象，沿用R2 |
| 11 | `"distillation column*"` | C | 既有题录及领域惯用语 | 蒸馏塔对象，沿用R2；与膜蒸馏、萃取蒸馏并列 |
| 12 | `"membrane distillation"` | C | L5、L7；72条中的2、29、60号 | 本轮补充膜蒸馏，避免仅以蒸馏塔对象覆盖 |
| 13 | `"extractive distillation"` | C | L6；72条中的6号 | 本轮补充萃取蒸馏及溶剂设计语境 |
| 14 | `"membrane separation"` | C | 化工单元操作及既有题录 | 膜分离对象，沿用R2 |
| 15 | `"flow chemistry"` | C | L4 | 自动化流动合成科研语境，沿用R2 |
| 16 | `bioprocess*` | B | P9及既有题录 | 生物生产过程，沿用R2；不假定完全覆盖biochemical engineering |

## 8 相对所附V3.1仍移出的备用词

下表列出的表达不进入本版主式。移入备用表不表示其研究方向不属于AI4S，也不表示现有上位词已经完整覆盖它们；后续应根据减少记录的内容决定是否恢复。备用词不得在不更新版本号的情况下全部加回。

| 处理 | 涉及表达 | 理由与边界 |
| --- | --- | --- |
| 数学名称去重 | `"applied mathematics"`；`"computational mathematics"` | 这两个短语本身包含mathematics；删除重复OR分支，不据此假设所有名称变体都被覆盖 |
| 数学通用方法备用词 | `"numerical linear algebra"`；`"optimization theory"` | R2已恢复numerical analysis与inverse problem*，这两项不再列为移出词。其余备用词仍需根据相关候选损失评估 |
| 数学细分方向移为备用 | `"algebraic geometry"`；`"algebraic topology"`；`"differential geometry"`；`"functional analysis"`；`"operator theory"`；`"probability theory"` | 将新增组收束到核心表达，避免单独展开完整细分目录。没有证据证明这些方向不重要或已完整覆盖 |
| 化工通用表达备用 | `"process engineering"` | 仍待进一步评估；reactor design、transport phenomena、multiphase flow已在R3恢复，不再列为备用 |
| 化工细分方向移为备用 | `"polymer processing"`；`petrochemical*`；`"biochemical engineering"`；`"electrochemical engineering"` | 减少加工/行业/交叉分支的并列展开；原有化学、材料或能源词不保证完整补回它们 |
| 蒸馏按具体对象表达 | `distillation` → `"distillation column*"`、`"membrane distillation"`、`"extractive distillation"` | R3新增后两项；裸词仍未恢复。具体短语仍不能覆盖全部物理蒸馏或科研中的知识蒸馏候选，剩余减少记录继续保留核查 |

不对全式加入`NOT "knowledge distillation"`。真实化工研究也可能使用知识蒸馏方法，直接全局排除会造成另一类漏检。

## 9 已知覆盖边界及验证方法

1. **本轮只新增5个化工组表达。** 相对R2，数学12项与其他42项原有领域词不变。原72条中五词并集本地匹配26条（P25/E0/U1）；其余46条为P31/E12/U3，继续保留核查。
2. **执行结果分版记录。** R1为11,443篇，R2为11,582篇，均为用户报告；R3待执行。仓库历史V3.2的11,684篇属于另一方案，不作为R3结果。
3. **同条件比较R3与R2。** 记录真实检索历史编号，分别运行R3 NOT R2和R2 NOT R3并导出UT、TI、AB、DE、ID。OR扩展在配置一致时应包含R2；异常时核对输入、快照与设置。
4. **审查实际新增记录。** AI是否承担目标科研任务与研究领域分别编码；化工组词命中不等于化工内容归属。当前减少池参与补词，不能作为独立验证集。
5. **任务词缺口仍存在。** 本轮不改变AB科研任务组，定理证明、猜想生成或部分化工优化任务仍可能覆盖不足。
6. **本地匹配不能替代WoS。** 规范化短语匹配按TI/AB/DE/ID分别进行，不模拟全部词形和索引行为，不外推R3新增总量、总体查准率或查全率。
7. **统计范围分别记录。** 686条历史增量池、211条R1减少池、72条R2减少池与各版全量候选量区分。2026年为部分年度；Early Access与卷期年需统一规则。

## 10 代表性文献与字段依据

| 编号 | 文献 | 用途 |
| --- | --- | --- |
| L1 | [Davies, A., et al. (2021). Advancing mathematics by guiding human intuition with AI. Nature, 600, 70–74.](https://doi.org/10.1038/s41586-021-04086-x) | 说明AI支持纯数学研究的实际路径，不把论文中所有数学术语自动加入检索式。 |
| L2 | [Romera-Paredes, B., et al. (2024). Mathematical discoveries from program search with large language models. Nature, 625, 468–475.](https://doi.org/10.1038/s41586-023-06924-6) | 用于检验数学发现的研究边界；论文在线发表于2023年，卷期年为2024年。 |
| L3 | [Schweidtmann, A. M., et al. (2021). Machine Learning in Chemical Engineering: A Perspective. Chemie Ingenieur Technik, 93(12), 2029–2039.](https://doi.org/10.1002/cite.202100083) | 核实PSE术语、反应器与蒸馏过程建模等用语；不将综述本身作为DT=Article一定能检出的哨兵论文。 |
| L4 | [Coley, C. W., et al. (2019). A robotic platform for flow synthesis of organic compounds informed by AI planning. Science, 365, eaax1566.](https://doi.org/10.1126/science.aax1566) | 补充flow chemistry与机器人流动合成的科研语境。 |
| L5 | [Machine learning and computational approaches for designing membrane distillation modules](https://doi.org/10.1016/j.seppur.2023.124627) | 来自用户72条中的2号；支持membrane distillation对象补词。 |
| L6 | [Generative discovery of safer chemical alternatives using diffusion modeling: A case study in green solvent design for cyclohexane/benzene extractive distillation](https://doi.org/10.1016/j.jes.2024.08.014) | 来自用户72条中的6号；支持extractive distillation及绿色溶剂生成语境。 |
| L7 | [Machine learning-driven multi-objective optimization of electrospun nanofibrous membranes design for membrane distillation](https://doi.org/10.1016/j.watres.2026.126093) | 来自用户72条中的60号；支持膜设计、实验验证及膜蒸馏对象。 |

新增L5—L7的题名、DOI及对象依据来自用户提供的题录与摘要；本轮不声称重新取得其全文。政策与官方来源沿用既有记录和访问日期。

**F1**：[Clarivate官方Web of Science Starter API客户端字段说明](https://github.com/clarivate/wosstarter_python_client/blob/master/README.md)。其TS条目明确列出Title、Abstract、Author keywords及Keywords Plus。原帮助页已转向新帮助中心，故保留当前可核实的官方说明链接。

## 11 方法部分可用表述

本研究采用显式AI4S表述、AI方法与科研任务及科学领域的交叉约束、Scientific Machine Learning与方程或物理约束三条互补检索路径。科研领域依据官方政策、学科资助范围和代表性文献构建。在减少记录的标题摘要审查基础上，R2恢复数学表达numerical analysis与inverse problem*；本轮R3进一步恢复reactor design、transport phenomena和multiphase flow，并补充membrane distillation与extractive distillation。其他领域词、AI方法词、科研任务词、字段与全局限制不变。恢复或补充表达用于改善候选覆盖，不作为内容领域标签。R3实际命中数与同条件差集仍待执行和核验。

## 12 完整可复制检索式

下方为当前V3.1-R3完整式，与压缩包根目录AI4S_V3_1_R3_完整检索式.txt一致。整段复制到WoS Core Collection高级检索，执行后记录实际索引、筛选设置、日期与命中量。R3尚无实测总量。

```text
(
TS=(
"AI for science"
OR "artificial intelligence for science"
OR "AI4S"
OR "AI4Science"
OR "AI for scientific discover*"
OR "artificial intelligence for scientific discover*"
OR "AI-driven scientific discover*"
OR "AI-enabled scientific discover*"
OR "AI-accelerated scientific discover*"
OR "machine learning for science"
OR "self-driving laborator*"
OR "autonomous laborator*"
OR "robotic laborator*"
OR "closed-loop laborator*"
)

OR

(
(
TI=(
"artificial intelligence"
OR "machine learning"
OR "deep learning"
OR "neural network*"
OR "graph neural network*"
OR GNN*
OR "foundation model*"
OR "generative model*"
OR "large language model*"
OR "Bayesian optimization"
OR "active learning"
OR "reinforcement learning"
OR "diffusion model*"
)

OR

AK=(
"artificial intelligence"
OR "machine learning"
OR "deep learning"
OR "neural network*"
OR "graph neural network*"
OR GNN*
OR "foundation model*"
OR "generative model*"
OR "large language model*"
OR "Bayesian optimization"
OR "active learning"
OR "reinforcement learning"
OR "diffusion model*"
)
)

AND

AB=(
"scientific discover*"
OR "hypothesis generat*"
OR "causal infer*"
OR "equation discover*"
OR "physical law discover*"
OR "governing equation*"
OR "mechanism discover*"
OR "mechanism infer*"
OR "symbolic regression"
OR "structure-function*"
OR "material* discover*"
OR "drug discover*"
OR "virtual screen*"
OR "high-throughput screen*"
OR "inverse design"
OR "de novo design"
OR "molecular design"
OR "protein design"
OR "catalyst design"
OR "molecule generat*"
OR "protein structure predict*"
OR "molecular propert* predict*"
OR "material* propert* predict*"
OR "reaction predict*"
OR retrosynthes*
OR "experiment* design"
OR "experiment* planning"
OR "autonomous experiment*"
OR "closed-loop experiment*"
OR "self-driving laborator*"
OR "robotic laborator*"
OR "design space explor*"
OR "design optim*"
)

AND

TS=(
"materials science"
OR "materials informatics"
OR "material* design"
OR "material* discover*"
OR "critical material*"

OR "chemical science*"
OR "chemical synthesis"
OR catalys*
OR "reaction predict*"
OR retrosynthes*

OR "quantum physics"
OR "quantum information science"
OR "nuclear physic*"
OR "particle physics"
OR "high energy physics"
OR "fusion energy"
OR "nuclear fusion"
OR "nuclear fission"
OR "plasma physics"

OR astrophysic*
OR astronom*
OR "space science*"

OR "earth science*"
OR geoscience*
OR "climate science*"

OR biotechnology
OR genomic*
OR proteomic*
OR "protein design"
OR "protein structure"
OR "drug discover*"
OR "drug design"
OR "biomedical science*"
OR "medical science*"

OR "nuclear energy"
OR "energy system*"
OR "power grid"

OR "advanced manufacturing"
OR semiconductor*
OR microelectronic*
OR "engineering design"
OR "complex engineering system*"

OR mathematics
OR "mathematical science*"
OR "numerical analysis"
OR "differential equation*"
OR "inverse problem*"
OR "dynamical system*"
OR "nonlinear dynamics"
OR "graph theory"
OR combinatorics
OR "number theory"
OR "symbolic computation"
OR "computer algebra"

OR "chemical engineering"
OR "process systems engineering"
OR "chemical process*"
OR "reaction engineering"
OR "chemical reactor*"
OR "reactor design"
OR "process intensification"
OR "transport phenomena"
OR "multiphase flow"
OR "separation process*"
OR "distillation column*"
OR "membrane distillation"
OR "extractive distillation"
OR "membrane separation"
OR "flow chemistry"
OR bioprocess*
)
)

OR

(
TS=(
"scientific machine learning"
OR "physics-informed machine learning"
OR "physics informed machine learning"
OR "physics-informed neural network*"
OR "physics informed neural network*"
OR PINN*
OR "neural operator*"
)

AND

AB=(
"partial differential equation*"
OR PDE*
OR "governing equation*"
OR "physical law*"
OR "conservation law*"
OR "boundary condition*"
)
)
)

AND PY=(2010-2026)
AND LA=(English)
AND DT=(Article)
```

## 13 R1减少记录复核

此前提供的211条R1减少记录均有唯一UT与DOI，并全部对应原686条。标题摘要复核处置为P183、E18、U10；不能把全部减少记录当作误检。R2首先恢复两个数学表达，用户报告11,582篇。211条复核报告与逐条材料作为历史证据保留在压缩包“复核211篇”。

## 14 实际72条复核与本轮落实

用户提供的实际72条，UT与此前从211条预测的剩余集合一致；对应TI/AB/DE/ID/PY/SO/DI/WC均相同，沿用标题摘要处置P56/E12/U4。三项恢复表达在此池匹配20条（P19/E0/U1），再补充两项蒸馏表达后五词并集26条（P25/E0/U1）。17、34号仅在Keywords Plus匹配具体蒸馏短语，不据此断言其内容主题为该蒸馏类型。

本轮已将上述5项写入R3，数学和其他原有领域词不再调整。26条仅是此减少池的本地匹配；剩余46条含P31/E12/U3，不能自动删除。裸词distillation在原72条对应P20/E12/U1，需要结合科研内容判断；不增加全局NOT knowledge distillation。
