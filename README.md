[README.md](https://github.com/user-attachments/files/29358522/README.md)
# CAFP Board Motion Approval Form
### Canadian Association of Former Parliamentarians
*Association canadienne des anciens parlementaires*

---

## What this is

A bilingual (English/French) electronic form for CAFP board members to vote on motions and submit their signature. It runs as a single HTML file hosted on GitHub Pages — no server, no database, no cost.

## Contents

| File | Description |
|---|---|
| `cafp_board_approval.html` | The form itself — open this in any browser |
| `README.md` | This file |

## Current Motions (2026–27)

1. **Budget** — That the Board approve the proposed budget attached for the 2026–27 fiscal year.
2. **Membership 365** — That the Board approve the purchase of a new membership system called Membership 365.

## How it works

1. A board member opens the link
2. They choose their preferred language (EN / FR) using the toggle in the header
3. They vote **For**, **Against**, or **Abstain** on each motion
4. They enter their full name and draw their electronic signature
5. On submission, their votes and signature are emailed to the CAFP administrator via Formspree

## Setup instructions

### 1. Get a Formspree account (free)

1. Go to [formspree.io](https://formspree.io) and create a free account
2. Click **New Form** and name it `CAFP Board Votes`
3. Copy your **Form ID** — it looks like `xpwzabcd`

### 2. Add your Form ID to the HTML file

Open `cafp_board_approval.html` in any text editor and find this line near the bottom:

```js
const FORMSPREE_ID = 'YOUR_FORM_ID';
```

Replace `YOUR_FORM_ID` with your actual Formspree ID and save the file.

### 3. Deploy to GitHub Pages

1. In this repository, go to **Settings → Pages**
2. Under **Source**, select the `main` branch and click **Save**
3. GitHub will provide a public URL within a minute, e.g.:
   `https://yourusername.github.io/cafp-board-votes/cafp_board_approval.html`
4. Share this URL with board members by email

## Updating motions

To change or add motions, open `cafp_board_approval.html` in a text editor and update:

- The motion text in the `<div class="motion-text">` blocks (one per motion)
- The French translation in the `translations` object in the JavaScript section
- The motion names in the `motionNames` object for the confirmation summary

After saving, upload the updated file to this repository and the live URL updates automatically.

## Responses

Each submission sends an email to the address linked to your Formspree account containing:

- Board member's full name
- Vote on each motion (for / against / abstain)
- Date and time of submission
- Signature image (as a base64 PNG)

Formspree's free tier allows **50 submissions per month**, which is more than sufficient for board votes.

## Privacy

- No data is stored in this repository
- Submissions are handled by Formspree and delivered to the administrator's email only
- The form does not use cookies or tracking

---

*For technical questions about this form, contact your web administrator.*
