#  Apple Quality Prediction

This project is a **Flask-based web application** that predicts the **quality of a fruit** (Good or Bad) based on user input parameters such as size, weight, sweetness, crunchiness, juiciness, ripeness, and acidity.  
The backend uses a pre-trained **Support Vector Machine (SVM)** model (`svc.pickle`) for classification.

---

##  Features

-  Machine learning–powered prediction (SVM model)
-  Web-based user interface built with Flask
-  Accepts multiple fruit quality parameters
-  Instant prediction (Good / Bad)
-  Modular structure for easy extension and deployment

---

##  Tech Stack

- **Python 3.8+**
- **Flask** — Web framework  
- **Scikit-learn (SVC)** — Machine learning model  
- **NumPy** — Data manipulation  
- **HTML/CSS (Jinja2 templates)** — Frontend interface  

---

##  Folder Structure

+ apple_quality_prediction_deploy
  + models
      + svc.pickle
  + templates
      + index.html
      + result.html
  + app.py
  + dockerfile
  + requirements.txt

---

## Local Setup (Without Docker)

## Installation

1. **Clone the repository:**
        
    ```bash
        git clone https://github.com/s-samadmasud/apple-quality-prediction-deploy.git
        cd brain_tumor_detection_deploy
2. **Create a virtual environment(conda):**

   
      ```bash
            conda create -p venv python==3.10 -y
            conda activate venv/
3. **Install dependencies:**
      ```bash
            pip install -r requirements.txt
4. **Run the application:**
    ```bash
          python app.py
## Local Setup (with Docker)
1. **Clone the repository:**
        
    ```bash
        git clone https://github.com/s-samadmasud/apple-quality-prediction-deploy.git
        cd ai_vision_agent
2. **Build Docker Image:**

   
      ```bash
            docker build -t apple-quality-prediction-deploy .
3. **Run Container:**
      ```bash
            docker run -p 5000:5000 apple-quality-prediction-deploy:latest
4. **Run the application:**
    ```bash
          http://localhost:5000/
## Local Setup (Pull from Docker Hub)
1. **Pull the Prebuilt Docker Image:**

    ```bash
        docker pull samad25/apple-quality-prediction-flask:latest
2. **Run the Prebuilt Docker Image:**
    ```bash            
        docker run -p 5000:5000 docker pull samad25/apple-quality-prediction-flask:latest
3. **Run the application:**
    ```bash
          http://localhost:5000/
##  How It Works

1. The user enters fruit attributes (size, sweetness, etc.) in the web form.  
2. The app converts the input into a **NumPy array**.  
3. The trained **SVM model** (`svc.pickle`) predicts fruit quality.  
4. The result is displayed on a new page (`result.html`) as:
   -  **Good** — if model output > 0.5  
   -  **Bad** — otherwise  

---

##  Example Input

| Feature       | Value  |
|----------------|--------|
| Size           | 5.2    |
| Weight         | 130.0  |
| Sweetness      | 8.5    |
| Crunchiness    | 6.0    |
| Juiciness      | 7.5    |
| Ripeness       | 8.0    |
| Acidity        | 3.2    |

 **Predicted Quality:** `Good`

---

## Important Notes

- Ensure the file **`models/svc.pickle`** exists in the correct path.  
- The model should be trained using **Scikit-learn** and saved via `pickle.dump()`.  
- If you update the model, retrain and re-save it as **`models/svc.pickle`**.

---


## Author

<p align="left">
  <b>Suhal Samad</b><br>
  AI & ML Engineer | Real-Time Computer Vision, Edge AI & Deep Learning<br>
  🔗 <a href="https://metaidigit.com" target="_blank">metaidigit.com</a>
</p>

---
