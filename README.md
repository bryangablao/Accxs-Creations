# Accxs Creations Website

A single-file website for **Accxs Creations**, a software and web agency based in Davao City, Philippines. Everything (home page, customer reviews, staff dashboard, privacy policy and terms of service) lives in one `index.html`. There is nothing to build or install.

## What's inside

| Page | Address | What it does |
|---|---|---|
| Home | `#/` | Hero, purpose and goal, services, personal websites, Code Studio, project quote form, customer review strip, contact |
| Customer Reviews | `#/reviews` | Customers sign in with Google or Facebook and post, edit or remove one review |
| Staff Dashboard | `#/dashboard` | Staff-only: project quotes, progress tracking, archive and logs, account and role management |
| Privacy Policy | `#/privacy` | Full policy with section menu, browser preference tools and print |
| Terms of Service | `#/terms` | Full terms with section menu, key terms and scope pop-ups, and print |

Section links work too, for example `#/home/contact` or `#/home/codestudio`.

## Features

- **One shared header and footer** across all pages, with a sliding line under the active menu item.
- **Day and night mode.** The first visit follows the device setting, the toggle remembers your choice, and everything (including scrollbars and icons) adapts.
- **Responsive** for phones, iPads and desktops. Wide tables and code scroll inside their own box instead of widening the page.
- **Self-contained icons.** All icons are embedded in the file as vector images, so there are no missing-icon boxes and no icon font to load.
- **Live Philippine Standard Time** in the footer.
- **Back-to-top button**, smooth page transitions, and reduced motion for people who turn animations off.
- **Print-friendly** Privacy and Terms pages.

## Running it

1. Put `index.html` on any web host, or open it directly in a browser.
2. The site needs an internet connection for Tailwind CSS, Google Fonts and Firebase.

Page links use `#`, so no special server settings are needed.

## Firebase

Reviews, quotes and staff sign-in use Firebase (Authentication and Firestore).

| Collection | Used for |
|---|---|
| `customerReviews` | Customer reviews, one per signed-in customer |
| `projectQuotes` | Quote requests from the home page and their progress in the dashboard |
| `employees` | Staff profiles (name, role, user ID), linked by the account's `authUid` |
| `access` | Access records used by the dashboard |

- **Staff sign in** with their user ID at the `staff.accxscreations.com` email domain.
- **Roles:** Owner, Administrator, Manager, IT Support, Staff. Only Owners and Administrators can manage accounts; Owners, Administrators and Managers can archive records.
- **Security:** the page itself does not protect your data. Make sure your Firestore security rules are deployed so that reviews and quotes can only be read or written by the right people.
- The dashboard only checks staff sign-in while you are on the Dashboard page, so signing in as a customer on the Reviews page is not affected.

## Editing

All five original pages were merged into this one file by a build script. To make changes, edit `index.html` directly:

- **Colours and layout** use Tailwind classes, plus a shared `<style>` block in the head.
- **Menu, theme, routing and icons** are in the small scripts near the end of the file.
- **Each page** sits inside its own `<div data-page="...">` in the `<main id="app">` section.
- **Icons** are written as `<i class="fa-solid fa-name">`. The file contains only the icons it uses, so a new one needs its drawing added to the icon list in the icon script.

## Known limits

- The favicon is built into the file. To use your own image, replace the `rel="icon"` link in the head.
- In a locked-down preview that blocks Google's Firebase servers, the pages still open and Staff Login opens its popup, but sign-in, reviews and quotes will not work until the page is opened normally.
- Brand logos are drawn in one colour that follows the theme, not in their official colours.

## Credits

Icons: Font Awesome Free (CC BY 4.0). Fonts: Inter and Fira Code via Google Fonts. Styling: Tailwind CSS.

&copy; Accxs Creations. All rights reserved.
