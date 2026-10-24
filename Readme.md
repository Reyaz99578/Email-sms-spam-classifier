# 📩 Email/SMS Spam Classifier

An end-to-end machine learning project that classifies a message as **Spam** or **Not Spam**, built with Python, scikit-learn, NLTK and Streamlit, and deployed as a live web app.

🔗 **Live Demo:** [Add your Streamlit link here]([https://your-app-name.streamlit.app](https://email-sms-spam-classifier-ac5q2ljwjwyaese3vbgmj8.streamlit.app/))

<!-- Add a screenshot: save it in the repo as screenshot.png, then uncomment the line below -->
<!-- ![App Screenshot](screenshot.png) -->

---

## 🎯 Problem Statement

Spam and fraud messages are a daily problem. This project builds a model that reads a message, understands its content, and flags it as spam, with a simple web interface anyone can use.

## ⚙️ How It Works

```
Raw message
   ↓
Text preprocessing (lowercase → tokenize → remove stopwords/punctuation → stemming)
   ↓
TF-IDF vectorization (3000 features)
   ↓
Multinomial Naive Bayes classifier
   ↓
Spam / Not Spam  (shown in Streamlit UI)
```

## 📊 Results

| Metric | Score |
|--------|-------|
| Accuracy | ~96.7% |
| Precision | 100% |

Precision was prioritised because, in spam filtering, wrongly marking a genuine message as spam is costlier than letting a spam message through.

## 🗂️ Dataset

[UCI SMS Spam Collection](https://www.kaggle.com/uciml/sms-spam-collection-dataset): 5,572 labelled SMS messages (5,169 after removing duplicates), split 80/20 for training and testing.

## 🛠️ Tech Stack

- **Language:** Python
- **Data:** Pandas, NumPy
- **NLP:** NLTK (tokenization, stopwords, Porter stemmer)
- **ML:** scikit-learn (TF-IDF, Multinomial Naive Bayes)
- **App & Deployment:** Streamlit, Streamlit Community Cloud, GitHub

## 📁 Project Structure

```
├── app.py               # Streamlit web app
├── train.py             # Preprocessing + training + saves model
├── spam.csv             # Dataset
├── model.pkl            # Trained Naive Bayes model
├── vectorizer.pkl       # Fitted TF-IDF vectorizer
├── requirements.txt     # Dependencies
└── README.md
```

## 🚀 Run Locally

```bash
# 1. Clone the repo
git clone https://github.com/Reyaz99578/Email-sms-spam-classifier.git
cd Email-sms-spam-classifier

# 2. Create and activate a virtual environment
python -m venv venv
venv\Scripts\activate        # Windows
# source venv/bin/activate   # Mac/Linux

# 3. Install dependencies
pip install -r requirements.txt

# 4. (Optional) Retrain the model
python train.py

# 5. Run the app
streamlit run app.py
```

## 🧪 Example

| Message | Prediction |
|---------|-----------|
| "URGENT! You have won a FREE 2000 cash prize. Text WIN to 80086 to claim now!" | 🚨 Spam |
| "Ok I will call you after dinner. Please keep the notes ready." | ✅ Not Spam |

## ⚠️ Limitations

- Trained on English SMS data (UK-based, older messages), so it may miss newer fraud patterns such as Indian KYC/UPI scams or phishing links.
- Does not support Hindi or Hinglish messages.
- Bag-of-words features ignore word order and context.

## 🔮 Future Improvements

- Train on a larger, more recent dataset that includes phishing and Indian-context scam messages
- Compare more models (Logistic Regression, SVM, XGBoost) and tune hyperparameters
- Try embeddings or a transformer model (e.g. BERT) for better context understanding
- Add Hindi/Hinglish support
- Show the prediction confidence score in the app

## 🙏 Acknowledgements

Project idea and walkthrough inspired by the [CampusX](https://www.youtube.com/@campusx-official) spam classifier tutorial. Model retrained and app rebuilt with updated libraries and deployment on Streamlit Cloud.

## 👤 Author

**Reyaz Ansari**
GitHub: [@Reyaz99578](https://github.com/Reyaz99578)
