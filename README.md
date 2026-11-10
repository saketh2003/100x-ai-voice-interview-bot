# 100x AI Interview Twin

A Streamlit voice-enabled AI interview assistant powered by Groq chat and Whisper transcription. Interviewers can record or type questions and listen to spoken answers without installing anything or entering an API key.

## Deploy on Streamlit Community Cloud

1. Upload `app.py`, `profile.txt`, `requirements.txt`, `README.md`, and `.gitignore` to a **public GitHub repository**.
2. At https://share.streamlit.io choose **Create app** / **Deploy a public app from GitHub**.
3. Select the repository, branch `main`, and entrypoint `app.py`.
4. In **Advanced settings → Secrets**, enter:

   ```toml
   GROQ_API_KEY = "your_groq_api_key_here"
   ```

5. Deploy. Open the public URL in a private/incognito window and test recording, text, and Speak Answer.

## Personalize before submitting

Edit `profile.txt` with true details about the applicant. The template deliberately avoids inventing personal information. Until personalized, the bot may state that it does not have enough information.

## Notes

- Groq free tier has limits; check model availability and adjust the model in `app.py` if necessary.
- Microphone recording is handled by Streamlit; voice transcription uses Groq Whisper.
- Spoken playback uses the visitor's browser speech synthesis and requires a click on Speak Answer. Availability varies by browser/device.
- Never upload your API key or `.env` to GitHub.
