# 🧠 AI-Powered Task Management System

> A complete ML-based project to classify task priority and assign them intelligently using NLP, structured features, and workload balancing logic.

---

## 📌 1. Introduction

Managing software project tasks manually often leads to imbalance, misclassification, and delays.  
This project proposes an AI-powered task manager that leverages **Natural Language Processing (NLP)** and **Machine Learning (ML)** to:
- **Automatically classify** the priority of tasks (High / Medium / Low)
- **Assign tasks fairly** to team members based on workload
- Simulate a real-world planning and productivity enhancement system

---

## 📂 2. Dataset Creation

- A custom dataset of **200 synthetic tasks** was generated using realistic software development phrases.
- Each record contains:
  - `Task_ID`
  - `Description` (text)
  - `Deadline` (date)
  - `Assigned_To`
  - `Priority` (High, Medium, Low)
  - `Completed` (Yes/No)

📁 File: `task_data_200.csv`

---

## 📊 3. Exploratory Data Analysis (EDA)

- Distribution of task priorities:
  - Medium: 99 tasks
  - High: 54 tasks
  - Low: 47 tasks
- Completion status:
  - Completed: 65
  - Not completed: 135
- Workload was visualized using bar charts for fair member task assignment

---

## 🔄 4. NLP Preprocessing

NLP techniques were applied on task descriptions:

- Lowercasing, punctuation removal
- Stopword removal (`nltk`)
- TF-IDF feature extraction

📌 These features were then passed into ML models.

---

## 🧠 5. Model Training & Evaluation

Three models were implemented to classify task priority:

| Model            | Accuracy | F1 (High) | F1 (Medium) | F1 (Low) |
|------------------|----------|-----------|-------------|----------|
| Naive Bayes      | 42%      | 0.00      | 0.59        | 0.44     |
| Random Forest    | 42%      | 0.10      | 0.63        | 0.33     |
| VotingClassifier | 42%      | 0.17      | 0.59        | 0.42     |

> 📌 VotingClassifier combined Random Forest + Logistic Regression and achieved best-balanced results.

---

## ⚙️ 6. Feature Engineering

To improve learning, the following structured features were added:

- `Days_Left` = (Deadline - Today)
- `Urgent` = Boolean (True if < 5 days left)
- `Completed_Binary` = 1 if Completed, else 0

✅ These features were scaled and concatenated with TF-IDF vectors to create hybrid models.

---

## 📦 7. Task Assignment Logic

A custom workload-balancing algorithm was implemented to:
- Assign tasks **evenly among 4 team members**: Kiran, Sneha, Rohit, Aanya
- Prioritize **High priority** tasks first
- Always assign to the member with the **least number of current tasks**

📈 Final distribution: 50 tasks each per member

---

## 🧾 8. Project Files

| File | Description |
|------|-------------|
| `AI_Task_Management.ipynb` | Full Colab notebook with code |
| `task_data_200.csv` | Dataset used for training/testing |
| `AI_Task_Management_Report.pdf` | Final detailed report with visuals & evaluation |
| `README.md` | This file |

---

## 🔮 9. Conclusion & Future Scope

This project demonstrates how AI and ML can be applied practically to real-world team management tools.

✅ Completed:
- Data preprocessing
- NLP-based ML classification
- Ensemble modeling
- Feature engineering
- Rule-based task allocation

💡 Future Improvements:
- Use BERT embeddings for deeper language context
- Skill-based assignment (matching task type to developer expertise)
- Web dashboard with Streamlit or Flask

---

## 👨‍💻 Developed By

**Ismail Nossam**  
Intern, Infotact Solutions  
June 2025 Cohort  
[GitHub](https://github.com/ismailnossam01)

---

⭐ If you liked this project, feel free to ⭐ the repo and connect on [LinkedIn](https://www.linkedin.com/in/ismail-nossam)
