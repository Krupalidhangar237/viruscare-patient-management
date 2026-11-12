# VirusCare – HTML, CSS and JavaScript prototype

## Included
- `index.html` – UI structure and forms
- `styles.css` – responsive styling
- `app.js` – role-based workflows, validation, sample data and localStorage persistence

## Run locally
Extract the ZIP and open `index.html` in a browser. For a smoother development experience, open the folder in VS Code and use Live Server.

## Deploy to Vercel
1. Create a GitHub repository.
2. Upload all three files (`index.html`, `styles.css`, `app.js`) to the repository root.
3. Import the repository in Vercel.
4. Select **Other** as framework preset. No build command is required for this static project.
5. Deploy. Vercel will generate a public URL.

You can also deploy the folder using Netlify Drop.

## Demo roles and workflows
**Nurse:** record one daily temperature per admitted patient. Duplicate readings are blocked.

**Doctor:** view daily readings, complete a visit only after today's temperature is recorded, add notes, and recommend discharge when the recovery rule is met.

**Administrator:** register patients (maximum 74 active beds), confirm doctor-recommended discharges, record demo death outcomes, and monitor mortality/success rates.

All roles use the same browser's localStorage. Sign out and sign in as another role in the same browser to see shared changes. Different browsers/devices do not synchronize.

## Rules and assumptions
- Capacity: 74 active admissions.
- One official temperature per patient per calendar date.
- Routine doctor visit requires same-day temperature entry.
- Recovery check: three consecutive *previous calendar days* with a recorded temperature below 37.5°C. Missing records do not count.
- Doctor recommends; administrator confirms discharge.
- Mortality = deaths / (deaths + recoveries); success = recoveries / (deaths + recoveries). Active patients are excluded.
- Warning appears when mortality is greater than 15%.

**Clinical caveat:** 37.5°C is an illustrative threshold, not medical advice. The facility's clinical lead must approve the threshold and clarify whether "three full days" means three calendar days or a continuous 72-hour period.

## Limitations
This is a case-study front-end prototype, not a production healthcare system. Demo role selection is not secure authentication. Data is stored only in this browser and is not encrypted or synchronized. Production deployment needs a backend database, secure authentication and authorization, audit controls, backups, privacy safeguards and clinical validation.
