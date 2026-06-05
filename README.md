# MealLens

Snap a photo of a meal and get an AI estimate of calories, protein, fat, and carbs — with portion editing, a daily log, trend charts, blood-sugar-aware alerts, and CSV reports. It runs entirely in your browser; there's no server.

## Use it

Open the page (the hosted URL, or `index.html` locally in Chrome/Safari), tap the **gear** icon, paste your **Anthropic API key** (`sk-ant-...`), set your goals, and start adding meals.

## Host it free on GitHub Pages

1. Create a new GitHub repository, e.g. `meallens`.
2. Upload `index.html` (and this README) into the repo.
3. Go to **Settings → Pages**. Under **Source**, choose **Deploy from a branch**, set the branch to **main** and the folder to **/(root)**, and **Save**.
4. Wait about a minute. Your app is live at `https://<your-username>.github.io/meallens/`.

On your phone, open that URL and use **Add to Home Screen** for an app-like icon.

## Your API key is safe to commit

The key is **not** in the code. You enter it at runtime, and it's stored only in your browser's local storage on your own device — it is never written into the file or sent to GitHub. A public repo therefore exposes no secret. Anyone who opens your hosted page just sees a prompt for *their own* key; they can't use yours.

**The one rule:** don't paste your key into the source file.

## Notes

- Each photo analysis calls the Anthropic API with your key (typically a fraction of a cent per photo).
- Your data — logged meals, goals, alert settings, and the key — is stored per-site in your browser. Moving from the local `file://` copy to the hosted `https://` URL starts with an empty log, because browsers treat them as different sites.
- The default model is set near the top of the file (`const MODEL = ...`); switch it to a cheaper model there if you like.
- Nutrition figures are estimates from a photo and are not medical advice.
