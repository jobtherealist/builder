# LittleNest core MVP preview

The first LittleNest preview is implemented as a native Frappe website page at [`builder/www/littlenest.html`](../builder/www/littlenest.html). On a running Frappe site with this app installed, open `/littlenest`.

For a simple static review, serve `builder/www` from the repository root:

```sh
python3 -m http.server 4173 --directory builder/www
```

Then visit <http://localhost:4173/littlenest.html>.

This is a product preview, not production authentication. The profile and nursery quotes are stored in browser `localStorage`; they do not sync to Frappe or another server. Do not enter real child details or sensitive information. Use **Family profile → Delete local preview data** to clear the prototype data.

Weekly equivalent is calculated from the entered hourly, daily or weekly quote and the selected days and hours. Monthly equivalent is annualised as `weekly equivalent × weeks per year ÷ 12`; weeks per year defaults to 52. These calculations compare user-entered rates only and do not check nursery prices, childcare funding or eligibility.

Next, connect the page to Frappe authentication and owner-scoped profile and quote records, then move persistence out of local storage.
