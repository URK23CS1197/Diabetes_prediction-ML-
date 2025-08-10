🩺 Diabetes Prediction Web App
A Flask-based web application for predicting diabetes using a machine learning model. The project is containerized with Docker, automatically tested and deployed using GitHub Actions, and hosted on Render.

Features
Machine Learning Model: Logistic Regression trained on diabetes dataset.

Flask API & Web UI: Interactive web form for user health data and instant predictions.

Containerized: Reliable and cross-platform deployments with Docker.

CI/CD: Automated build, test, and deployment pipeline via GitHub Actions.

Cloud Hosting: Render platform for live public access.

Technology Stack
Python 3.10, Flask

scikit-learn, joblib

Gunicorn

Docker

GitHub Actions (CI/CD)

Render (cloud hosting)

HTML/CSS (user interface)

Included Files
dia_ml.py - Model training script.

diabetes_model.pkl - Trained model file.

app.py - Main Flask backend application.

/templates/index.html - Web UI for user data entry and prediction.

requirements.txt - Python dependencies.

Dockerfile - Docker build instructions.

.github/workflows/ci_cd.yml - GitHub Actions automation workflow.

Local Setup
Clone the repo

bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
Install dependencies

bash
pip install -r requirements.txt
Train the model

bash
python dia_ml.py
Run the app locally

bash
flask run --host=0.0.0.0 --port=5000
Open http://localhost:5000 in your browser.

Docker Usage
Build the Docker image

bash
docker build -t diabetes-flask-app .
Run a container

bash
docker run -p 5000:5000 diabetes-flask-app
Visit http://localhost:5000 in your browser.

CI/CD & Deployment
Automated pipeline configured in .github/workflows/ci_cd.yml:

Trains the model.

Builds & tests Docker image (health check using curl).

Deploys to Render upon success.

Set the following secrets in your GitHub repository:

RENDER_SERVICE_ID

RENDER_API_KEY

On Render, create a Web Service connected to your GitHub repo.

Ensure the Dockerfile uses the correct CMD ["gunicorn", "app:app", "-b", "0.0.0.0:5000"] directive.

The app binds to port 5000 as required by Render.

Usage Notes
The frontend JavaScript fetches predictions from the /predict relative URL to ensure compatibility across local and deployed environments.

Ensure diabetes_model.pkl is present in the project root and committed or generated during CI to avoid model loading errors.

Consider adding a favicon.ico in the static folder for a polished user experience (avoids 404 errors for favicon requests).

Logs are accessible via Render dashboard and locally with docker logs diabetes-flask-app for troubleshooting.

Modify the form validation or UI as needed to improve user experience.

Troubleshooting
Prediction not working or no response:
Verify the fetch call's URL is relative (e.g., /predict), not hardcoded to localhost.
Check that the model file diabetes_model.pkl exists in the deployment.
Review backend logs for exceptions.

Container fails to start or connect:
Confirm Docker CMD syntax is in exec JSON array form.
Verify ports are exposed and mapped correctly.
Allow adequate startup time before health checks.

Render deployment issues:
Ensure GitHub secrets are correctly set.
Verify Render service is configured to listen on port 5000 with correct start command or Dockerfile.
Use Render logs to identify errors or crashes.

Contribution
Contributions are welcome! Please fork the repository and submit pull requests for bug fixes or improvements. Ensure tests pass and changes align with project goals.


Author
NIRANSON

GitHub: https://github.com/URK23CS1197/Diabetes_prediction-ML-.git

