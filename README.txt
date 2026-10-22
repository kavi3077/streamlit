AI-enabled Web Application - Google Cloud Run (No Dockerfile)

FILES
-----
app.py             Streamlit application
requirements.txt   Python dependencies

DEPLOYMENT ON WINDOWS
---------------------
1. Install Google Cloud CLI:
   https://cloud.google.com/sdk/docs/install

2. Open Command Prompt and sign in:
   gcloud init

3. Change directory to this extracted project folder. Example:
   cd %USERPROFILE%\Downloads\ai-enabled-web-app

4. Set your Google Cloud project ID:
   gcloud config set project YOUR_PROJECT_ID

5. Enable the required APIs:
   gcloud services enable run.googleapis.com cloudbuild.googleapis.com

6. Deploy directly from source (no Dockerfile required):
   gcloud run deploy ai-enabled-web-app --source . --region asia-south1 --allow-unauthenticated

7. When deployment completes, open the Service URL printed in the terminal.

NOTES
-----
- Replace YOUR_PROJECT_ID with your actual Google Cloud project ID.
- Ensure billing is enabled and you have permission to deploy.
- This command uses Google Cloud buildpacks to build from source; it does not require you to create or maintain a Dockerfile.
- Public access means anyone with the URL can use the app.
