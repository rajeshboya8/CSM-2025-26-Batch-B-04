# CSM-2025-26-Batch-B-04
#!/bin/bash
# 🌿 Setup Script for Ayurveda Intelligence for Healing (AI4H)

# Create project structure
mkdir AI4H && cd AI4H
mkdir data models static templates

# Create requirements.txt
cat <<EOL > requirements.txt
flask
scikit-learn
pandas
numpy
nltk
spacy
requests
EOL

# Create app.py (Flask entry point)
cat <<'EOL' > app.py
from flask import Flask, render_template, request
import pickle
import nltk

app = Flask(__name__)

# Load trained ML models (placeholders for now)
try:
    disease_model = pickle.load(open("models/disease_model.pkl", "rb"))
    medicine_model = pickle.load(open("models/medicine_model.pkl", "rb"))
except:
    disease_model = None
    medicine_model = None

@app.route('/')
def index():
    return render_template("index.html")

@app.route('/predict', methods=['POST'])
def predict():
    symptoms = request.form['symptoms']
    # Placeholder logic (replace with real ML prediction)
    disease = "Fever"
    medicine = "Tulsi Tea"
    remedy = "Boil Tulsi leaves in water, add honey, drink twice daily."
    return render_template("result.html", symptoms=symptoms, disease=disease, medicine=medicine, remedy=remedy)

if __name__ == "__main__":
    app.run(debug=True)
EOL

# Create chatbot.py
cat <<'EOL' > chatbot.py
# Simple NLP-based chatbot placeholder
def chatbot_response(user_input):
    responses = {
        "fever": "Drink Tulsi tea and consult nearby doctor if high temperature.",
        "cough": "Use turmeric milk, and avoid cold drinks.",
        "headache": "Practice yoga and try herbal tea."
    }
    for key in responses:
        if key in user_input.lower():
            return responses[key]
    return "I'm still learning! Please consult a doctor if serious."
EOL

# Create index.html
cat <<'EOL' > templates/index.html
<!DOCTYPE html>
<html>
<head>
  <title>AI4H - Ayurveda Intelligence for Healing</title>
</head>
<body>
  <h1>🌿 Ayurveda Intelligence for Healing</h1>
  <form action="/predict" method="post">
    <label>Enter your symptoms:</label><br>
    <input type="text" name="symptoms" placeholder="e.g., fever, body pain">
    <button type="submit">Get Remedy</button>
  </form>
</body>
</html>
EOL

# Create result.html
cat <<'EOL' > templates/result.html
<!DOCTYPE html>
<html>
<head>
  <title>AI4H Result</title>
</head>
<body>
  <h2>Prediction Result</h2>
  <p><b>Symptoms:</b> {{ symptoms }}</p>
  <p><b>Predicted Disease:</b> {{ disease }}</p>
  <p><b>Recommended Ayurvedic Medicine:</b> {{ medicine }}</p>
  <p><b>Remedy Preparation:</b> {{ remedy }}</p>
  <a href="/">Go Back</a>
</body>
</html>
EOL

echo "✅ AI4H project structure created successfully!"
