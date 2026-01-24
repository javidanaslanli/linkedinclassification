# LinkedIn Job Title Classification

**Capstone Project** | Julius-Maximilians-Universität Würzburg

A machine learning system that classifies LinkedIn job titles into **seniority levels** and **departments** using an ensemble of neural networks and gradient boosting.

---

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/javidanaslanli/linkedinclassification/blob/main/notebook/LinkedInClassification.ipynb)

## 📊 Results

| Task | Accuracy | F1 Macro | F1 Weighted |
|------|----------|----------|-------------|
| **Seniority** | 65.90% | 61.06% | 69.00% |
| **Department** | 73.85% | 66.47% | 74.79% |

---

## 📁 Project Structure

```
linkedin-classification/
│
├── README.md                          # This file
├── requirements.txt                   # Python dependencies
│
├── config/                            # Configuration files (included)
│   ├── keywords.json                  # Keyword rules for fallback logic
│   ├── concepts.json                  # Concept definitions for neural model
│   └── training_titles.json           # Synthetic training examples
│
├── data/                              # YOUR DATA GOES HERE
│   ├── department-v2.csv              # Department training data
│   ├── seniority-v2.csv               # Seniority training data
│   └── testdata.txt                   # Test data (JSON format)
│
├── notebooks/
│   └── LinkedInClassification.ipynb   # Main notebook (run this)
│
├── app/
│   └── gradio_app.py                  # Standalone demo application
│
├── models/                            # Generated after training
│   ├── moe_seniority.pt
│   ├── moe_department.pt
│   └── models_bundle.pkl
│
└── outputs/                           # Generated visualizations
    └── confusion_matrices.png
```

---

## 📥 Full Project Download

**[Google Drive - All Files (Data, Models, Report)]((https://drive.google.com/drive/folders/18GTTqHFBUde-JM9nLHL-8hW7RfMTqv0I?usp=drive_link))**
```

---

## Getting the Link ID

Your Google Drive link looks like:
```
https://drive.google.com/drive/folders/1ABC123xyz?usp=sharing
                                        ↑
                                   This is the FOLDER_ID
```

For files:
```
https://drive.google.com/file/d/1ABC123xyz/view?usp=sharing
                                ↑
                           This is the FILE_ID


```

## 🚀 Quick Start: Google Colab

### Step 1: Prepare Google Drive

Create this exact folder structure in your Google Drive:

```
My Drive/
└── linkedin-classification/
    │
    ├── config/
    │   ├── keywords.json        ← Copy from this repo
    │   ├── concepts.json        ← Copy from this repo
    │   └── training_titles.json ← Copy from this repo
    │
    ├── data/
    │   ├── department-v2.csv    ← Your training data
    │   ├── seniority-v2.csv     ← Your training data
    │   └── testdata.txt         ← Your test data
    │
    ├── models/                  ← Create empty folder
    │
    └── outputs/                 ← Create empty folder
```

### Step 2: Upload Files

1. Download this repository as ZIP (Code → Download ZIP)
2. Extract the ZIP file
3. Upload the **entire `config/` folder** to your Google Drive
4. Upload your data files to the `data/` folder

### Step 3: Open Notebook in Colab

1. Go to [Google Colab](https://colab.research.google.com)
2. File → Upload notebook
3. Select `notebooks/LinkedInClassification.ipynb`
4. **Important:** Change runtime to GPU
   - Runtime → Change runtime type → T4 GPU → Save (Or any GPU)

### Step 4: Run the Notebook

1. Run the first cell to mount Google Drive
2. Run all remaining cells (Runtime → Run all)
3. The Gradio demo will launch at the end with a public URL

---

## 💻 Local Setup

```bash
# Clone or download repository
git clone https://github.com/YOUR_USERNAME/linkedin-classification.git
cd linkedin-classification

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows

# Install dependencies
pip install -r requirements.txt

# Add your data files to data/ folder

# Run Jupyter notebook
jupyter notebook notebooks/LinkedInClassification.ipynb

# Or run standalone Gradio demo (after training)
python app/gradio_app.py
```

---

## 📋 Data Format

### Training CSV Files

Files: `department-v2.csv`, `seniority-v2.csv`

```csv
text,label
Software Engineer,Information Technology
Sales Manager,Sales
CEO,Management
Junior Developer,Junior
```

### Test Data JSON

File: `testdata.txt`

```json
[
  [
    {
      "position": "Senior Software Engineer",
      "organization": "Google",
      "seniority": "Senior",
      "department": "Information Technology",
      "status": "ACTIVE"
    }
  ]
]
```

---

## 🏷️ Classification Categories

### Seniority Levels (6 classes)

| Level | Description | Examples |
|-------|-------------|----------|
| Junior | Entry-level, interns | Intern, Praktikant, Trainee |
| Professional | Standard roles | Engineer, Analyst, Manager |
| Senior | Experienced ICs | Senior Engineer, Principal |
| Lead | Team leaders | Team Lead, Head of |
| Director | Department heads | Director, VP |
| Management | C-level, founders | CEO, Founder, Geschäftsführer |

### Departments (11 classes)

| Department | Keywords |
|------------|----------|
| Information Technology | software, developer, engineer, data scientist |
| Sales | sales, account executive, vertrieb |
| Marketing | marketing, brand, SEO |
| Human Resources | HR, recruiter, talent |
| Consulting | consultant, berater |
| Project Management | project manager, scrum master |
| Business Development | BD manager, partnerships |
| Customer Support | support, customer service |
| Administrative | assistant, secretary |
| Purchasing | procurement, buyer, einkauf |
| Other | Everything else (default fallback) |

---

## 🌍 Supported Languages

- **English** (primary)
- **German** (Geschäftsführer, Entwickler, Berater)
- **French** (Directeur, Ingénieur, Responsable)

---



## 📄 License

MIT License - Academic project for Julius-Maximilians-Universität Würzburg
