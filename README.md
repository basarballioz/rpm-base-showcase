# RPMBase

> A digital garage for the car you own. Track service, fuel, and costs on iPhone and Android. The website explains the product and ships tools that do not need an account.

Solo-built. The garage app is iOS and Android. The public site is live at [rpmbase.app](https://rpmbase.app). Store listings are not the homepage yet: until they are, [Download](https://rpmbase.app/download) is the waitlist. Source is private. This repo is the public engineering summary.

I built it because car ownership usually lives in folders, photos, and memory. I wanted a private log for the car I already drive, not a classifieds board and not a 18,000-model catalogue.

## What I shipped

Website, mobile app, and API. Waitlist and SEO. Store billing when the listings go live. If it ships, I own it.

Three calls that keep RPMBase from becoming a second RPMVault:

- **Garage on the phone.** Service, fuel, expenses, reminders, documents, Ask, and PDF live in the app. rpmbase.app is education, calculators, and download. It does not host your vehicle records.
- **No catalogue, no public listing.** The product is the car you own. There is no browseable inventory and no public vehicle page.
- **Store billing only.** Premium is App Store or Google Play. There is no checkout on the website.

| | Website | App |
| --- | :---: | :---: |
| Guides, calculators, SEO, waitlist / download | ✅ | |
| Garage: service, fuel, expenses, reminders, documents | | ✅ |
| Ask (garage context) and PDF export | | ✅ |
| Device calendar and push for upcoming work | | ✅ |
| Premium (App Store / Play) | | ✅ |

The website is English, Turkish, Spanish, and German. The app is English and Turkish. Ask is informational, not a workshop.

## Stack

| | |
| --- | --- |
| Website | Next.js 15, React 19, Tailwind CSS 4 |
| Mobile | Expo SDK 57, React Native 0.86 |
| API | Node.js, Express 5, Vercel |
| Data | MongoDB Atlas |
| Auth | Firebase: email, Google, Sign in with Apple |
| Billing | App Store and Google Play, verified on the server |

```
Website (Next.js)     public pages, no garage data
                      rpmbase.app

iOS / Android    ─── HTTPS, signed-in requests ─► API (Node / Express)
                                                  │
                                                  ├─ MongoDB
                                                  ├─ Firebase Auth
                                                  └─ App Store / Play billing
```

Private garage data is available only to a signed-in account in the app. Implementation details stay with the private source.

Product screenshots (no plates, VIN, or documents) will land in `screenshots/` next.

_README only for now. Source is private. All rights reserved._
