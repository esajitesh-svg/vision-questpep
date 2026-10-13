# VisionQuest Cloud core-module repair

Your latest Streamlit deployment logs show `ModuleNotFoundError: No module named 'core'` while `app.py` imports:
- `core.cloud_db`
- `core.cloud_vision`
- `core.voice`

The `core` directory must exist at the root of the same GitHub branch and repository that contains `app.py` (in the latest logs, repository `vision-quest-burger`, branch `main`).

Expected repository layout:

```
app.py
requirements.txt
core/
  __init__.py
  cloud_db.py
  cloud_vision.py
  voice.py
```

Do not upload this ZIP itself to GitHub. Extract it, then place its `core` directory into your local clone of `vision-quest-burger`, at the same level as `app.py`. In GitHub Desktop, commit and push the new files to `main`. If the repository already has a `core` folder, merge these files into it rather than creating `core/core`.

Do not replace `app.py` or `requirements.txt` as part of this repair. The logs show dependency installation succeeded; this repair addresses the missing package path only.
