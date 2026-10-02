# 代表与前沿研究：推荐、搜索与个性化

核验截止2026-10-02。9项一手论文来源覆盖经典目标、序列与图模型、生成推荐和作者近期研究。它们不是完整研究版图；“前沿”指近期可核查的问题与路线，不等于已验证的最新最优模型。

| 工作 | 日期及可核状态 | 为何读、怎样读 | 一手来源 |
|---|---|---|---|
| BPR: Bayesian Personalized Ranking from Implicit Feedback | 原工作UAI 2009；arXiv上传2012年5月，不能混成2012新方法 | 理解隐式反馈下正负排序目标；重点检查未观测作为负例的假设 | [原作者arXiv论文](https://arxiv.org/abs/1205.2618) |
| SASRec / Self-Attentive Sequential Recommendation | 2018-08-20首版；arXiv注明ICDM 2018长论文录用 | 学会行为序列、位置编码与因果注意力；注意预测时只能看到过去 | [arXiv](https://arxiv.org/abs/1808.09781) |
| LightGCN | 2020-02-06首版；2020-07-07 v4；SIGIR 2020正式工作 | 理解用户物品二部图邻居聚合及层间融合；简化结构可作为有力基线 | [arXiv及录用记录](https://arxiv.org/abs/2002.02126) |
| TIGER / Recommender Systems with Generative Retrieval | 2023-05-08首版；NeurIPS 2023正式工作 | 将语义ID与序列生成相连。明确输出为物品标识，检查新物品泛化与合法ID限制 | [arXiv](https://arxiv.org/abs/2305.05065) |
| HSTU / Actions Speak Louder than Words | ICML 2024正式论文，PMLR 235 | 面向高基数、非平稳流式行为，把推荐视作序列转导；辨别参数规模、稠密计算与部署预算 | [PMLR正式页](https://proceedings.mlr.press/v235/zhai24a.html) |
| Agent4Ranking | 2023-12-24首版；本次独立核实预印本；TOIS正式发表状态尚未独立确认，按预印本引用 | 不同用户表达怎样改变排序？角色改写、共享/专用专家和一致性训练有何互补？ | [arXiv](https://arxiv.org/abs/2312.15450) |
| CAGED / Causality-aware Graph Aggregation Weight Estimator | 2025-10-06预印本；所读PDF及学校出版页支持CIKM 2025，DOI 10.1145/3746252.3761155 | 把图权重与历史交互分布联系起来。关注因果假设以及冷门与热门结果的权衡 | [arXiv](https://arxiv.org/abs/2510.04502)、[CityU出版记录](https://scholars.cityu.edu.hk/en/publications/causality-aware-graph-aggregation-weight-estimator-for-popularity/) |
| GloRank / From Local Indices to Global Identifiers | 2026-04-28首版；预印本；未独立确认正式出版，按预印本引用 | 全局语义ID改善局部位置语义漂移，结合监督初始化、奖励后训练与受约束输出 | [arXiv](https://arxiv.org/abs/2604.25291) |
| MuSeR | 2026-09-20首版；预印本；ICDM 2026状态待独立确认 | 分层压缩和多兴趣实现工业长历史召回。分别看公开短序列评测与私有长序列证据 | [arXiv](https://arxiv.org/abs/2609.23677) |

## 不要混淆三种“生成”

TIGER以语义ID生成召回结果；GloRank在给定候选集合内生成重排列表；HSTU研究更一般的工业行为序列转导。它们的输入、输出、评价和部署约束不同，不能把各自报告的收益直接相加或按百分比排座次。

## 方法之间怎样连接

离线语义增强与用户画像可补充协同信息；语义ID、解码与后训练连接生成式召回和重排；跨域、多场景模型需要统一评价来识别负迁移；查询改写与记忆检索则连接用户表达和个性化结果。这些连接按研究问题建立，不能假定不同方法的收益可以直接叠加。

通用搜索智能体的工具使用和动作决策可以提供方法启发，但其问答成绩不能替代推荐或个性化搜索指标。

## 值得持续跟踪的问题

| 研究问题 | 现有切入 | 还缺什么证据 |
|---|---|---|
| ID协同与语义泛化怎样平衡 | 双分支、分层语义标识、语义增强 | 按冷启动、头尾、领域分别评价，避免平均提升掩盖损失 |
| 长历史怎样在预算内保留低频兴趣 | 池化、多兴趣、缓存、稀疏或状态空间 | 真正长序列公共测试、等预算对照、兴趣漂移诊断 |
| 生成列表怎样优化整体效用 | 全局动作空间、奖励后训练、集合生成 | 奖励和人类满意差距、训练稳定性、候选合法性 |
| 个性化是否真正保留用户意图 | 用户语料对齐、画像、记忆检索 | 真实用户证据、意图忠实性、群体差异与隐私 |

后续结论均需重新核验版本与出版状态。大模型用户模拟、个人记忆和公平性讨论，不能只凭单个离线分数认定实际用户收益。
