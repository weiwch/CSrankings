# 哈尔滨工程大学 Google Scholar 逐人核查与本地交接

**状态：未完成。** 2026-11-09 的云端核查访问 Google Scholar 个人页时收到 429 或访问失败，无法直接确认档案内容。以下 4 个账号均是**待直验候选**；其余 31 人未发现可确认的账号，不等于没有账号。请在有正常访问条件的本地继续逐人核查。

- PR 工作分支：[`weiwch/CSrankings:heu-faculty-provisional`](https://github.com/weiwch/CSrankings/tree/heu-faculty-provisional)；交接时的 HEAD 是 `c7d4e48f3263268301f3d6b48321c067f9e88ea1`。工作分支有 27 条新增、1 条既有教师机构更新，共 28 人。
- 本交接文件单独放在 `heu-scholar-audit-handoff` 分支，**不要将此文件或核查结果文件合并进上游 PR 分支**。上游只允许修改规定的 CSV 文件。
- 学院名单中的 7 位仍在 DBLP 消歧页的教师，也应核查其 Scholar，但暂不加入 PR。郑香平为预聘，不加入。
- 当前分支中 26 处 `NOSCHOLARPAGE` 是临时占位符，不代表查证无主页。庞志奇的候选 ID 是临时线索；於志文沿用上游 ID，均待直接核验。

## 本地 Codex 执行任务

1. 先获取本文件和 fork 当前状态。若已经有本地仓库，保留未提交修改；必要时使用独立 worktree。先 `fetch` 并核对两个远端分支当前 HEAD；分支发生变化时在最新状态上处理，不 reset 他人的工作，不强推。
2. 逐项检索下方全部 **35 人**（28 人在工作分支、7 人仅为候选）。对搜索结果打开 Google Scholar 个人主页，记录当前显示的姓名、单位/经验证的邮箱域、研究方向以及匹配论文。搜索姓名时去掉 DBLP 数字后缀，因为后缀不是作者真实姓名的一部分。
3. 为每个档案建立能区分同名者的证据链：以学校个人主页/可信学校资料为一端，核对至少一篇可独立确认作者及单位的论文标题、合作者或学校邮箱为另一端。尽量记录两个独立证据地址。仅凭相同姓名、相同单位、DBLP 指向的链接、研究方向或 ORCID 不能单独断言正确；旧单位可配合履历判断。对于混名或作者本人资料不足的条目，保持未定。
4. 每人填写状态：`VERIFIED`（已直接查看公开 Scholar 页面且身份有交叉证据）、`AUTHOR_CONFIRMED_NO_PUBLIC_PROFILE`（有本人明确说明并记录来源）、`NOT_FOUND_AFTER_SEARCH`（充分检索仍未发现，不能据此断言不存在）、`AMBIGUOUS` 或 `BLOCKED`。记录链接、证据和匹配论文。Google Scholar 页面出现限流、验证码或登录墙时停下并如实记录，不绕过限制；不索要用户的密码或 cookie。
5. 在 **28 位 PR 工作分支人员**中，仅将 `VERIFIED` 的有效 ID 填入 CSV 的 `scholarid` 第四列；`AUTHOR_CONFIRMED_NO_PUBLIC_PROFILE` 才视为确证无公开档案。暂时无法确认的条目须在结果表中明确列出，保留原字段作工作占位，**不能因搜不到而认定没有主页**，也不可将 `PENDING` 等非规定值写入 CSV。任何不匹配的旧 ID 先标疑问并保留证据，再谨慎修正。
6. 只更改已核实的 Scholar 字段；不要改姓名、DBLP 数字后缀、机构、个人主页或 ORCID，不添加 7 位消歧人员。保留原有排序、字段和换行，不要用 Excel。确认 diff 中仅有预期行的第 4 列改变。
7. 在本交接分支另存 `HEU_GOOGLE_SCHOLAR_RESULTS.tsv`，对每位提供一行，列名为：`chinese_name, dblp_name, scope, status, scholar_id, scholar_url, scholar_affiliation, matched_paper, independent_evidence_urls, notes`（实际用 tab 分隔）。保存可公开的资料，不保存账号凭据、cookie、浏览器截图或个人隐私。`scope` 使用 `pr_branch` / `excluded_dblp_disambiguation`。
8. 将核查表提交并推送到 `heu-scholar-audit-handoff`；如有已核实的 CSV 更新，另提交并推送到 `heu-faculty-provisional`。仅允许快进推送。GitHub 操作优先使用 GitHub 插件。输出两条分支最新提交、已核实 ID 与未解决人员清单。**不要创建或提交上游 PR**，直到其余资格、DBLP 混名及占位问题另行处理。

维护者规则：<https://github.com/emeryberger/CSrankings/blob/gh-pages/CONTRIBUTING.md>；学校收录批准：<https://github.com/emeryberger/CSrankings/issues/15445>。

## 28 位工作分支候选

ORCID 是既有工作稿字段，不表示本轮逐人复核成功；“未发现”只表示云端现阶段尚无可靠候选。教师姓名链接指向学校主页或学校名单；DBLP 列为目前工作稿中的精确名称及链接。

| 教师 | DBLP 作者页 | 工作稿 ORCID | Scholar 线索与当前限制 | 既有身份注意事项 |
| --- | --- | --- | --- | --- |
| [陈睿](https://cstc.hrbeu.edu.cn/3662/list.htm) | [Rui Chen 0012](https://dblp.org/pid/02/1003-12.html) | `0000-0002-3853-6308` | [`ngVttWUAAAAJ`](https://scholar.google.com/citations?user=ngVttWUAAAAJ)：DBLP 所链候选；作者页混有其他机构同名研究者，勿仅凭 DBLP 链接确认 | 普通页；混入他校论文；无个人主页，使用学院名录占位 |
| [冯光升](https://faculty.hrbeu.edu.cn/fengguangsheng/zh_CN/index.htm) | [Guangsheng Feng](https://dblp.org/pid/43/8404.html) | `0000-0001-7192-1622` | 云端未找到可验证的 ID；继续检索 | 两个 ORCID；另一个可能也是本人 |
| [韩启龙](https://faculty.hrbeu.edu.cn/hanqilong/zh_CN/index.htm) | [Qilong Han](https://dblp.org/pid/84/2613.html) | `0000-0002-5185-8387` | 云端未找到可验证的 ID；继续检索 | 两个 ORCID；另一个可能也是本人 |
| [黄少滨](https://faculty.hrbeu.edu.cn/huangshaobin/zh_CN/index.htm) | [Shaobin Huang](https://dblp.org/pid/98/6530.html) | `0000-0002-7895-7326` | 云端未找到可验证的 ID；继续检索 | ORCID 由 DBLP 根据元数据推断 |
| [江俊慧](https://faculty.hrbeu.edu.cn/jiangjunhui/zh_CN/index.htm) | [Junhui Jiang 0001](https://dblp.org/pid/125/0816-1.html) | `0000-0002-7667-4760` | 云端未找到可验证的 ID；继续检索 | 学院博导名单；2026目录前四方向未列 |
| [李思照](https://faculty.hrbeu.edu.cn/lisizhao/zh_CN/index.htm) | [Sizhao Li](https://dblp.org/pid/154/5806.html) | `0000-0002-6557-262X` | 云端未找到可验证的 ID；继续检索 | 普通页；已确认混入浙江大学同名作者论文 |
| [李伟](https://faculty.hrbeu.edu.cn/liwei/zh_CN/index.htm) | [Wei Li 0109](https://dblp.org/pid/64/6025-109.html) | `0000-0003-0998-5435` | [`I3QXhTAAAAAJ`](https://scholar.google.com/citations?user=I3QXhTAAAAAJ)：DBLP 所链候选；作者页存在多 ORCID，须对照论文和本人身份 | 多个 ORCID；疑似论文亦误入 Wei Wayne Li 页 |
| [刘刚](https://faculty.hrbeu.edu.cn/liugang) | [Gang Liu 0021](https://dblp.org/pid/37/2109-21.html) | `0000-0002-7032-8429` | 云端未找到可验证的 ID；继续检索 | 2026/081200；个人页列2027博士招生 |
| [卢丹](https://faculty.hrbeu.edu.cn/ludan/zh_CN/index.htm) | [Dan Lu 0004](https://dblp.org/pid/36/7513-4.html) | `0000-0001-6410-8422` | 云端未找到可验证的 ID；继续检索 | 学院名录及主页抬头为博导；简介仅写硕导 |
| [吕宏武](https://faculty.hrbeu.edu.cn/lvhongwu) | [Hongwu Lv](https://dblp.org/pid/87/8407.html) | `0000-0002-1917-3978` | 云端未找到可验证的 ID；继续检索 | 普通页；疑混入北理工同名作者 |
| [吕继光](https://faculty.hrbeu.edu.cn/lvjiguang/zh_CN/index/72441/list/index.htm) | [Jiguang Lv](https://dblp.org/pid/151/5907.html) | `0000-0001-5502-7217` | 云端未找到可验证的 ID；继续检索 | 2026/081200；论文及ORCID支持 |
| [苘大鹏](https://faculty.hrbeu.edu.cn/mandapeng/zh_CN/index.htm) | [Dapeng Man](https://dblp.org/pid/46/2089.html) | `0000-0003-1177-3693` | 云端未找到可验证的 ID；继续检索 | 2026/081200；Wiley论文支持ORCID |
| [史长亭](https://faculty.hrbeu.edu.cn/shichangting/zh_CN/index.htm) | [Changting Shi](https://dblp.org/pid/29/4496.html) | `0000-0002-3912-0099` | 云端未找到可验证的 ID；继续检索 | ORCID 由 DBLP 根据元数据推断 |
| [田乔](https://faculty.hrbeu.edu.cn/tianqiao/zh_CN/index.htm) | [Qiao Tian 0002](https://dblp.org/pid/206/9465-2.html) | `0000-0001-8177-7724` | 云端未找到可验证的 ID；继续检索 | 学院名录及主页抬头为博导；简介仅写硕导 |
| [王红滨](https://faculty.hrbeu.edu.cn/wanghongbin/zh_CN/index.htm) | [Hongbin Wang 0001](https://dblp.org/pid/98/3467-1.html) | `0000-0002-5925-4924` | 云端未找到可验证的 ID；继续检索 | 2026/081200；个人页列2027博士招生 |
| [王巍](https://faculty.hrbeu.edu.cn/wangwei123) | [Wei Wang 0076](https://dblp.org/pid/35/7092-76.html) | `0000-0002-9768-3121` | 云端未找到可验证的 ID；继续检索 | 普通页；含两个 ORCID 和自动化学院成果，需区分 |
| [王兴梅](https://faculty.hrbeu.edu.cn/wangxingmei/zh_CN/index.htm) | [Xingmei Wang 0002](https://dblp.org/pid/34/486-2.html) | `0000-0002-0281-0336` | 云端未找到可验证的 ID；继续检索 | 2026/081200；出版方论文支持 ORCID |
| [吴伟宁](https://faculty.hrbeu.edu.cn/wuweining/zh_CN/index.htm) | [Weining Wu](https://dblp.org/pid/132/5623.html) | `0000-0002-3410-4460` | 云端未找到可验证的 ID；继续检索 | ORCID 由 DBLP 根据元数据推断 |
| [吴艳霞](https://faculty.hrbeu.edu.cn/wuyanxia/zh_CN/index.htm) | [Yanxia Wu 0001](https://dblp.org/pid/88/5327-1.html) | `0000-0001-8384-9234` | 云端未找到可验证的 ID；继续检索 | 普通页；部分相关论文可能留在未分配页 |
| [谢晓芹](https://faculty.hrbeu.edu.cn/xiexiaoqin/zh_CN/index.htm) | [Xiaoqin Xie](https://dblp.org/pid/90/1767.html) | `0000-0002-9981-9483` | 云端未找到可验证的 ID；继续检索 | 普通页；另一作者的 ORCID 疑为重庆工商大学同名者 |
| [玄世昌](https://faculty.hrbeu.edu.cn/xuanshichang) | [Shichang Xuan](https://dblp.org/pid/206/1731.html) | `0000-0003-0332-0686` | 云端未找到可验证的 ID；继续检索 | 2026/081200；论文与学院主页支持 |
| [杨武](https://faculty.hrbeu.edu.cn/yangwu) | [Wu Yang 0001](https://dblp.org/pid/56/2037-1.html) | `0000-0001-5985-7648` | 云端未找到可验证的 ID；继续检索 | 2026/081200；论文与学院主页支持 |
| [印桂生](https://faculty.hrbeu.edu.cn/yinguisheng/zh_CN/index.htm) | [Guisheng Yin](https://dblp.org/pid/25/2295.html) | `0000-0003-0924-4741` | 云端未找到可验证的 ID；继续检索 | 2025/081200；2026目录前四方向未列 |
| [於志文](https://faculty.hrbeu.edu.cn/yuzhiwen/zh_CN/index.htm) | [Zhiwen Yu 0001](https://dblp.org/pid/z/YuZhiwen.html) | `0000-0002-9905-3238` | [`H0qmM6gAAAAJ`](https://scholar.google.com/citations?user=H0qmM6gAAAAJ)：上游既有值且 DBLP 链到该 ID；学校主页提及 Scholar 引用，云端未直验该主页 | 更新现有NWPU记录；保留现有ORCID与Scholar ID |
| [张越](https://faculty.hrbeu.edu.cn/zhangyue/zh_CN/index.htm) | [Yue Zhang 0015](https://dblp.org/pid/47/722-15.html) | `0000-0002-4515-8931` | 云端未找到可验证的 ID；继续检索 | 用户确认；2026/081200；论文支持 ORCID |
| [郑丽颖](https://faculty.hrbeu.edu.cn/zhengliying/zh_CN/index.htm) | [Liying Zheng](https://dblp.org/pid/48/6193.html) | `0000-0002-1596-0309` | 云端未找到可验证的 ID；继续检索 | 普通页；另一 ORCID 属于美国 NIOSH 作者 |
| [周连科](https://faculty.hrbeu.edu.cn/zhoulianke/zh_CN/index.htm) | [Lianke Zhou](https://dblp.org/pid/202/1194.html) | `0000-0002-3601-9286` | 云端未找到可验证的 ID；继续检索 | 学院博导名单；2026目录前四方向未列 |
| [庞志奇](https://faculty.hrbeu.edu.cn/pangzhiqi/zh_CN/index.htm) | [Zhiqi Pang](https://dblp.org/pid/276/4841.html) | `0000-0003-0940-3351` | [`UM-V0YsAAAAJ`](https://scholar.google.com/citations?user=UM-V0YsAAAAJ)：第三方论文作者数据对应 DBLP PID 276/4841；云端未直验该主页 | 用户确认；现行主页列青年博导；Scholar ID UM-V0YsAAAAJ 待直验 |

## 7 位待 DBLP 消歧的候选

下表可以核查 Scholar 来辅助后续消歧，但查到 Scholar **不构成**现在把消歧页加入 CSRankings 的理由。保留候选状态，不将这些人加入本次 CSV 编辑。

| 教师 | DBLP 消歧页 | 辅助交叉核对 |
| --- | --- | --- |
| [冯晓宁](https://faculty.hrbeu.edu.cn/fengxiaoning/zh_CN/index.htm) | [Xiaoning Feng](https://dblp.org/pid/59/2775.html) | [SAND 论文](https://pmc.ncbi.nlm.nih.gov/articles/PMC10969041/)；Scholar 暂无已验证 ID |
| [李丽洁](https://faculty.hrbeu.edu.cn/lilijie/zh_CN/index.htm) | [Lijie Li](https://dblp.org/pid/95/748.html) | [学校所列 WFF 论文](https://faculty.hrbeu.edu.cn/lilijie/zh_CN/lwcg/70396/content/1832554.htm)；Scholar 暂无已验证 ID |
| [李熔盛](https://faculty.hrbeu.edu.cn/lirongsheng1/zh_CN/index.htm) | [Rongsheng Li](https://dblp.org/pid/147/5827.html) | [NAACL 2024 论文](https://aclanthology.org/2024.naacl-long.149.pdf)；Scholar 暂无已验证 ID |
| [刘海波](https://faculty.hrbeu.edu.cn/liuhaibo/zh_CN/index.htm) | [Haibo Liu](https://dblp.org/pid/83/1694.html) | [ICMR 2025 论文](https://doi.org/10.1145/3731715.3733400)；Scholar 暂无已验证 ID |
| [唐滨](https://faculty.hrbeu.edu.cn/TangBin/zh_CN/index.htm) | [Bin Tang](https://dblp.org/pid/77/5837.html) | [学校成果页](https://faculty.hrbeu.edu.cn/TangBin/zh_CN/lwcg/8540/list/index.htm)；另有 Tang Bin 署名，须区分；Scholar 暂无已验证 ID |
| [徐丽](https://faculty.hrbeu.edu.cn/xuli/zh_CN/index.htm) | [Li Xu](https://dblp.org/pid/85/2168.html) | [PLOS 论文](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1014051)；Scholar 暂无已验证 ID |
| [庄园](https://faculty.hrbeu.edu.cn/zhuangyuan/zh_CN/index.htm) | [Yuan Zhuang](https://dblp.org/pid/15/6840.html) | [AAAI 2025 MTVHunter](https://ojs.aaai.org/index.php/AAAI/article/view/33664)；Scholar 暂无已验证 ID |

## 4 个候选的溯源

- 於志文：CSRankings 原有条目及 [DBLP 作者页](https://dblp.org/pid/z/YuZhiwen.html)的个人 Google Scholar 链接一致；其[学校主页](https://faculty.hrbeu.edu.cn/yuzhiwen/zh_CN/index.htm)提到 Google Scholar 引用。由于云端无法查看 Scholar 档案内容，仍要直验。
- 庞志奇：一份公开的 [NeurIPS 论文作者数据](https://github.com/Jin1Xu/Med-Multimodal-Paper-List/blob/aaedff03692ca734b7d1ce8b523ff76f042d55e4/Mm_classification_papers/nips2025_filtered_for_mm_classification.json)将 `UM-V0YsAAAAJ` 与姓名及 DBLP PID `276/4841` 并列，这是第三方汇编，不等于已直验 Scholar 页面。
- 李伟：候选取自 [Wei Li 0109 的 DBLP 页面](https://dblp.org/pid/64/6025-109.html)中 **visit / Google Scholar profile** 链接，而非通用搜索链接。多 ORCID 及同名情况需要逐项比对。
- 陈睿：候选取自 [Rui Chen 0012 的 DBLP 页面](https://dblp.org/pid/02/1003-12.html)中 **visit / Google Scholar profile** 链接；该 DBLP 页存在其他机构同名作者论文，所以不能把链接自动认定为哈工程陈睿。

**重要：**上述 Scholar 查找结果不解决学院 0812 独立博导资格、主聘单位、ORCID 准确性、DBLP 论文混名或个人主页缺失等其他待办。候选总数不是最终可提交人数。
