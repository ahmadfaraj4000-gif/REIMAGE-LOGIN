# RE IMAGE Client Login Portal

Customer portal for login.reimagebs.com.

## Local setup

```bash
npm install
cp .env.example .env.local
npm run dev
```

Add your Supabase project URL and anon key to `.env.local`.

## Supabase setup

Run `supabase/login-portal.sql` in the Supabase SQL editor.

Before running it, change `reimagebs@gmail.com` to the email you use for your admin account if needed.

## What this portal does

- Customer signup/login through Supabase Auth
- Submit a service request into the same `start_requests` table your admin portal already reads
- Customer can see status as Received / Opened / Confirmed / etc.
- Customer can message your team inside each request
- Messages save to `request_messages`

## Test flow

1. Start the app with `npm run dev`
2. Create a customer account
3. Submit a request
4. Open the admin portal and confirm it appears in `start_requests`
5. Change the status in admin
6. Refresh the client portal and confirm customer sees the matching status
