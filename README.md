# Tahoe Lakefront Property Landing Page

This is a static Netlify-ready property landing page for 7600 N Lake Blvd #34.

## Deploy

1. Upload this folder to Netlify or connect it to a Git repo.
2. In Netlify, enable Forms/Form detection.
3. Deploy the site.
4. In Netlify, go to Forms and add email notifications for the `private-showing` form.

Netlify will capture the showing request form because the form is present in static HTML and includes `name="private-showing"` plus `data-netlify="true"`.

## Hero video

The current hero uses `assets/images/meta/hero-poster.jpg` as a static image.

When the hero video is ready:

1. Save the video as `assets/video/hero-video.mp4`.
2. In `index.html`, replace the hero image with the commented `<video>` block directly below it.
3. Keep the poster image as the fallback.

Recommended video settings: MP4/H.264, 1080p, short loop, muted background footage, compressed for web.

## Before launch

Confirm final active-listing facts before publishing: price, MLS status, bed/bath count, square footage, HOA, showing instructions, rental/STR rules, brokerage disclaimer, and any required agent compliance language.


## Krys contact details

The contact block, footer, hidden Netlify form fields, and success page now include:

- Instagram: https://www.instagram.com/krysbenyamein
- Phone: 714-588-1017
- Email: krysbenyamein@gmail.com

Netlify form email notifications are configured inside Netlify, not inside this HTML file. Add krysbenyamein@gmail.com and any team inboxes as notification recipients after deployment.

## Outbound place links

Neighborhood, resort, water-access, airport, grocery, and market cards are clickable. External links open in a new tab. The Ski Country card jumps to the detailed resort section on the same page.


## Netlify Forms fix applied

The showing form now uses Netlify's static HTML detection pattern:

```html
<form name="private-showing" method="POST" netlify netlify-honeypot="bot-field" action="/success/">
  <input type="hidden" name="form-name" value="private-showing">
```

A matching success page exists at both `/success/` and `success.html`. The form posts to `/success/` because extensionless success paths are the safest Netlify pattern. `_redirects` also forwards older `/success.html` and `/thanks.html` paths to `/success/`.

After redeploying, open Netlify Dashboard > Forms and make sure form detection is enabled. Then submit one test lead. If the form appears as `private-showing`, add email notifications for Krys and the real estate team in Netlify Dashboard > Forms > Form notifications.


## Added launch pages
- `/404.html` uses the existing illustrated Tahoe artwork style, not property photography.
- `/accessibility/` includes a simple accessibility statement and Krys contact info.
- `/privacy/` explains form collection and use.
- `/terms/` includes reliable-but-not-guaranteed, buyer verification, financing, and Equal Housing Opportunity language.

## Quick accessibility fixes included
- Visible focus states.
- Decorative icons marked as hidden from assistive tech.
- Audience-toggle inactive copy marked `aria-hidden`.
- Toggle/filter buttons use `aria-pressed`.
- Netlify honeypot field is hidden and removed from tab order.


## Favicon package

The 34 favicon assets are included in `/assets/favicons/` and all static page heads have been patched to reference them.
