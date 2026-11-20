# MindStack
## AI-Based Technical Language Simplifier

**COMP365 Team Project – North Carolina A&T State University**

**Team Members:** Derry Moss, Jordyn Walsh-Hill, Sydney Jackson, Jerry Kang

---

### 1. Project Overview

MindStack is an AI-based technical language simplifier designed to make technical documentation easier to understand while preserving its original meaning and factual accuracy.

The project explores two large language models (LLMs) to simplify technical passages from several computing-related areas. The team evaluates the generated text using readability measurements and human reviews to compare the models' performance.

The project focuses on three main areas:

- Readability: How easy the simplified text is to read.
- Meaning preservation: Whether important technical information from the original passage is retained.
- Factual accuracy: Whether the simplified text remains accurate without introducing unsupported information.

### 2. Dataset

The project dataset contains 30 technical passages collected from sources including Microsoft Learn, Microsoft Support, and Cisco.

The dataset includes five categories:

| Category | Number of Passages |
|---|---:|
| Cloud Computing | 10 |
| Databases | 5 |
| Networking | 5 |
| Security | 5 |
| Software Engineering | 5 |
| **Total** | **30** |

The `Passages.csv` file contains the passage ID, category, source URL, original text, and word count.

### 3. Technology and Development Environment

The project uses:

- Python
- Google Colab
- Google Drive
- Hugging Face Transformers
- Qwen2.5-1.5B-Instruct
- Qwen3-4B
- 4-bit model quantization for Version 2

The team uses prompt engineering to guide the language models. Neither model is fine-tuned for this project.

**Models Evaluated**

| Version | Language Model | Configuration |
|---|---|---|
| Version 1 | Qwen2.5-1.5B-Instruct | Initial model, CPU |
| Version 2 | Qwen3-4B | 4-bit quantization, Colab GPU |

Version 2 was introduced to improve the quality of technical simplifications after the initial model produced passages with omitted details and factual inaccuracies.

**Why Google Colab?**

Google Colab was selected as the development environment because it provides a browser-based Python notebook environment that integrates with Google Drive. This allows team members to work with the notebook and project files without requiring identical local development environments.

Colab also supports the Python libraries and model workflow used in this project. Google Drive stores project files, while GitHub provides version control and a central location for sharing project code and documentation.

### 4. Evaluation Methods

The team uses two complementary evaluation methods.

**Readability Measurements**

Two measurements are used:

- **Flesch Reading Ease:** Estimates how easy a passage is to read. Higher scores generally indicate easier text.
- **Flesch-Kincaid Grade Level:** Estimates the U.S. school grade level needed to understand the text. Lower scores generally indicate easier text.

**Human Evaluation**

Each of the 30 simplified passages is reviewed using two criteria:

- **Meaning Preserved:** Determines whether the simplified passage retains the important technical meaning and information from the original.
- **Factually Accurate:** Determines whether the simplified passage contains accurate information without unsupported or incorrect details.

The same review criteria are applied to both models.

### 5. Project Results

**Readability Comparison**

| Measurement | Original | Version 1 | Version 2 |
|---|---:|---:|---:|
| Flesch Reading Ease | 36.49 | 67.32 | 58.89 |
| Flesch-Kincaid Grade Level | 12.19 | 7.94 | 8.57 |

Both models improved readability compared with the original passages. Version 1 achieved higher Flesch Reading Ease and a lower grade-level score.

**Human Evaluation Comparison**

| Evaluation | Version 1 | Version 2 |
|---|---:|---:|
| Meaning Preserved | 16/30 (53.3%) | 24/30 (80.0%) |
| Factually Accurate | 9/30 (30.0%) | 23/30 (76.7%) |
| Passed Both Criteria | 9/30 (30.0%) | 23/30 (76.7%) |

Version 2 achieved better human evaluation results for meaning preservation and factual accuracy. Although Version 1 produced higher readability scores, Version 2 performed better in retaining technical meaning and factual information.

These findings demonstrate that readability and content quality are different aspects of text simplification. A passage can be easier to read without necessarily preserving all of its original technical information.

**Evaluation Limitation**

The evaluation is based on 30 technical passages. The results provide a comparison of the two models within this dataset but should not be interpreted as proof of performance across all technical documentation.

### 6. Project Files

The repository contains the following files:

| File | Description |
|---|---|
| `COMP365_Technical_Language_Simplifier.ipynb` | Main Google Colab notebook |
| `Passages.csv` | Original dataset containing 30 technical passages |
| `Simplified_Passages.csv` | Version 1 simplified passages |
| `Simplified_Passages_V2.csv` | Version 2 simplified passages |
| `Quality_Review.csv` | Version 1 human evaluation records |
| `Quality_Review_V2.csv` | Version 2 human evaluation records |
| `Quality_Review_Summary.csv` | Version 1 quality evaluation summary |
| `Quality_Review_Summary_V2.csv` | Version 2 quality evaluation summary |
| `Readability_Results.csv` | Version 1 readability measurements |
| `Readability_Results_V2.csv` | Version 2 readability measurements |
| `README.md` | Project overview and instructions |

### 7. How to Run the Project

1. Download or clone the MindStack repository from GitHub.
2. Open [Google Colab](https://colab.research.google.com/).
3. Upload or open `COMP365_Technical_Language_Simplifier.ipynb`.
4. Place the required dataset and project files in the `COMP365_Team_Project` folder in Google Drive.
5. Mount Google Drive when prompted by the notebook.
6. Select a compatible Colab runtime with sufficient resources for the selected model.
7. Execute the notebook cells in order.
8. Review the simplified passages, readability measurements, and human evaluation results.

**Important:** The notebook uses the following Google Drive folder path:

`/content/drive/MyDrive/COMP365_Team_Project`

Make sure the folder and required files are available at that location before running the notebook.

The model-loading and simplification steps may require internet access and sufficient runtime resources.

### 8. Version Control and Collaboration

GitHub is used to maintain the project's source files and document development progress.

The team uses Git to track changes to the notebook, dataset, and supporting documentation. Meaningful commits help maintain a record of project development and make changes easier to review.

**Repository:** [https://github.com/Jerry-junsoo/MindStack](https://github.com/Jerry-junsoo/MindStack)

### 9. Reproducibility

To reproduce the project, users should have:

- A Google account with access to Google Colab and Google Drive.
- The project notebook and required CSV files.
- Internet access to load the required Python libraries and language models.
- A compatible Colab runtime with sufficient resources.

The notebook contains the project workflow, while the CSV files provide the original dataset, simplified passages, and saved evaluation results.

For consistent comparisons, use the same dataset, model versions, and notebook workflow documented in this repository.