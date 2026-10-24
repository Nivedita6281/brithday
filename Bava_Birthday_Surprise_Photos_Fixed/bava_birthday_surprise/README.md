# Bava's Birthday Surprise 💗

A mobile-friendly romantic birthday page built with Flask + HTML/CSS/JavaScript.

## Run locally

1. Install Python 3.10+.
2. Open a terminal in this folder.
3. Create and activate a virtual environment (optional but recommended):
   - Windows PowerShell: `py -m venv .venv` then `.\.venv\Scripts\Activate.ps1`
   - macOS/Linux: `python3 -m venv .venv` then `source .venv/bin/activate`
4. Install dependencies: `pip install -r requirements.txt`
5. Start it: `python app.py`
6. Open `http://127.0.0.1:5000` on your computer.

## Deploy free with Render + GitHub

1. Create a GitHub account if you don't already have one.
2. Create a **new public repository** named `bava-birthday-surprise`.
3. Upload the contents of this folder to the repository (the files themselves, not the ZIP).
4. Sign in to Render and choose **New + → Web Service**.
5. Connect GitHub and select `bava-birthday-surprise`.
6. Render should detect `render.yaml`. If it asks for settings, use:
   - Build command: `pip install -r requirements.txt`
   - Start command: `gunicorn app:app`
   - Instance plan: Free (if available to your account/region)
7. Click **Create Web Service** and wait for the deployment to finish.
8. Copy the `https://...onrender.com` URL and send it to Bava.

Free hosting availability and sleep/cold-start behavior can change. If Render's free plan is not offered, use another Flask-compatible host with the same build/start commands.

## Personalize before sharing

- Open `templates/index.html` and edit the letter text.
- Add your own photos to `static/` and change the `PHOTO_MEMORIES` list in `templates/index.html` to use them, e.g. `"/static/us1.jpg"`.
- For music, add an MP3 file you have permission to use as `static/birthday-song.mp3`. Mobile browsers usually require the recipient to tap the music button before playback.
- Preview on your phone before sending. Don't upload private or sensitive photos to a public repository; use only images you're comfortable making publicly accessible.


## Set up Kannoramaai from 0:50

The page has a music button configured to use an official YouTube embed starting at 50 seconds. To avoid redistributing copyrighted audio, it does not include a downloaded song file.

1. Open `templates/index.html`.
2. Find `const YOUTUBE_VIDEO_ID = 'ADD_OFFICIAL_VIDEO_ID';`.
3. Replace `ADD_OFFICIAL_VIDEO_ID` with the video ID from an official/licensed YouTube upload of **Kannoramaai** by Pogan, Ankith Jain, Dharshana Vijayan & Stupid MonkeyZ. The ID is the part after `v=` in a YouTube link (or after `youtu.be/`).
4. Save and redeploy the site. Bava must tap the music button to start playback; mobile browsers generally block autoplay until a user interaction.


## Personal photos and song
The gallery includes the photos supplied for this birthday surprise. The music button uses the YouTube link provided (`ssFveirNpic`) and requests playback starting at 0:50. The player is kept visually offscreen; playback begins only after Bava taps the music button, as mobile browsers require user interaction. The song is streamed from YouTube, not copied into this project.

Gallery update: photos use `object-fit: contain` so the full image is visible without trimming. The “Always US” card repeats the favourite first photo.
