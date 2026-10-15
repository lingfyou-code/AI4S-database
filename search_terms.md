# AI4S 检索词与政策来源说明

**版本：V3.2　文档日期：2026-10-14　数据库：Web of Science Core Collection**

## 1 修订范围与基线

本轮在V3.1基础上，依据686条新增题录审查修订数学和化工领域表达，形成V3.2。操作基线仍是用户提供的`检索式.txt`；原有42个领域词保持原样。三块OR结构、TI/AK方法词、AB科研任务词、全部字段与PY=(2010-2026)、LA=(English)、DT=(Article)限制不变。本轮没有增加全局NOT、期刊或WC限制。

V3.1曾新增数学22项、化工19项。V3.2改为明确词与邻近语境组合，按数学10组、化工12组说明，不能把组数当作与旧41项直接可比的词项数。V3.1完整存档式保留在第13节，便于同日对照。

V2 Word附录与当前TXT基线并非相同字段版本：前者部分使用TI/AB/AK并集，当前基线使用TS；科研任务组也有差异。V3.2沿用实际TXT基线，不将两者混用。“相对V2新增686条”依据用户说明，尚未取得完整旧集合与同日历史独立复现差集。

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

AI方法词来自方法学和论文用语；政策主要用于支持科研领域与任务范围。官方部署信息、学科资助范围、政策正文和政策解读不能相互冒充。P5、P6的年份早于V2优先选择的2024—2026年政策，系本轮为补足数学依据而明确新增的回溯来源；政策来源年份不改变文献检索的2010—2026年范围。

## 4 政策与官方资助依据

全部来源访问日期为2026-10-14。P7、P9无独立发布日期，按访问日期记录。

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

## 6 数学领域修订词

以10组表达说明修订，不将“组数”等同于独立词项数。原学科名沿用P5—P7（数学）或P8—P10（化工）依据；本轮新增对象词及邻近规则为审查与文献补充C级，不声称这些检索规则由政策逐字列出。

| 组 | 词簇 | 表达方式 | 审查依据与用途 |
| --- | --- | --- | --- |
| 1 | 明确数学学科 | 明确词/短语 | 保留明确学科名；去掉单独mathematics造成的数学教育误检。 |
| 2 | 数学发现及精确对象 | 明确词/短语 | 依据331、601、630、662等保留数学发现、整数序列与代数关系；属于文献补充C级。 |
| 3 | 符号与计算机数学 | 明确词/短语 | 保留计算机数学词，AI是否实际使用仍须核验。 |
| 4 | 方程与动力系统 | 明确词/短语 | 保留方程、动力系统和离散微分算子等数学对象；研究贡献须人工核验。 |
| 5 | 方程缩略语求解语境 | NEAR/10语境 | 仅在学习、求解或识别语境补入PDE/ODE，覆盖只写缩略语的科学计算研究。 |
| 6 | 理论分支与数学成果 | NEAR/10语境 | 降低图论、拓扑、几何仅作为其他学科建模工具的混入。 |
| 7 | 泛函分析数学语境 | NEAR/10语境 | 避免functional analysis被解释为生物功能分析。 |
| 8 | 数值分析方法语境 | NEAR/10语境 | 避免仅写对工程对象做numerical analysis即进入数学扩展。 |
| 9 | 反问题方法研究 | NEAR/10语境 | 降低一般逆向设计仅提反问题的混入，同时保留贝叶斯、方程及代理模型反演方法。 |
| 10 | 统计推断方法研究 | NEAR/10语境 | 保留因果森林及聚类数据统计方法；教育应用数据不自动排除统计方法研究。 |

下面是第二逻辑块TS领域组内的数学模块，不能脱离完整检索式单独代替正式方案。

```text
"mathematical science*" OR "pure mathematics" OR "applied mathematics" OR "computational mathematics" OR "numerical linear algebra" OR "number theory" OR "algebraic geometry" OR "mathematical statistics" OR "statistical theory"
OR "mathematical discover*" OR "mathematical conjectur*" OR "mathematical theorem*" OR "mathematical proof*" OR "integer sequence*" OR "Diophantine equation*" OR "recurrence relation*" OR "Groebner basis" OR "Grobner basis"
OR "symbolic computation" OR "computer algebra"
OR "differential equation*" OR "dynamical system*" OR "nonlinear dynamics" OR "differential operator*"
OR ((PDE* OR ODE*) NEAR/10 (solv* OR solution* OR solver* OR learn* OR discover* OR identif* OR "numerical method*" OR discretiz* OR discretis*))
OR (("graph theory" OR combinatorics OR "algebraic topology" OR "differential geometry" OR "operator theory" OR "probability theory" OR "optimization theory") NEAR/10 (theorem* OR conjectur* OR proof* OR "mathematical problem*" OR "mathematical discover*" OR "mathematical theor*" OR bound*))
OR (("functional analysis") NEAR/10 (Banach OR Hilbert OR Sobolev OR "function space*" OR "operator algebra*" OR "spectral theor*" OR "bounded operator*"))
OR (("numerical analysis") NEAR/10 (convergence OR stability OR consisten* OR "error estimat*" OR "error analys*" OR "numerical method*" OR "numerical scheme*" OR discretiz* OR discretis* OR "approximation theor*"))
OR (("inverse problem*") NEAR/10 (regulariz* OR regularis* OR "ill posed" OR illposed OR "inverse operator*" OR "numerical method*" OR "numerical analys*" OR identifiab* OR "inverse solver*" OR Bayesian OR "Gaussian process*" OR "reduced order" OR "surrogate model*" OR "automatic differentiation" OR PDE* OR ODE*))
OR (("statistical infer*" OR "causal infer*" OR "causal forest*") NEAR/10 ("statistical method*" OR "statistical theor*" OR "simulation stud*" OR "asymptotic theor*" OR "treatment effect*" OR "causal effect*" OR "multivariate outcome*" OR cluster* OR multilevel OR propensity))
```

## 7 化工领域修订词

以12组表达说明修订，不将“组数”等同于独立词项数。原学科名沿用P5—P7（数学）或P8—P10（化工）依据；本轮新增对象词及邻近规则为审查与文献补充C级，不声称这些检索规则由政策逐字列出。

| 组 | 词簇 | 表达方式 | 审查依据与用途 |
| --- | --- | --- | --- |
| 1 | 明确化工学科与过程 | 明确词/短语 | 保留明确学科、过程和装置词；bioprocess*在本子集24/27条判为化工，保留高效入口，生物功能和教学/监控仍需核验。 |
| 2 | 反应与反应器对象 | 明确词/短语 | 用反应工程对象补充原reactor design，降低核反应器设计混入。 |
| 3 | 反应动力学语境 | NEAR/5语境 | 覆盖实际动力学识别与反应参数研究。 |
| 4 | 连续流反应语境 | NEAR/5语境 | 覆盖632等连续流光化学实验平台，不使用裸continuous flow。 |
| 5 | 反应器语境 | NEAR/5语境 | 不再单独使用reactor design；用反应或停留时间等过程语境限定。 |
| 6 | 化工蒸馏语境 | NEAR/5语境 | 去掉裸distillation，正向限定实际蒸馏单元，不全局NOT knowledge distillation。 |
| 7 | 具体分离单元 | 明确词/短语 | 补充实际分离与混合单元，保留膜蒸馏、结晶、微混合器和溶剂设计文献。 |
| 8 | 轻烃分离对象 | NEAR/5语境 | 补充以物质名称描述的轻烃分离，避免只认gas separation短语。 |
| 9 | 分离过程物质语境 | NEAR/5语境 | 降低物理微结构phase separation等混入。 |
| 10 | 石化过程语境 | NEAR/5语境 | 避免仅研究石化工人健康即计入化工。 |
| 11 | 传递与多相流化工语境 | NEAR/10语境 | 将通用传递和多相流限定到化工单元或过程；该语境仍需内容核验。 |
| 12 | 生物生产过程 | 明确词/短语 | 强化生物制造与发酵生产，避免一般生命活动bioprocesses。 |

下面是第二逻辑块TS领域组内的化工模块，不能脱离完整检索式单独代替正式方案。

```text
"chemical engineering" OR "process engineering" OR "process systems engineering" OR "chemical process*" OR "reaction engineering" OR "chemical reactor*" OR "process intensification" OR "membrane separation" OR "polymer processing" OR "flow chemistry" OR bioprocess* OR "biochemical engineering" OR "electrochemical engineering"
OR "reaction kinetic*" OR "chemical kinetic*" OR "electrochemical reactor*" OR "photochemical reactor*" OR photoreactor* OR bioreactor* OR "oscillatory baffled reactor*" OR "continuous flow reactor*"
OR ((kinetic*) NEAR/5 (reaction* OR catalytic OR enzymatic OR polymeriz* OR polymeris* OR pyrolysis OR saponif*))
OR (("continuous flow" OR microfluidic*) NEAR/5 (reactor* OR reaction* OR chemical OR synthesis OR photochemical OR saponif*))
OR ((reactor*) NEAR/5 (chemical OR catalytic OR electrochemical OR biochemical OR photochemical OR "reaction kinetic*" OR "residence time*" OR saponif*))
OR ((distill*) NEAR/5 (column* OR tray* OR reboil* OR reflux OR azeotrop* OR extractive OR reactive OR vacuum OR "vapor liquid" OR "vapour liquid" OR membrane* OR desalination OR entrainer* OR fractionat* OR purif* OR feedstock* OR "heat pump*" OR solvent*))
OR "solvent extract*" OR "liquid liquid extract*" OR "gas separation*" OR "electrostatic separation" OR "adsorption desalination" OR "crystallization process*" OR "crystallisation process*" OR "pressure swing adsorpt*" OR "temperature swing adsorpt*" OR pervaporat* OR "membrane distillation" OR micromixer*
OR ((separat*) NEAR/5 (ethane OR ethylene OR propane OR propylene OR olefin*))
OR (("separation process*") NEAR/5 (chemical OR gas OR liquid OR membrane* OR adsorpt* OR chromatograph* OR solvent* OR "mass transfer"))
OR ((petrochemical*) NEAR/5 (process* OR reactor* OR refin* OR plant* OR cataly* OR separat* OR feedstock*))
OR (("transport phenomena" OR "multiphase flow" OR "heat transfer" OR "mass transfer") NEAR/10 ("chemical process*" OR reactor* OR catalyst* OR distillation OR membrane* OR "heat exchang*" OR evaporator* OR crystalliz* OR crystallis* OR drying OR leach* OR "fluidized bed*"))
OR "bioprocess engineer*" OR "bioprocess optim*" OR biomanufactur* OR fermentat* OR "cell cultivation" OR "microbial production" OR "biopharmaceutical process*" OR "cell therapy process*" OR "anaerobic digestion"
```

## 8 相对V3.1的针对性调整

| 涉及表达 | V3.2处理 | 根据与取舍 |
| --- | --- | --- |
| 单独mathematics | 用明确学科名、数学发现与具体数学对象替代 | 减少数学教育数据和背景性提及；保留实际统计方法研究 |
| inverse problem* | 与正则化、病态性、数值方法、贝叶斯反演、方程或代理模型等NEAR/10 | 减少光学、材料等研究只把逆问题当工具的混入；仍可能跨领域 |
| numerical analysis | 与收敛、稳定性、误差、离散或数值方法等NEAR/10 | 避免任意工程数值分析自动归入数学 |
| functional analysis | 与Banach、Hilbert、Sobolev、函数空间或算子等NEAR/10 | 避免生物功能分析同义误检 |
| 图论、拓扑、几何等通用理论词 | 与定理、猜想、证明、数学问题或界等NEAR/10 | 保留理论方向，降低仅用作表示工具的混入；需检查未匹配论文 |
| differential equation*、dynamical system*、nonlinear dynamics | 保留；补离散微分算子与有求解语境的PDE/ODE | 回查显示普遍加严会漏掉较多科学计算候选，采用较宽的对象入口 |
| distillation | distill*与塔、塔盘、回流、再沸器、共沸、萃取、膜等NEAR/5 | 正向识别化工蒸馏；不全局NOT knowledge distillation |
| reactor design | 用明确反应器对象及reactor*与化学、催化、电化学、动力学或停留时间NEAR/5替代 | 减少核反应器等混入；未给化工语境的真实反应器论文可能漏匹配 |
| separation process* | 加物质和单元操作语境；补萃取、吸附、结晶、膜蒸馏和轻烃分离 | 减少其他学科的泛化分离描述，保留具体化工研究对象 |
| petrochemical* | 与过程、精炼、反应器、催化、分离或原料NEAR/5 | 减少石化工人健康研究；仍须人工核验 |
| transport phenomena、multiphase flow | 与反应器、膜、换热器、蒸发、结晶、干燥、浸出等NEAR/10 | 将传递过程连接到化工对象，部分通用流体/传热候选可能漏匹配 |
| bioprocess* | 保留并补充发酵、生物制造和明确生产过程 | 原子集中27条命中记录有24条判为化工；一般生物活动、综述及监控内容继续人工核验 |

## 9 回查结果、覆盖边界及验证方法

对用户提供的686条V3.1新增子集，按TI、AB、DE、ID分别进行简化词项与邻近匹配：原新增领域组匹配686条，V3.2新增领域组匹配492条。先前初筛的326条目标领域候选中匹配294条（90.2%），另32条未匹配；其他科学工程领域134条、建议排除23条不再匹配。匹配记录中的目标领域候选占比从47.5%变为59.8%。这是同一已审子集的回查，不是新的WoS结果总量、全文确认后的精确率或总体查全率。

| 先前初筛类别 | V3.1子集条数 | V3.2领域组匹配 | 领域组未匹配 |
| --- | ---: | ---: | ---: |
| 数学及科学计算 | 184 | 167 | 17 |
| 化工 | 134 | 121 | 13 |
| 数学与化工交叉 | 8 | 6 | 2 |
| 其他科学工程领域 | 283 | 149 | 134 |
| 建议排除 | 54 | 31 | 23 |
| 需全文核实 | 23 | 18 | 5 |
| 合计 | 686 | 492 | 194 |

本地匹配方法：TI、AB、DE、ID分别分词，不跨字段计算邻近；忽略大小写，标准化拉丁字母与标点；带*词采用词尾截断，多词短语按连续词序匹配；NEAR/x按两短语最近端点间的间隔词数近似判定。未复现WoS词形还原、全部词干扩展、索引分词及系统更新。本地旧领域组能重匹配全部686条，便于同口径比较，但不能据此宣称完全复现WoS。

该子集已用于调整词表，因此回查不是独立验证集，可能存在对已见样本过度适配。新补充词可能引入这686条之外的文献，本地回查不能估计其规模或相关性。单人标题摘要初筛也不是最终纳入标准。

领域词新增不等于任务覆盖完整。原AB任务词未增加theorem proving、conjecture generation、process optimization等表达，摘要仅写这些任务的论文仍可能漏检。新增数学对象词在TS侧不自动解决AB任务缺口。AI词中的foundation model、diffusion model、neural network仍有非AI词义；Article标记也不能排除所有实际综述。例行监控是否属于科学研究须看具体科研贡献。

WoS官方帮助支持NEAR/x与括号组合；本式NEAR两侧仅用词项或OR，不在NEAR操作数内部嵌入AND。NEAR/5、NEAR/10是本轮审查后选择的检索参数，不是官方学科边界。官方资料：[Search Operators](https://webofscience.zendesk.com/hc/en-us/articles/20016122409105-Search-Operators)、[Search Rules](https://webofscience.zendesk.com/hc/en-us/articles/25350084904721-Search-Rules)，本轮访问于2026-10-14。引号、通配符和词形处理会影响实际匹配，应记录Exact Search状态。

同日、同索引库和同一限制分别运行Q0（基线）、Q1（V3.1）、Q2（V3.2），记录实际集合编号。核查Q2 NOT Q1新引入文献、Q1 NOT Q2移出文献、Q2 NOT Q0净新增；Q0 NOT Q2在同快照与同限制下应为0，否则检查输入与配置。优先核验本轮32条目标候选未匹配记录，并抽查新引入集合；已收到用户说明对应V3.2的结果页截图：SCI-EXPANDED命中11,684条；实际执行全文与限制仍待核对，不能据此报告查准率。

## 10 代表性文献与字段依据

| 编号 | 文献 | 用途 |
| --- | --- | --- |
| L1 | [Davies, A., et al. (2021). Advancing mathematics by guiding human intuition with AI. Nature, 600, 70–74.](https://doi.org/10.1038/s41586-021-04086-x) | 说明AI支持纯数学研究的实际路径，不把论文中所有数学术语自动加入检索式。 |
| L2 | [Romera-Paredes, B., et al. (2024). Mathematical discoveries from program search with large language models. Nature, 625, 468–475.](https://doi.org/10.1038/s41586-023-06924-6) | 用于检验数学发现的研究边界；论文在线发表于2023年，卷期年为2024年。 |
| L3 | [Schweidtmann, A. M., et al. (2021). Machine Learning in Chemical Engineering: A Perspective. Chemie Ingenieur Technik, 93(12), 2029–2039.](https://doi.org/10.1002/cite.202100083) | 核实PSE术语、反应器与蒸馏过程建模等用语；不将综述本身作为DT=Article一定能检出的哨兵论文。 |
| L4 | [Coley, C. W., et al. (2019). A robotic platform for flow synthesis of organic compounds informed by AI planning. Science, 365, eaax1566.](https://doi.org/10.1126/science.aax1566) | 补充flow chemistry与机器人流动合成的科研语境。 |

**F1**：[Clarivate官方Web of Science Starter API客户端字段说明](https://github.com/clarivate/wosstarter_python_client/blob/master/README.md)。其TS条目明确列出Title、Abstract、Author keywords及Keywords Plus。原帮助页已转向新帮助中心，故保留当前可核实的官方说明链接。


### 10.1 本轮审查记录依据（文献补充C级）

以下取自用户导出的原始题录与摘要。编号对应既有686篇审查表；词项补充并非政策直接摘录。

| 审查编号 | 原始题名 | 导出DOI | UT |
| --- | --- | --- | --- |
| 331 | Mathematical discoveries from program search with large language models | 10.1038/s41586-023-06924-6 | WOS:001157281900001 |
| 601 | Discovery of Exact Equations for Integer Sequences | 10.3390/math12233745 | WOS:001376398100001 |
| 630 | Discovery of Exact Equations via Computing the Gröbner Basis | 10.1007/s10994-026-07112-z | WOS:001826395500001 |
| 662 | Discovering Infinite Recursive Conjectures Through Genetic Programming | 10.1109/TEVC.2025.3611312 | WOS:001784195800024 |
| 20 | Machine learning-based predictive control using on-line model linearization: Application to an experimental electrochemical reactor | 10.1016/j.cherd.2023.08.017 | WOS:001068762600001 |
| 55 | Computational fluid dynamic enabled design optimisation of miniaturised continuous oscillatory baffled reactors in chemical processing | 10.1080/10618562.2019.1683169 | WOS:000493234000001 |
| 224 | Accelerating In Silico Discovery of Metal-Organic Frameworks for Ethane/Ethylene and Propane/Propylene Separation: A Synergistic Approach Integrating Molecular Simulation, Machine Learning, and Active Learning | 10.1021/acsami.3c14505 | WOS:001161280100001 |
| 445 | Learning mesh-free discrete differential operators with self-supervised graph neural networks | 10.1016/j.cma.2026.119388 | WOS:001877842400001 |
| 451 | Intelligent design of distillation columns integrating detailed tray geometry using data-driven model | 10.1016/j.cherd.2026.02.031 | WOS:001701342400001 |
| 467 | Machine learning and genetic algorithm as tools for single and multi-objective shape optimization of micromixers with Cantor fractal structure | 10.1007/s43153-023-00414-y | WOS:001103079900002 |
| 632 | Kinetic study in an automatic continuous-flow photochemical platform with machine learning | 10.1002/aic.18102 | WOS:000973620100001 |
| 659 | Machine learning-driven multi-objective optimization of electrospun nanofibrous membranes design for membrane distillation | 10.1016/j.watres.2026.126093 | WOS:001769037400001 |
| 666 | Integrated design of solvent-antisolvent mixtures and crystallization processes powered by machine learning | 10.1016/j.compchemeng.2025.109272 | WOS:001543678600001 |

## 11 方法部分可用表述

本研究采用显式AI4S、方法—任务—领域共现、机理约束科学机器学习三条检索路径。在V3.1数学与化工扩展子集686条的标题摘要初筛基础上，仅修订第二逻辑块的领域表达，形成V3.2。修订对逆问题、数值分析、泛函分析和蒸馏等歧义表达增加语境条件，并补充数学发现、具体反应器及分离对象；保留微分方程、动力系统和生物过程等有效入口。原有领域42项、AI方法词、摘要任务词、字段及全局限制保持一致。子集本地回查匹配492条，其中294条属于先前初筛的目标领域候选；该回查用于诊断词表取舍，不作为独立查准率或总体查全率证据。随后收到用户说明为V3.2的结果页截图，SCI-EXPANDED界面命中11,684条；实际新增、移出及净新增集合仍需相同快照和设置下对照确定。

## 12 V3.2完整可复制检索式

在Web of Science Core Collection的高级检索/字段查询中复制以下完整代码块；用户随后提供了对应V3.2的结果页截图，显示SCI-EXPANDED命中11,684条；以下为本地存档完整式，实际执行全文仍待核对。

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

OR (
"mathematical science*" OR "pure mathematics" OR "applied mathematics" OR "computational mathematics" OR "numerical linear algebra" OR "number theory" OR "algebraic geometry" OR "mathematical statistics" OR "statistical theory"
OR "mathematical discover*" OR "mathematical conjectur*" OR "mathematical theorem*" OR "mathematical proof*" OR "integer sequence*" OR "Diophantine equation*" OR "recurrence relation*" OR "Groebner basis" OR "Grobner basis"
OR "symbolic computation" OR "computer algebra"
OR "differential equation*" OR "dynamical system*" OR "nonlinear dynamics" OR "differential operator*"
OR ((PDE* OR ODE*) NEAR/10 (solv* OR solution* OR solver* OR learn* OR discover* OR identif* OR "numerical method*" OR discretiz* OR discretis*))
OR (("graph theory" OR combinatorics OR "algebraic topology" OR "differential geometry" OR "operator theory" OR "probability theory" OR "optimization theory") NEAR/10 (theorem* OR conjectur* OR proof* OR "mathematical problem*" OR "mathematical discover*" OR "mathematical theor*" OR bound*))
OR (("functional analysis") NEAR/10 (Banach OR Hilbert OR Sobolev OR "function space*" OR "operator algebra*" OR "spectral theor*" OR "bounded operator*"))
OR (("numerical analysis") NEAR/10 (convergence OR stability OR consisten* OR "error estimat*" OR "error analys*" OR "numerical method*" OR "numerical scheme*" OR discretiz* OR discretis* OR "approximation theor*"))
OR (("inverse problem*") NEAR/10 (regulariz* OR regularis* OR "ill posed" OR illposed OR "inverse operator*" OR "numerical method*" OR "numerical analys*" OR identifiab* OR "inverse solver*" OR Bayesian OR "Gaussian process*" OR "reduced order" OR "surrogate model*" OR "automatic differentiation" OR PDE* OR ODE*))
OR (("statistical infer*" OR "causal infer*" OR "causal forest*") NEAR/10 ("statistical method*" OR "statistical theor*" OR "simulation stud*" OR "asymptotic theor*" OR "treatment effect*" OR "causal effect*" OR "multivariate outcome*" OR cluster* OR multilevel OR propensity))
)

OR (
"chemical engineering" OR "process engineering" OR "process systems engineering" OR "chemical process*" OR "reaction engineering" OR "chemical reactor*" OR "process intensification" OR "membrane separation" OR "polymer processing" OR "flow chemistry" OR bioprocess* OR "biochemical engineering" OR "electrochemical engineering"
OR "reaction kinetic*" OR "chemical kinetic*" OR "electrochemical reactor*" OR "photochemical reactor*" OR photoreactor* OR bioreactor* OR "oscillatory baffled reactor*" OR "continuous flow reactor*"
OR ((kinetic*) NEAR/5 (reaction* OR catalytic OR enzymatic OR polymeriz* OR polymeris* OR pyrolysis OR saponif*))
OR (("continuous flow" OR microfluidic*) NEAR/5 (reactor* OR reaction* OR chemical OR synthesis OR photochemical OR saponif*))
OR ((reactor*) NEAR/5 (chemical OR catalytic OR electrochemical OR biochemical OR photochemical OR "reaction kinetic*" OR "residence time*" OR saponif*))
OR ((distill*) NEAR/5 (column* OR tray* OR reboil* OR reflux OR azeotrop* OR extractive OR reactive OR vacuum OR "vapor liquid" OR "vapour liquid" OR membrane* OR desalination OR entrainer* OR fractionat* OR purif* OR feedstock* OR "heat pump*" OR solvent*))
OR "solvent extract*" OR "liquid liquid extract*" OR "gas separation*" OR "electrostatic separation" OR "adsorption desalination" OR "crystallization process*" OR "crystallisation process*" OR "pressure swing adsorpt*" OR "temperature swing adsorpt*" OR pervaporat* OR "membrane distillation" OR micromixer*
OR ((separat*) NEAR/5 (ethane OR ethylene OR propane OR propylene OR olefin*))
OR (("separation process*") NEAR/5 (chemical OR gas OR liquid OR membrane* OR adsorpt* OR chromatograph* OR solvent* OR "mass transfer"))
OR ((petrochemical*) NEAR/5 (process* OR reactor* OR refin* OR plant* OR cataly* OR separat* OR feedstock*))
OR (("transport phenomena" OR "multiphase flow" OR "heat transfer" OR "mass transfer") NEAR/10 ("chemical process*" OR reactor* OR catalyst* OR distillation OR membrane* OR "heat exchang*" OR evaporator* OR crystalliz* OR crystallis* OR drying OR leach* OR "fluidized bed*"))
OR "bioprocess engineer*" OR "bioprocess optim*" OR biomanufactur* OR fermentat* OR "cell cultivation" OR "microbial production" OR "biopharmaceutical process*" OR "cell therapy process*" OR "anaerobic digestion"
)
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


## 13 V3.1完整存档式（历史对照）

V3.1截图总量与686条审查均对应此历史版本，不归入V3.2实际结果。

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
OR "applied mathematics"
OR "computational mathematics"
OR "numerical analysis"
OR "numerical linear algebra"
OR "differential equation*"
OR "inverse problem*"
OR "dynamical system*"
OR "nonlinear dynamics"
OR "graph theory"
OR combinatorics
OR "number theory"
OR "algebraic geometry"
OR "algebraic topology"
OR "differential geometry"
OR "functional analysis"
OR "operator theory"
OR "probability theory"
OR "optimization theory"
OR "symbolic computation"
OR "computer algebra"
OR "chemical engineering"
OR "process engineering"
OR "process systems engineering"
OR "chemical process*"
OR "reaction engineering"
OR "chemical reactor*"
OR "reactor design"
OR "process intensification"
OR "separation process*"
OR distillation
OR "membrane separation"
OR "polymer processing"
OR petrochemical*
OR "flow chemistry"
OR "transport phenomena"
OR "multiphase flow"
OR bioprocess*
OR "biochemical engineering"
OR "electrochemical engineering"
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
