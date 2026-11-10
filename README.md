# 🏡 Family Directory & Invitation Manager

A lightweight, responsive web app to manage family members, invitation status, and RSVP tracking with Supabase.

## Features
- Secure login with Supabase Auth
- Add, edit, delete, and search family records
- Filter by family side and invitation status
- Export records as CSV
- WhatsApp and call actions for each contact
- Mobile-friendly dashboard

## Requirements
- A modern browser
- A Supabase project
- A `relatives` table in Supabase

## Supabase table schema

```sql
create table public.relatives (
  id uuid default gen_random_uuid() primary key,
  name text not null,
  relation text not null,
  family_side text not null default 'Paternal',
  phone text,
  city text,
  invitation_status text not null default 'Pending',
  invitation_date date,
  rsvp_status text not null default 'Pending',
  notes text,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now()
);
```

## Setup
1. Open `index.html` in a browser.
2. Make sure your Supabase project is active.
3. Update the Supabase keys in the script section if needed.
4. Log in using your Supabase Auth user.
5. Start adding and managing family records.

## Useful notes
- Keep `relatives` as the database table name unless you change it in the JavaScript.
- If you want to edit data from the browser, enable authentication and add the correct RLS policies in Supabase.

## Deployment
You can host this as a static website on GitHub Pages, Netlify, Vercel, or any other static hosting provider.
