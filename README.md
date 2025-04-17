# 📊 Sentiment Analysis on Tokopedia App Reviews

This project performs sentiment analysis on user reviews of the Tokopedia application by using both Machine Learning and Deep Learning techniques.

---

## 📥 Data Collection & Cleaning

- **Source**: User reviews scraped from the Tokopedia app on Google Play Store using `google-play-scraper`.
- **Initial Cleaning**:
  - Removed missing values
  - Removed duplicate entries

---

## 🧹 Text Preprocessing

To standardize the input and improve model performance, the following preprocessing steps were applied:

- Convert text to lowercase  
- Remove numbers  
- Remove punctuation  
- Remove extra whitespaces  
- Tokenize text into words  
- Remove stopwords (using `stopwordbahasa.csv`)  
- Normalize slang using `new_kamusalay.csv`

These steps ensure cleaner and more consistent input for vectorization using either **TF-IDF** or **Tokenizer**.

---

## 🧠 Models and Performance

Four different models were trained and evaluated on the same dataset:

### 1. **Random Forest (TF-IDF)**
- **Train Accuracy**: 98.49%  
- **Test Accuracy**: 87.77%  
- Very strong performance on training data; slightly lower test accuracy compared to SVM.

### 2. **DNN (TF-IDF)**
- **Train Accuracy**: 97.99%  
- **Test Accuracy**: 87.88%  
- Stable and balanced performance across both training and test datasets.

### 3. **BiLSTM (Tokenizer)**
- **Train Accuracy**: 95.77%  
- **Test Accuracy**: 86.89%  
- Good performance overall, especially on sequential data; test accuracy slightly lower than other models.

### 4. **SVM (TF-IDF)**
- **Train Accuracy**: 93.23%  
- **Test Accuracy**: 89.11%  
- Highest test accuracy among all models; best generalization on unseen data.

---

## ✅ Final Conclusion

- **Best for generalization**: **SVM (TF-IDF)** – highest test accuracy  
- **Best fit to training data**: **Random Forest (TF-IDF)**  
- **Most balanced and stable**: **DNN (TF-IDF)**  
- **For sequential data**: **BiLSTM (Tokenizer)**

> The best model depends on the specific objective: whether prioritizing prediction accuracy, model strength, or generalization capability.

---

## 📁 Project Structure

Below is a brief description of each file in the repository:

| File | Description |
|------|-------------|
| `Data Scraping.ipynb` | Notebook for scraping Tokopedia reviews from the Google Play Store. |
| `Notebook pelatihan.ipynb` | Main training notebook for preprocessing and model training. |
| `Inference.ipynb` | Notebook for testing the trained model on new inputs. |
| `README.md` | Project documentation. |
| `label_encoder.pkl` | Label encoder used to convert sentiment labels to integers and back. |
| `new_kamusalay.csv` | Slang word dictionary used to normalize informal words. |
| `stopwordbahasa.csv` | Indonesian stopword list. |
| `requirements.txt` | Python dependencies for this project. |
| `svm_tfidf_model.pkl` | Pre-trained SVM model using TF-IDF. |
| `tfidf_vectorizer.pkl` | TF-IDF vectorizer used for transforming text data. |

---

## ⚙️ Installation

To run this project locally:

```bash
pip install -r requirements.txt
