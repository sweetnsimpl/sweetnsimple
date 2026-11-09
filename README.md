# Sweet n Simple — Modern & Minimal

A responsive handmade chocolate catalogue for **Sweet n Simple**, built with static HTML/CSS/JavaScript for **free GitHub Pages hosting**.

## Website address
After enabling Pages, the site will be at https://sweetnsimpl.github.io/sweetnsimple/

## Enable GitHub Pages
1. Open https://github.com/sweetnsimpl/sweetnsimple/settings/pages
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select **main** and **/(root)**, then **Save**.
4. Open https://sweetnsimpl.github.io/sweetnsimple/ once deployment completes.

## Connect Google Sheets (editable menu)
1. Create a Google Sheet and import `menu-template.csv`.
2. Update product rows: `name`, `category`, `description`, `price`, `image`, `badge`, `available`.
3. Under **File → Share → Publish to web**, select the **menu tab** and **Comma-separated values (.csv)**. Publish and copy the CSV URL.
4. Edit `index.html` on GitHub, find `const CONFIG=` near the bottom, and paste the published CSV URL into `googleSheetCsvUrl` (between the quotes), then commit the change.

Sample configuration:
```js
const CONFIG={
  googleSheetCsvUrl:"https://docs.google.com/spreadsheets/d/e/YOUR_PUBLIC_ID/pub?output=csv",
  whatsappNumber:"919876543210",
  instagramUrl:"https://www.instagram.com/_sweet_n_simple/"
};
```

**Never use the example WhatsApp number.** Enter your real WhatsApp Business number with country code and digits only, and commit. Product enquiry buttons will then open WhatsApp with a prefilled message including product name and price. Until configured, buttons open Instagram instead.

**Product prices:** `250` displays as `₹250`. Use `Starting at ₹250` or `Price on request` for variable products.

**Product images:** Use publicly accessible direct HTTPS image URLs in the `image` column. Image URLs must resolve directly to a photo, rather than a private Google Drive page. You can also upload images to an `assets/` folder in this repository and use `assets/photo.jpg`, but then adding photos requires uploading to GitHub. Google Sheets lets you change which image URL appears without editing code.

Set `available=No` to hide a product.

**Note:** The published CSV is public. Do not include customer names, phone numbers or order details. Google may cache published CSV updates, so menu changes can take time to appear. If cross-origin fetch is blocked, use an endpoint that supports CORS.

## Before sharing with customers
- Add your business WhatsApp number
- Publish and connect the product Sheet
- Replace sample products and prices with confirmed details
- Replace emoji placeholders with your own product photos
- Test WhatsApp links and product search on mobile

This is a product enquiry catalogue, not an online payment/checkout system. No paid hosting or backend is required.