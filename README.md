***

# 💎 闪记卡 Pro+ (Flashcard Pro+)

> **极简、高效、沉浸式的本地化单词记忆引擎**  
> 基于浏览器的 SRS（间隔重复）记忆卡片应用。无需注册，无需后端，数据完全存储在本地（LocalStorage），保护您的隐私。

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![License](https://img.shields.io/badge/License-Proprietary-red?style=flat-square)

## ✨ 核心特性

*   🧠 **SRS 间隔重复算法**：基于 6 个熟悉度阶段（Lv.0 - Lv.5），自动计算下次复习时间（从 1 天到 30 天不等），科学对抗遗忘曲线。
*   🔄 **双模式无缝切换**：「📖 识记模式」看词回忆释义，「✍️ 拼写模式」看释义默写单词，通过优雅滑块一键切换。
*   ⏱️ **极限施压记忆**：支持 3s/5s 倒计时限制，逼迫大脑建立快速神经反射。
*   📅 **可视化打卡日历**：记录每日学习轨迹，支持查看历史错词、一键打印错词本，甚至支持“时光倒流”进行**补卡**操作。
*   🎨 **沉浸式自定义**：支持上传自定义背景图、调节卡片透明度、自定义 TTS 语音的语速与音调。
*   📊 **全功能词库管理**：支持单元格直接编辑（Contenteditable）、批量删除、分类筛选、以及完整的 CSV 导入/导出。

---

## 🚀 快速开始

1.  **克隆或下载**本仓库到本地。
2.  双击打开 `index.html`（推荐使用 Chrome、Edge 或 Safari 等现代浏览器以获得最佳的 TTS 语音合成体验）。
3.  进入 **导入** 标签页，上传您的 CSV 词库文件，即可开始学习。

---

## 📥 CSV 词库导入指南

本应用支持通过 CSV 文件批量导入词库。为了确保数据完美解析，请确保您的 CSV 文件包含以下表头（字段顺序可打乱，但**名称必须一致**，建议首行包含表头）。

### 📑 字段说明

| 字段名 | 含义 | 是否必填 | 说明 |
| :--- | :--- | :---: | :--- |
| `word` | 单词/词组 | **是** | 核心词汇，应用将以此作为唯一标识（去重依据）。 |
| `part_of_speech` | 词性 | 否 | 如 `n.`, `v.`, `adj.`，在卡片中会以斜体标签显示。 |
| `meaning` | 释义 | **是** | 英文释义或中文核心意思。 |
| `example` | 例句 | 否 | 包含该单词的例句，点击“记不记得”后会自动朗读此句。 |
| `translation` | 翻译 | 否 | 例句的中文翻译，以高亮引用块形式展示。 |
| `pronunciation` | 音标 | 否 | 单词音标（如 `/ɪɡˈzæmpl/`），作为数据保留。 |
| `category` | 分类 | 否 | 词库分类（如 `CET4`, `托福`, `雅思`, `日常口语`），用于筛选学习范围。 |
| `notes` | 备注 | 否 | 词根词缀记忆法、易混淆词等扩展笔记。 |
| `level` | 难度等级 | 否 | 数字（如 1-5），用于标记单词难度。 |

### 💡 标准 CSV 示例

您可以将以下内容复制并保存为 `my_vocab.csv`（注意使用 **UTF-8 编码** 保存，以防中文乱码），然后导入应用中进行测试：

```csv
word,part_of_speech,meaning,example,translation,pronunciation,category,notes,level
ephemeral,adj.,lasting for a very short time,"Fame in the world of pop music is often ephemeral.",流行音乐界的名声往往是昙花一现的。,/ɪˈfemərəl/,GRE/TOEFL,词根：epi(在...上) + hemer(一天) + al -> 只有一天的,4
ubiquitous,adj.,present, appearing, or found everywhere,"Smartphones have become ubiquitous in modern society.",智能手机在现代社会已变得无处不在。,/juːˈbɪkwɪtəs/,GRE/TOEFL,同义词：omnipresent,3
serendipity,n.,the occurrence of events by chance in a happy way,"Finding this rare book in a small village shop was pure serendipity.",在一个小村庄的店里找到这本绝版书纯属机缘巧合。,/ˌserənˈdɪpəti/,日常口语,源自斯里兰卡旧称“锡兰”(Serendip)的童话,2
pragmatic,adj.,"dealing with things sensibly and realistically","We need a pragmatic approach to solve this budget issue.",我们需要一种务实的方法来解决这个预算问题。,/præɡˈmætɪk/,商务英语,反义词：idealistic (理想主义的),3
eloquent,adj.,fluent or persuasive in speaking or writing,"She gave an eloquent speech that moved the entire audience.",她发表了一场雄辩的演讲，感动了全场观众。,/ˈeləkwənt/,雅思/托福,词根：e(出) + loqu(说) + ent -> 能说会道的,4
```

*注：如果您使用 Excel 编辑，请在“另存为”时选择 `CSV UTF-8 (逗号分隔) (*.csv)` 格式。*

---

## 🛠️ 使用技巧与进阶

1.  **错词自动循环**：当一组（20个）卡片复习完毕后，系统会自动将您标记为“忘了”或“拼写错误”的词汇加入下一轮队列，确保弱点被彻底攻克。
2.  **键盘快捷键**：在拼写模式下，输入框会自动聚焦，您可以直接敲击键盘输入并按 `Enter` 键触发核对。
3.  **日历数据同步**：在“打卡日历”页面，您可以导出 JSON 格式的日历与错词数据，并在另一台设备上导入，实现跨设备的学习进度同步。
4.  **本地打印排版**：词库列表和错词本均内置了 `@media print` 样式，点击打印按钮会自动隐藏无关 UI，生成干净的 A4 纸质排版。

---

## ⚙️ 技术栈

*   **纯前端架构**：HTML5 + CSS3 + Vanilla JavaScript (ES6 Classes)。
*   **数据持久化**：`localStorage`（无需数据库，零服务器成本）。
*   **第三方依赖**：仅依赖 [PapaParse](https://www.papaparse.com/) 用于健壮的 CSV 文件解析。
*   **语音合成**：基于浏览器原生 `Web Speech API` (SpeechSynthesis)。

---

## 📜 版权与许可

本项目由 **Ch'ien Chou** 独立开发并保留所有权利。
*(Copyright © Ch'ien Chou. All Rights Reserved.)*

未经授权，请勿用于商业用途。欢迎个人学习者 Fork、Star 及交流探讨！

---
*如果这个项目对您的语言学习有所帮助，请不吝点亮 ⭐️ Star！*
