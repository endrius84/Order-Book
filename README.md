# Order book

A single-file, fully offline app for tracking orders and invoicing them. No server, no accounts, no internet needed — just open `index.html` in a browser.

## Features

- **Orders**: order number (auto-suggests the next one), date, quantity, price per order, customer or note. Value is worked out for you.
- **Paid tracking**: click to stamp an order PAID, or mark several at once.
- **Summary**: order count, units, total value, paid and outstanding. Follows your filters (status, month, search).
- **Invoices**: pick orders, add bill-to details, and see a live preview. Invoice numbers auto-increment and due dates come from your payment terms. Optional VAT.
- **Branding**: logo, company name, address, contact details, VAT/company number, payment details and footer.
- **PDF export**: generated in the browser (jsPDF is bundled in the file).
- **Email**: opens your mail app or webmail (Gmail, Outlook, custom link) with the recipient, subject and message filled in. The PDF downloads alongside, ready to attach.
- **CSV export** of orders.
- **Backup / restore** of all data as a JSON file.

## Running it

```bash
git clone https://github.com/<you>/order-book.git
xdg-open order-book/index.html
```

Or serve it locally so the browser always sees the same address:

```bash
cd order-book && python3 -m http.server 8080
# then open http://localhost:8080
```

## Where your data lives

Everything is stored in the browser's local storage, **not** in this repo. That means:

- Data is tied to one browser **and** one address. Opening the file from a different path, or in a different browser, shows an empty app.
- Clearing browsing data wipes it.
- **Use Settings → Backup → Download backup regularly.** Restore it on any machine with Settings → Restore from backup.

Backup files contain customer and invoice details. `.gitignore` keeps them out of the repo — don't commit them, especially if the repo is public.

## Hosting on GitHub Pages (optional)

Repo → Settings → Pages → Source: *Deploy from a branch*, `main` / root. The app will be at `https://<you>.github.io/order-book/`.

The page is public but your data isn't. It stays in each visitor's own browser, so nobody else can see your orders. Pages on a private repo needs a paid GitHub plan.

## Licence

MIT — see `LICENSE`. Bundled jsPDF is MIT — see `THIRD_PARTY_NOTICES.md`.
