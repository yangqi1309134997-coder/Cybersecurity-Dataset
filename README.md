# Cybersecurity-Dataset
网络安全数据集是一个全面的网络安全相关数据集合，旨在用于训练和微调网络安全应用中的大型语言模型 (LLM)。它专注于内部网络（离线）环境，解决漏洞检测、威胁分析、代码审计和 AI 驱动的防御机制等痛点。该数据集经过精心策划，旨在支持开发本地部署的 AI 模型，例如 DeepSeek-14B 和 Qwen-Code-30B MOE，从而实现敏感数据映射、零信任架构、AI 威胁预警、智能代码安全审计、网络流量分析和 WebShell 木马检测等功能。

(Note: Replace the above with the actual URL of the uploaded image for the "智穹盾" poster. You can upload it to Hugging Face or another host like GitHub for embedding.)

Dataset Summary
The Cybersecurity-Dataset is a comprehensive collection of cybersecurity-related data designed for training and fine-tuning large language models (LLMs) in network security applications. It focuses on inner-network (offline) environments, addressing pain points such as vulnerability detection, threat analysis, code auditing, and AI-driven defense mechanisms. This dataset was curated to support the development of locally deployable AI models like DeepSeek-14B and Qwen-Code-30B MOE, enabling features such as sensitive data mapping, zero-trust architecture, AI threat warnings, intelligent code security auditing, network traffic analysis, and WebShell trojan detection.

The dataset consists of question-answering (Q&A) pairs, code snippets, and technical explanations primarily in Chinese, covering topics like adversarial attacks, traffic pattern analysis, zero-day vulnerabilities, encrypted traffic inspection, internal threat detection, and more. It has been used in real-world scenarios, including government and enterprise network security training, attack-defense drills, and platform integrations like the "智穹盾" (Smart Dome Shield) AI platform.

Key statistics:

Size: Approximately 63,527 examples (10K–100K range)
Downloads: 19 (as of last month)
Total File Size: 139 MB (original JSON), 65.6 MB (Parquet conversion)
This dataset promotes AI integration in cybersecurity, aligning with national policies like China's Network Security Law and Data Security Law, emphasizing indigenous innovation and offline deployment for critical sectors such as government, finance, and energy.

Motivation
In the context of rapid growth in China's cybersecurity market (projected to exceed 1,000 billion CNY by 2025), this dataset addresses three core pain points:

Offline environments lacking internet-based protection.
Traditional tools struggling with AI-driven complex attacks.
Small teams facing talent and cost constraints in security operations.
Sourced from diverse legitimate channels and processed using the Easy Dataset tool, it enables fine-tuning of models for practical applications, such as improving attack detection rates by 40% in energy enterprises and reducing vulnerability fix times from 14 days to 3 days in finance.

Composition
The dataset is structured as instructional Q&A pairs with optional inputs and system prompts, including Python code examples for implementation. Examples cover practical scenarios from vulnerability exploitation to defensive strategies, drawn from real attack-defense logs and educational materials.

Dataset Structure
Data Instances
An example instance looks like this (in JSON format):

{
  "instruction": "在会话异常检测中，如何应对对抗性攻击对模型性能的影响？",
  "input": "",
  "output": "详细的技术响应，包括对抗训练、集成防御、输入验证等步骤，以及Python代码片段。",
  "system": "You are a cybersecurity expert AI."
}

Instances vary in length: instruction strings (3–143 chars), output strings (0–17.7k chars).

Data Fields
instruction (string): The query or prompt related to a cybersecurity topic, e.g., "How to handle adversarial attacks in session anomaly detection?"
input (string, optional): Additional context or data for the query (often empty).
output (string): Detailed response, including explanations, steps, and code snippets in Python for implementation.
system (string, optional): System prompt for guiding the model's behavior (e.g., role-playing as a security expert).
Data Splits
Train: The primary split containing all 63,527 examples. No explicit test/validation splits are provided, but users can create custom splits as needed.
Dataset Creation
Curation Rationale
This dataset was created to fill the gap in localized, offline-capable AI training data for cybersecurity. It supports models compliant with China's "Xin Chuang" (indigenous innovation) requirements, such as adaptation to domestic CPUs/OS like Feiteng chips, Kirin OS, and Tongxin UOS.

Source Data
Data Collection and Processing
Data was collected from legitimate, public sources using scripts for automated scraping and downloading:

Search engines: Google, Baidu, 360 Search.
Platforms: GitHub repositories, CSDN articles and code snippets.
Resources: Cybersecurity e-books, shared netdisk files (e.g., Baidu Netdisk).
Proprietary: Anonymized real-world attack-defense logs from company operations (e.g., vulnerability scans, penetration tests).
The raw data was processed using the Easy Dataset tool for deduplication, validation, labeling, and formatting into Q&A pairs. All processing ensured compliance with intellectual property laws, focusing on educational and defensive use only.

Annotation Process
Annotations were semi-automated: Scripts extracted key topics, and manual review ensured relevance to network security. No personal data or sensitive information is included.

Who are the source data producers?
Produced by the team at Xinjiang Huancheng Wang'an Technology Co., Ltd., in collaboration with educational institutions and industry partners like Tianrongxin Education and Ji'an Yunke.

Uses
Direct Use
Load the dataset for training/fine-tuning LLMs:

from datasets import load_dataset

dataset = load_dataset("hcnote/Cybersecurity-Dataset")
print(dataset['train'][0])

Ideal for:

Fine-tuning models like DeepSeek-14B or Qwen-Code-30B MOE using frameworks such as Llama Factory or Ollama.
Building AI platforms for local deployment, e.g., integrating with FastAPI for API access.
Research in AI-driven cybersecurity, such as threat detection in offline networks.
Out-of-Scope Use
Not intended for offensive cybersecurity activities, real-time attacks, or any illegal purposes. Use strictly for defensive, educational, and research scenarios.

Bias, Risks, and Limitations
Bias: Primarily Chinese-language content, potentially biased toward regional threats (e.g., APT attacks in government/energy sectors).
Risks: Misuse could lead to ineffective models if not fine-tuned properly; ensure compliance with local laws.
Limitations: Focused on text-based Q&A; lacks multimodal data. Coverage may not include emerging threats post-2025.
Citation
If you use this dataset, please cite it as:

@dataset{hcnote_cybersecurity_dataset_2025,
  author = {Xinjiang Huancheng Wang'an Technology Co., Ltd. Team},
  title = {Cybersecurity-Dataset: A Dataset for AI-Driven Network Security},
  year = {2025},
  url = {https://huggingface.co/datasets/hcnote/Cybersecurity-Dataset}
}

Dataset Card Authors
hcnote (Primary curator)
Contributors from "智穹盾" project team
Dataset Card Contact
For questions or contributions, contact via Hugging Face discussions or email (add your contact here).

License
This dataset is licensed under the Apache License 2.0. All data is sourced legitimately and intended for open research.
