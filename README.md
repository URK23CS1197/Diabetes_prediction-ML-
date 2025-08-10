🩺 Diabetes Prediction Web App
A Flask-based web application for predicting diabetes using a machine learning model. The project is containerized with Docker, automatically tested and deployed using GitHub Actions, and hosted on Render.


Features

        Machine Learning Model: Logistic Regression trained on diabetes dataset.

        Flask API & Web UI: Interactive web form for user health data and instant predictions.

        Containerized: Reliable and cross-platform deployments with Docker.

        CI/CD: Automated build, test, and deployment pipeline via GitHub Actions.

        Cloud Hosting: Live public access via Render.


Technology Stack

      Python 3.10, Flask

      scikit-learn, joblib

      Gunicorn

      Docker

      GitHub Actions (CI/CD)

      Render (Cloud Hosting)

      HTML/CSS (User Interface)


Included Files & Directories

                dia_ml.py — Model training script

                diabetes_model.pkl — Trained model file

                app.py — Main Flask backend application

                /templates/index.html — Web UI for user data entry and prediction

                requirements.txt — Python dependencies

                Dockerfile — Docker build instructions

                .github/workflows/ci_cd.yml — GitHub Actions automation workflow

Local Setup

                Clone the repository:

                bash
                        git clone https://github.com/<your-username>/<repo-name>.git
                        cd <repo-name>


Install dependencies:

                bash
                        pip install -r requirements.txt


Train the model:

                bash
                        python dia_ml.py


Run the app locally:

                bash
                        flask run --host=0.0.0.0 --port=5000

                        
Open in browser:

                http://localhost:5000



Docker Usage

                Build the Docker image:

                bash
                        docker build -t diabetes-flask-app .
                        Run the container:

                bash
                        docker run -p 5000:5000 diabetes-flask-app

                        
Visit in browser:

                http://localhost:5000



CI/CD & Deployment

                Pipeline is configured in .github/workflows/ci_cd.yml:

                Trains the model

                Builds & tests Docker image (health check using curl)

                Deploys to Render upon success

 
 GitHub Actions secrets required:

                RENDER_SERVICE_ID

                RENDER_API_KEY



Render Setup:

                Create a Web Service in Render dashboard

                Connect GitHub repo and branch

                Dockerfile and port 5000 are auto-detected

                

Usage Notes

                The frontend JavaScript fetches predictions from /predict relative URL.

                Ensure diabetes_model.pkl is present before deployment.

                Access logs via Render dashboard or docker logs diabetes-flask-app locally.

                For best results, add a favicon.ico to /static folder.



Troubleshooting

                Prediction not working?

                        Fetch URL in JavaScript must be /predict

                        Backend must load diabetes_model.pkl

                        Review logs for errors
                
                Deployment issues?

                        Confirm Docker CMD and port

                        Ensure secrets and service ID/API key are set

                Use Render logs for debugging


Contribution

                Contributions welcome! Fork the repo, create a pull request, and ensure all automated checks pass.


Author

                NIRANSON
                
GitHub: https://github.com/URK23CS1197/Diabetes_prediction-ML
