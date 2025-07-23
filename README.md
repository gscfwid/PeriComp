# 🏥 Enhancing Privacy-Preserving Deployable Large Language Models for Perioperative Complication Detection: A Targeted Strategy with LoRA Fine-tuning

[![medRxiv](https://img.shields.io/badge/medRxiv-2025.06.11.25329235-red)](https://www.medrxiv.org/content/10.1101/2025.06.11.25329235v1)
[![Python](https://img.shields.io/badge/Python-3.8+-blue)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Paper](https://img.shields.io/badge/Paper-Preprint-brightgreen)](https://www.medrxiv.org/content/10.1101/2025.06.11.25329235v1)

## 🚀 Quick Navigation
- 📊 [Data Source](#️-data_source) - Patient medical records and expert annotations
- 💬 [Prompts](#-prompt) - Complication definitions and prompt engineering
- 🚀 [Processing](#-requestsipynb) - AI model inference pipelines
- 📈 [Results](#-results) - Evaluation metrics and visualizations
- 📚 [Citation](#-citation) - How to cite this work

## ✨ Key Highlights

🔹 **Privacy-Preserving**: Deployable models without sending data to external APIs  
🔹 **LoRA Fine-tuning**: Efficient adaptation of open-source LLMs  
🔹 **Targeted Strategy**: Optimized prompt engineering for medical tasks  
🔹 **Multi-Center Validation**: Tested across different healthcare centers  
🔹 **Comprehensive Evaluation**: Micro and macro averaging strategies  

## 📖 Project Description

This repository contains the code for the research paper "Enhancing Privacy-Preserving Deployable Large Language Models for Perioperative Complication Detection: A Targeted Strategy with LoRA Fine-tuning" (Preprint DOI: [10.1101/2025.06.11.25329235v1](https://www.medrxiv.org/content/10.1101/2025.06.11.25329235v1)).

The study explores how combining targeted prompt engineering with LoRa fine-tuning can boost performance of open-source models for perioperative complication detection from clinical records.

## 📁 File Structure

### 🗂️ data_source
This is where our story begins. Due to privacy protection requirements, we have only uploaded an example.

📋 [medical_record.json](data_source/medical_record.json) contains patient medical records, which typically include 3 parts:
- 🩺 Medical history
- 🧪 Laboratory tests (including chemical and microbiological tests)
- 🔍 Examinations

Two folders contain human expert judgments on perioperative complications (file: 👨‍⚕️ [human_expert.json](data_source/center1/human_expert.json)) and the gold standard (🥇 [gold_standard.json](data_source/center1/gold_standard.json)) determined by expert consensus.
- 🏥 [Center 1](data_source/center1/) was used for validation and test set division (only one example shown).
- 🏨 [Center 2](data_source/center2/) serves as an external validation set.

### 💬 prompt
This contains our definition of complications (📝 [defination.md](prompt/defination.md)), based on the European Perioperative Clinical Outcome (EPCO) definition.

Based on AI complication identification results, we made certain modifications to 📝 [defination.md](prompt/defination_modified.md) (📝 [defination_modified.md](prompt/defination_modified.md)).

📓 [prompts.ipynb](prompt/prompts.ipynb) is the notebook for processing prompts. Here we integrate medical_records with definitions to form prompt files for different strategies (comprehensive vs targeted) for subsequent AI processing. The prompts consist of the following components:
- 🎯 Role and objective
- 📚 Definition of perioperative complications
- 📊 Output format
- 📋 Medical records

### 🚀 requests.ipynb
The main notebook for AI processing: 📓 [requests.ipynb](requests.ipynb)

### 📊 results
This contains all our results.

The raw folder stores all AI processing results. Due to the large amount of case information in think tags, we have only provided some examples.

📓 [format_results.ipynb](results/format_results.ipynb) converts raw results into comparable results. Comparable results are saved by center in:
- 🏥 [center1](results/center1/)
- 🏨 [center2](results/center2/)

Since comparable results contain no case information, we uploaded all results. Each case is a list of postoperative complications that can be compared with the gold standard (🥇 [gold.json](results/center1/gold.json)) to obtain metrics (F1, recall, precision).

📓 [evaluation.ipynb](results/evaluation.ipynb) is our notebook for calculating metrics. Here we calculate results for each AI using two different averaging strategies (micro & macro), with final results saved in the 📊 [evaluation_dataframes](results/evaluation_dataframes/) folder.

Using the 📈 [plot.ipynb](results/plot.ipynb) notebook, we visualized all evaluation dataframes, with results saved in the 📈 [figures](results/figures/) folder, which contains all panels used in our paper.

## 📚 Citation

If you use this work in your research, please cite:

```bibtex
@misc{gao2025enhancing,
  title={Enhancing Privacy-Preserving Deployable Large Language Models for Perioperative Complication Detection: A Targeted Strategy with LoRA Fine-tuning},
  author={Shaowei Gao and Xu Zhao and Lihui Chen and Junrong Yu and Shuning Tian and Huaqiang Zhou and Jingru Chen and Sizhe Long and Qiulan He and Xia Feng},
  year={2025},
  howpublished={medRxiv},
  doi={10.1101/2025.06.11.25329235},
  url={https://www.medrxiv.org/content/10.1101/2025.06.11.25329235v1}
}
```

## 📞 Contact

For questions about this research, please contact:
- 📧 **Shaowei Gao**: [gshaowei@mail.sysu.edu.cn](mailto:gshaowei@mail.sysu.edu.cn)
- 📧 **Xia Feng**: [fengxia@mail.sysu.edu.cn](mailto:fengxia@mail.sysu.edu.cn)


## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
⭐ **If you find this work helpful, please consider giving it a star!** ⭐

