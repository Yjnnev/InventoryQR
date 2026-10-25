# LabQR

A QR-code-based lab equipment inventory and monitoring system. Students scan a QR code (or browse the web app directly) to check equipment out by quantity; admins manage the equipment catalog, track who has what, and process returns.

## Overview

Each physical item in the lab (microscope, glassware, tools, etc.) gets a QR code linking to `/item/:id`. Scanning it or just browsing the catalog lets a signed-in student check out some quantity of it (e.g. 1 of 3 microscopes). Only admins can mark a checkout returned, which keeps the audit trail reliable. Every checkout/return is logged, students can see their own borrow history, and admins get an email the moment something's checked out.

## Tech stack

| Layer | Choice |
|---|---|
| Frontend | React (Vite) + React Router |
| Styling | Plain CSS (`index.css`), no framework |
| Backend / DB | Supabase (Postgres) |
| Auth | Google OAuth via Supabase Auth |
| Notifications | Supabase Edge Function + Resend (email) |
| Hosting | Vercel (frontend), Supabase (backend, fully managed) |
