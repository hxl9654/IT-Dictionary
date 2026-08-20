# IT Vocabulary Dataset / IT词汇数据集

[English](#english) | [中文](#中文)

---

<a id="english"></a>
## English

This repository contains a structured vocabulary dataset extracted from technical documentation and enriched using Large Language Models (LLMs). The dataset is provided in `JSONL` format, making it easy to stream and process for various NLP tasks, vocabulary building applications, or educational purposes.

### 📦 Dataset Contents

The repository includes the following main files:
- `CloudWords.jsonl`: Single words extracted from cloud computing and technical contexts.
- `CloudPhrases.jsonl`: Common phrases and collocations from cloud computing documents.
- `Punctuation.jsonl`: Punctuation-related terms and their usage.
- `test.jsonl`: A sample subset for testing purposes.

### 📊 Data Format

Data is stored in [JSON Lines (JSONL)](https://jsonlines.org/) format. Each line is a valid JSON object representing a term. 

#### Schema 

| Field | Type | Description |
|---|---|---|
| `term` | String | The actual word or phrase. |
| `term_type` | String | Type of the term (e.g., `word`, `phrase`). |
| `count` | Integer | Frequency count of the term in the source technical documents. |
| `pos_list` | Array[String] | List of Parts of Speech (e.g., `noun`, `verb`). |
| `phonetics` | Array[String] | Phonetic transcriptions. |
| `collocations` | Array[String] | Common collocations and related expressions. |
| `daily` | Object | Meanings and examples for daily/general usage. |
| `tech` | Object | Meanings and examples specific to technical/IT contexts. |

#### Example Entry

```json
{
  "term": "ABAC",
  "term_type": "word",
  "count": 536,
  "pos_list": ["noun"],
  "phonetics": [],
  "collocations": ["ABAC policy", "ABAC model", "ABAC system"],
  "daily": {},
  "tech": {
    "noun": [
      {
        "meaning": "基于属性的访问控制",
        "gloss": "Attribute-Based Access Control, a security model",
        "example": "ABAC uses user attributes to grant access.",
        "example_zh": "ABAC 使用用户属性来授予访问权限。"
      }
    ]
  }
}
```

### 🤖 Data Generation & Sourcing

1. **Extraction**: Words and phrases were statistically extracted from various technical documents, cloud computing manuals, and software documentation. 
2. **Enrichment**: The definitions (gloss), bilingual examples (English/Chinese), and contextual categorizations (`tech` vs. `daily`) were generated and structured using Large Language Models (LLMs).

> **⚠️ Disclaimer**: The definitions, examples, and contextual tags in this dataset were generated programmatically using Large Language Models (LLMs) to handle the vast amount of terms, **and have not undergone a comprehensive human review**. While efforts have been made to ensure quality, LLMs can sometimes hallucinate or produce nuanced inaccuracies, especially with highly specialized IT jargon. This dataset is provided "as-is" for educational and research purposes. We highly encourage community contributions—if you spot any errors, hallucinations, or have better context examples, please open an Issue or submit a Pull Request!

### 🚀 Usage (Python)

```python
import json

with open('CloudWords.jsonl', 'r', encoding='utf-8') as f:
    for line in f:
        data = json.loads(line)
        print(data['term'], data['count'])
```

### 📄 License

[IT Dictionary](https://github.com/hxl9654/IT-Dictionary) © 2026 by [Xiaonglong He](https://github.com/hxl9654/) is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)

---

<a id="中文"></a>
## 中文

本仓库包含一个从技术文档中提取，并由大语言模型（LLM）进行内容补充和丰富结构化的词汇数据集。数据集采用 `JSONL` 格式提供，非常适合用于 NLP 任务的数据流处理、词汇学习应用开发或教育用途。

### 📦 数据集内容

本仓库包含以下核心文件：
- `CloudWords.jsonl`：从云计算及相关技术语境中提取的独立单词。
- `CloudPhrases.jsonl`：从云计算文档中提取的常见短语和词语搭配。
- `Punctuation.jsonl`：与标点符号相关的术语及其用法。
- `test.jsonl`：用于测试和预览的小型样本子集。

### 📊 数据格式

数据以 [JSON Lines (JSONL)](https://jsonlines.org/) 格式存储。每一行都是一个代表该词条的合法 JSON 对象。

#### 字段说明 (Schema)

| 字段名 | 类型 | 说明 |
|---|---|---|
| `term` | String | 具体的单词或短语。 |
| `term_type` | String | 词条类型（例如 `word` 或 `phrase`）。 |
| `count` | Integer | 该词条在源技术文档中出现的频率统计。 |
| `pos_list` | Array[String] | 词性列表（例如 `noun` 名词, `verb` 动词）。 |
| `phonetics` | Array[String] | 音标。 |
| `collocations` | Array[String] | 常见的词语搭配及相关表达。 |
| `daily` | Object | 在日常/通用语境下的释义和例句。 |
| `tech` | Object | 在技术/IT语境下的专门释义和例句。 |

#### 数据示例

```json
{
  "term": "ABAC",
  "term_type": "word",
  "count": 536,
  "pos_list": ["noun"],
  "phonetics": [],
  "collocations": ["ABAC policy", "ABAC model", "ABAC system"],
  "daily": {},
  "tech": {
    "noun": [
      {
        "meaning": "基于属性的访问控制",
        "gloss": "Attribute-Based Access Control, a security model",
        "example": "ABAC uses user attributes to grant access.",
        "example_zh": "ABAC 使用用户属性来授予访问权限。"
      }
    ]
  }
}
```

### 🤖 数据生成与来源

1. **提取阶段**：通过统计学方法，从各种技术文档中提取了高频词汇和短语。
2. **丰富阶段**：词条的精确定义 (gloss)、中英双语例句以及语境分类（`tech` 与 `daily` 区分）均由大语言模型（LLM）生成并进行结构化处理。

> **⚠️ 免责声明**：为了处理海量的词汇，本数据集中的所有释义、例句以及语境分类均是由大语言模型（LLM）程序化生成的，**且尚未经过全量的人工复核**。尽管我们在生成时尽力保证了质量，但 LLM 偶尔仍可能会出现“幻觉”或细微的不准确，尤其是在处理高度专业化的 IT 术语时。本数据集按“原样”提供，主要用于学习、交流与研究目的。我们非常欢迎社区的贡献——如果您发现了任何错误、机器幻觉或是想提供更准确的语境例句，请随时提交 Issue 或 Pull Request 帮我们一起完善！

### 🚀 快速使用 (Python)

由于数据是 JSONL 格式，您可以使用 Python 轻松地按行读取：

```python
import json

with open('CloudWords.jsonl', 'r', encoding='utf-8') as f:
    for line in f:
        data = json.loads(line)
        print(data['term'], data['count'])
```

### 📄 开源协议 (License)

[IT Dictionary](https://github.com/hxl9654/IT-Dictionary) © 2026 由 [Xiaonglong He](https://github.com/hxl9654/) 采用 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) 许可协议进行授权。
