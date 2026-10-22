# 模型辅助核心样本与DOI全文核验进度

> 历史阶段说明：下文数量、待办与上传状态按当时日期理解。当前使用v3（核心9,470篇、待补证20篇），六个完整包已于2026-10-22发布。[当前状态](../../README.md) · [全过程](../../search_results.md) · [下载入口](../../data/packages/README.md)
更新日期：2026-10-21

## 1. 已完成的模型辅助筛选
输入为领域筛选后10,189条候选。依据本地交付包summary.json及分类CSV核对，处置如下：

| 处置 | 条数 |
| --- | ---: |
| 核心分析样本v1（模型辅助） | 8,247 |
| 拓展参考，不计核心 | 513 |
| 证据不足，暂不纳入 | 1,412 |
| 非目标或非原创排除 | 13 |
| 重复合并或撤稿旧版移除 | 4 |
| 合计 | 10,189 |

定向二次推断覆盖5,812条，使用同一DeBERTa模型，不构成独立验证；未训练或微调。4条质量移除包括3条重复/版本合并及1条撤稿旧版。分析归年采用EA与PY中较早的已记录年份，855条与原PY不同；原PY/EA保留。原始文件和v1导出不覆盖。本说明未重新验证全部8,247条的科学相关性，也未将模型分数视为准确率。17个核心WoS TXT及完整审计表已通过数据包交付，本文档链接不代表已将完整数据包上传仓库。

## 2. DOI核验范围与证据层级
待核验1,412条中1,405条有DOI、7条缺DOI。DOI用于匹配出版社和开放仓储版本，不能仅凭DOI、开放获取标记或搜索摘要认定已经阅读全文。

本次完成2条正文相关章节的AI辅助核查、1条出版社文献类型核验；另1条全文访问失败继续待定。未通读两篇全文的每一节，未进行人工双人复核。其余1,408条本轮尚未完成DOI来源核验。网页正文通过检索工具读取；未调用本地MinerU（当前命令不可用），没有将PDF上传第三方解析服务。

## 3. 逐条证据与处置
### 10.1038/s41598-022-23431-2
题名：Uncertainty-aware mixed-variable machine learning for materials design。
来源：https://www.nature.com/articles/s41598-022-23431-2
实际阅读：出版社网页摘要、Introduction、Uncertainty-aware machine learning中的方法说明，网页读取行67—126。后续翻页遇到登录重定向，PMC镜像遇到验证码；不声称结果部分已完整读取。
判断：建议从证据不足转入核心。对象为材料设计；采用随机森林Lolo与潜变量高斯过程LVGP开展混合变量贝叶斯优化比较。正文明确说明自建比较研究及材料设计任务，不应仅因出现survey或方法回顾就按纯综述处理。
证据定位：Introduction末段的研究贡献；Uncertainty quantification in mixed-variable machine learning；Related comparative studies。结论限于筛选相关性，不评价其全部结果可靠性。

### 10.1038/s41598-023-36336-5
题名：Improving deep learning model performance under parametric constraints for materials informatics applications。
来源：https://www.nature.com/articles/s41598-023-36336-5
实际阅读：出版社网页Introduction及Results下Datasets、Model architecture design，网页行66—104。后续翻页受登录重定向影响，不声称已精读全部结果。
判断：建议从证据不足转入核心。对象为材料性质；BRNet/BNet直接预测形成能等材料性质，正文列明六个DFT或实验性质数据集、81:9:10训练验证测试划分和网络比较设计。属于有具体科学预测任务的原创计算研究。
证据定位：Results—Datasets；Results—Model architecture design。无需把方法创新与科学任务割裂。

### 10.1002/aenm.202503356
题名：Machine Learning for Accelerating Energy Materials Discovery: Bridging Quantum Accuracy with Computational Efficiency。
来源：https://advanced.onlinelibrary.wiley.com/doi/abs/10.1002/aenm.202503356
实际阅读：出版社文献类型与摘要页面，未取得全文。
判断：按研究者排除观点文章的既定要求，建议排除。出版社明确标注Perspective。此项为出版类型核验，不计作全文核查；不因WoS导出为Article就自动纳入。

### 10.1016/j.ssi.2025.117054
题名：Materials discovery through interpretation: An application to proton-conducting oxides。
来源：https://www.sciencedirect.com/science/article/pii/S0167273825002735
实际获取：出版社检索结果和高校作者机构页面；全文返回403。
判断：继续待核验。出版社称Research article，但摘要自称perspective并提出MDI框架，需要正文区分新实施研究与对既有案例的总结；不能仅依据摘要中的成果措辞直接纳入。
后续：查找作者稿或机构仓储全文，核对数据来源、实施方法及案例是否为本篇新增结果。

## 4. 数量口径与下一步
以上为独立增量核验记录，尚未回写v1核心CSV/TXT，故已交付v1仍为8,247条。若落实2条转入和1条排除，则工作台账为核心8,249、拓展513、证据不足1,409、内容排除14、质量移除4，合计10,189；该算术衔接不表示新版WoS文件已生成。
继续按DOI查找可获取全文，以方法、数据和结果中的实际任务证据裁定；无全文或证据仍不足的保留待核验。本文仅公开自写方法、汇总及核验理由，不转载论文全文或原始完整摘要。

