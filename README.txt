# ZARO — GitHub Pages + Admin

## Files
- `index.html` — public ZARO website
- `admin.html` — private admin dashboard
- `supabase-config.js` — Supabase public URL + anon/publishable key
- `supabase.sql` — database + storage setup

## One-time setup
1. Create/open your Supabase project.
2. Open **SQL Editor** and run `supabase.sql`.
3. Go to **Authentication → Users → Add user** and create the email/password you will use for ZARO admin.
4. Copy your Supabase **Project URL** and **anon/publishable key** into `supabase-config.js`.
5. Upload all four files to the same GitHub Pages repository.
6. Open `admin.html` from your GitHub Pages URL and sign in.
7. Add your real WhatsApp number under **Settings**.

### Important security note
Never put the Supabase `service_role` / secret key in GitHub Pages. Only the public anon/publishable key belongs in `supabase-config.js`.

## What the admin can control
- Add products
- Upload product photos
- Edit names in English/Arabic
- Edit price
- Edit category
- Edit sizes
- Edit stock
- Publish/hide products
- Delete products
- View orders saved in Supabase
- Change order status
- Change WhatsApp number
- Change delivery fee
- Edit basic store settings

## Orders
The current public checkout in the supplied design sends the order to WhatsApp. The `orders` table is included so the site can also store orders in Supabase once order-saving is enabled in the public checkout.

## Note about the current public checkout
The current design keeps the WhatsApp checkout behavior. Product management is cloud-backed through Supabase, so products added/edited in Admin can appear on the public website for visitors.

## GitHub Pages
Use the repository root for these files and enable GitHub Pages from the branch/folder you normally use. `index.html` must remain in the published root.

### Orders
Public checkout now attempts to save each order to the `orders` table and then opens WhatsApp. If the database is temporarily unavailable, WhatsApp checkout still proceeds.
