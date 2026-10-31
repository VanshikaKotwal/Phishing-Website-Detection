# Phishing Website Detection

A machine learning project focused on identifying phishing websites by analyzing suspicious URL patterns and classifying them as either safe or malicious.

## Project Goals

- Detect phishing URLs using a data-driven approach.
- Build a lightweight URL classification workflow based on text-based features extracted from website addresses.
- Train and evaluate classification models on a large phishing and legitimate URL dataset.
- Create a reusable workflow that can be extended for real-world threat detection use cases.
- Provide an easy-to-follow notebook-based implementation for experimentation and learning.

## Why This Project Matters

Phishing attacks often impersonate legitimate services such as banking, email, and e-commerce platforms to steal sensitive user information. This project helps automate the detection process by examining URL text patterns, domain behavior, and model-based classification to flag risky websites before users interact with them.

## Key Features

- Large-scale phishing URL dataset analysis
- URL text tokenization and stemming
- Feature engineering from suspicious URL strings
- Model training and evaluation using machine learning algorithms
- Pretrained model artifacts for quick reuse
- Notebook-based workflow for transparency and experimentation

## Project Structure

```text
Phishing-Website-Detection/
├── Dataset/
│   └── phishing_site_urls.csv
├── Phishing Website Detection System.ipynb
├── phishing.pkl
├── phishing_mnb.pkl
├── vectorizer.pkl
├── phishing_site_urls.csv.zip
├── .gitignore
└── README.md
```

## Tech Stack Checklist

- [x] Python
- [x] Jupyter Notebook
- [x] pandas
- [x] NumPy
- [x] scikit-learn
- [x] NLTK
- [x] Matplotlib
- [x] WordCloud
- [x] Pickle (model serialization)
- [x] CSV dataset processing

## Installation

1. Clone the repository:

```bash
git clone https://github.com/VanshikaKotwal/Phishing-Website-Detection.git
cd Phishing-Website-Detection
```

2. Create and activate a virtual environment:

```bash
python -m venv .venv
```

On Windows:

```bash
.venv\Scripts\activate
```

On macOS/Linux:

```bash
source .venv/bin/activate
```

3. Install the required dependencies:

```bash
pip install pandas numpy matplotlib scikit-learn nltk wordcloud jupyter
```

4. Download or confirm the dataset is available in the `Dataset` folder.

5. Open the notebook:

```bash
jupyter notebook "Phishing Website Detection System.ipynb"
```

## Usage Example

This project can be used to classify a URL as phishing or legitimate.

```python
import pickle

# Load trained model and vectorizer
with open('phishing.pkl', 'rb') as f:
    model = pickle.load(f)

with open('vectorizer.pkl', 'rb') as f:
    vectorizer = pickle.load(f)

# Example URL to validate
url = "https://paypal-security-login.com/account"

# Transform URL into feature vector
features = vectorizer.transform([url])

# Predict label
prediction = model.predict(features)[0]

if prediction == 'bad':
    print("This URL is likely phishing.")
else:
    print("This URL appears to be legitimate.")
```

## Example Output

```text
This URL is likely phishing.
```

## Model Workflow

The notebook follows this general flow:

1. Load phishing and legitimate URL data
2. Clean and tokenize URL strings
3. Stem and normalize text content
4. Convert text into numeric features
5. Train a machine learning classifier
6. Evaluate performance and save model artifacts

## Notes

- The dataset used in this project is a URL-based phishing detection dataset and is stored in `Dataset/phishing_site_urls.csv`.
- Pretrained model files such as `phishing.pkl` and `vectorizer.pkl` are included for quick testing and experimentation.
- The project is ideal for learning how text-based malicious URL detection works in real-world cybersecurity applications.

## License

This project is provided for educational and research purposes. Please check repository usage policies before commercial deployment.

## Contact

For questions or collaboration opportunities, feel free to reach out via the GitHub profile associated with this repository.
