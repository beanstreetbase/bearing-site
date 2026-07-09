# Bearing

Free, browser-based sales and demand forecasting for small businesses.

**Live at:** [atruebearing.com](https://atruebearing.com)

## What it does

Paste a list of recent numbers — daily sales, foot traffic, bookings, anything tracked over time — and Bearing returns:

- A trend forecast for the next few periods
- An honest confidence range, built from your own data's volatility
- A plain-language recommendation: order more, hold steady, or ease back

Everything runs client-side in the browser. No signup, no backend, no data stored or sent anywhere.

## Stack

Plain HTML, CSS, and JavaScript — a single self-contained `index.html` file. No build step, no dependencies, no framework.

## Files

| File | Purpose |
|---|---|
| `index.html` | The site — landing page, tool, and forecasting logic in one file |
| `favicon.svg` | Browser tab icon |
| `robots.txt` | Search engine crawl rules |
| `sitemap.xml` | Search engine sitemap |
| `og-image.png` | Link preview image for social shares (Facebook, Twitter, Slack, iMessage) |

## Deployment

Hosted on **Cloudflare Pages**, connected to this repo. Any push to `main` auto-deploys to [atruebearing.com](https://atruebearing.com) — no manual upload needed.

To deploy your own copy: fork this repo, connect it as a new Cloudflare Pages project (**Workers & Pages → Create → Pages → Connect to Git**), leave the build command empty, and set the output directory to `/`.

## Forecasting method

A simple linear regression fit to the pasted values, banded by the residual standard deviation of that same data (80% confidence interval). Deliberately simple and explainable rather than a black-box model — the goal is a fast, honest read, not false precision. If dates are included, points are sorted chronologically first.

## License

© Bearing. All rights reserved.
