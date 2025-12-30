# Portfolio Contact Server

This small Express server provides a single endpoint `/api/send-email` that sends contact form messages to your email using SMTP (via Nodemailer).

Setup

1. Copy the example env and fill in SMTP credentials:

   - Copy `server/.env.example` to `server/.env` and fill in values for `SMTP_HOST`, `SMTP_USER`, `SMTP_PASS`, etc.

2. Install dependencies and run the server:

   ```powershell
   Push-Location 'C:\Users\Shahmeer Qureshii\OneDrive\Desktop\Front End Portfolio\server';
   npm install;
   npm run dev; # or npm start
   Pop-Location
   ```

3. By default the frontend posts to `http://localhost:5000/api/send-email`. If you run the server on a different host/port, set `VITE_API_URL` in the frontend root `.env`.

Serverless option (Vercel)

- You can keep frontend and backend in a single Vercel repo by using the serverless function `api/send-email.js` (already included). In this case you don't need to set `VITE_API_URL` — the frontend calls `/api/send-email` by default.
- Add SMTP env vars in Vercel project settings: `SMTP_HOST`, `SMTP_PORT`, `SMTP_USER`, `SMTP_PASS`, `FROM_EMAIL`, `TO_EMAIL`.

Notes

- Use a trusted SMTP provider (SendGrid, Mailgun, SES, or your SMTP host).
- Do NOT commit real credentials; keep them in the `.env` file.
- If testing locally with Gmail, you may need an App Password or to enable SMTP access for the account.
