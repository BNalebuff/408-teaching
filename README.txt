Negotiation Journal Feedback Tool
==================================

FILES
-----
  app.py              — main server (replaces server.py)
  static/index.html   — web interface
  requirements.txt    — Python dependencies
  README.txt          — this file


──────────────────────────────────────────
OPTION A: RUN LOCALLY
──────────────────────────────────────────

1. Install dependencies (one time):
   pip3 install -r requirements.txt

2. Set your API key:
   Mac/Linux:  export ANTHROPIC_API_KEY=sk-ant-...
   Windows:    set ANTHROPIC_API_KEY=sk-ant-...

3. Start the server:
   python3 app.py

4. Open browser: http://localhost:8765


──────────────────────────────────────────
OPTION B: DEPLOY TO RENDER.COM (free, for TAs)
──────────────────────────────────────────

1. Create a free account at https://render.com

2. Push this folder to a GitHub repository:
   git init
   git add .
   git commit -m "Journal feedback tool"
   (create a repo on github.com, then follow their push instructions)

3. On Render.com:
   - Click "New" → "Web Service"
   - Connect your GitHub repo
   - Settings:
       Build Command:   pip install -r requirements.txt
       Start Command:   gunicorn app:app
       Environment:     Python 3

4. Add your API key as an environment variable:
   - Go to your service → "Environment"
   - Add: ANTHROPIC_API_KEY = sk-ant-your-key-here

5. Click "Deploy" — Render gives you a public URL like:
   https://your-app-name.onrender.com

   Share that URL with your TAs.

NOTE: Free Render instances spin down after 15 min of inactivity
and take ~30 seconds to wake up on the next visit. Upgrade to
the $7/month plan to keep it always on.


──────────────────────────────────────────
USING THE TOOL
──────────────────────────────────────────

1. Upload a student journal (PDF, DOCX, or TXT) or paste text
2. Fill in student name, cohort, and check Nexxtoil flags
3. Click "Generate Feedback"
4. Review and edit the feedback cards as needed
5. Adjust the grade if needed
6. Click "Download Annotated File" to get a new PDF or DOCX
   with the feedback appended as a formatted page
7. Or click "Copy All" to copy feedback to clipboard
