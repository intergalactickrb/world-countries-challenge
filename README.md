# UniversalFacts.in – World Countries Challenge

A responsive, single-page geography quiz built with HTML, CSS and vanilla JavaScript. Designed to be hosted on GitHub Pages and embedded in Google Sites.

## Included
- 10-question random quiz from a 50-question starter bank
- 20-second timer per question
- Mixed categories and immediate answer explanations
- Daily challenge: same deterministic question set for each visitor on the same local calendar date
- PNG certificate generated in the browser
- PDF certificate using jsPDF CDN
- Challenge-a-friend URL containing the same 10 question IDs
- Device-local leaderboard using localStorage
- Mobile-responsive dark-blue UI

## Important limitations
1. The leaderboard is local to the visitor's browser/device. It is not a shared global leaderboard. A global leaderboard requires a backend/database (for example Firebase or Supabase), security rules, spam protection and privacy disclosures.
2. Daily challenge date uses the visitor's local device date. The same daily set is produced by browsers using the same date.
3. Certificate IDs are client-generated labels, not independently verifiable credentials. The certificate is a virtual game achievement, not an accredited qualification.
4. PDF export loads jsPDF from cdnjs. PNG export is generated locally in the browser. If the CDN is blocked, PNG still works.
5. The starter question bank has 50 manually curated questions. Review and fact-check questions before publishing; expand it over time.

## Deploy to GitHub Pages
1. Sign in to GitHub and create a new **public** repository, e.g. `world-countries-challenge`.
2. Upload `index.html` to the repository root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select branch `main` and folder `/ (root)`, then Save.
6. Wait for GitHub Pages to publish. Your URL will look like `https://YOUR-USERNAME.github.io/world-countries-challenge/`.

## Embed in Google Sites
1. Open your UniversalFacts Google Site in edit mode.
2. Navigate to the page where the game should appear.
3. Choose **Insert → Embed → By URL**.
4. Paste your GitHub Pages URL and select Insert.
5. Resize the embed frame to a useful width and height. A wide section with a height around 1,000–1,200 px is a reasonable starting point; test on mobile.
6. Publish the Google Site and test the published page, not only the editor preview.

If the URL embed does not render in your particular Google Sites setup, use **Insert → Embed → Embed code** and paste:
```html
<iframe
  src="https://YOUR-USERNAME.github.io/world-countries-challenge/"
  width="100%"
  height="1100"
  style="border:0;border-radius:16px;max-width:100%;"
  loading="lazy"
  title="UniversalFacts World Countries Challenge">
</iframe>
```
Replace the example URL with your actual GitHub Pages URL.

## Update the game
Edit `index.html` in GitHub and commit the changes. GitHub Pages will redeploy automatically. Add questions to the `QUESTIONS` array using this format:
```js
{id:"q51",cat:"CAPITALS",q:"Question text?",a:["Option A","Option B","Option C","Option D"],c:2,e:"A short explanation."}
```
`c` is the zero-based index of the correct answer (0–3). Keep IDs unique.

## Test checklist
- Complete a random quiz and check all answer states.
- Let the timer reach zero.
- Complete a daily quiz on two browsers set to the same date and verify the question set matches.
- Use Challenge a friend and open the copied/shared URL in another browser.
- Download both certificate formats.
- Check the leaderboard in the same browser and in a different browser to understand its device-local behaviour.
- Test the published Google Sites page on Android and desktop.
