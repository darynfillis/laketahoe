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


## OG Image Update
The Open Graph image is the selected retro FOR SALE poster at assets/images/meta/og-image.jpg, exported at 1200 x 630 for social previews.


## OGv2 / iMessage social preview

The primary social preview image is:

`/assets/images/meta/OGv2.jpg?v=2`

The site uses absolute Open Graph image URLs for better compatibility with iMessage, Facebook, LinkedIn, Slack, and other preview scrapers.

After deploying, test directly:

`https://lakefronttahoevista.com/assets/images/meta/OGv2.jpg?v=2`

Then paste the homepage URL into a new iMessage thread. If an older image appears, send the URL with a cache-busting query once:

`https://lakefronttahoevista.com/?v=2`


## OGv3 iMessage fix

Primary OG image is now a root-level image for maximum iMessage compatibility:

`https://lakefronttahoevista.com/OGv3.jpg?v=3`

The site now has one OG/Twitter image block per HTML page and no alternate OG image file references.

After deploy:
1. Open `https://lakefronttahoevista.com/OGv3.jpg?v=3` directly.
2. Open `https://lakefronttahoevista.com/?v=3` in Safari.
3. Paste `https://lakefronttahoevista.com/?v=3` into a new iMessage thread.

If iMessage still shows the old card, delete the thread and try again because Apple caches previews aggressively.


## OGv4 iMessage no-crop fix

The previous OG image was cropped to fit 1200x630, which trimmed the top and bottom of the poster. OGv4 preserves the full poster inside a 1200x630 canvas with safe padding.

Primary image:

`https://lakefronttahoevista.com/OGv4.jpg?v=4`

Test after deployment:
1. Open `https://lakefronttahoevista.com/OGv4.jpg?v=4` directly.
2. Paste `https://lakefronttahoevista.com/?v=4` into a brand-new iMessage thread.
3. If iMessage still shows the old card, delete the thread and test again. Apple caches link previews aggressively.


## OGv5 iMessage edge-fill version

OGv5 removes the beige padding. It preserves the full poster without cropping by using a blurred full-bleed version of the artwork behind the fitted poster.

Primary image:

`https://lakefronttahoevista.com/OGv5.jpg?v=5`

Test:
`https://lakefronttahoevista.com/?v=5`


## OGv6 correct-size poster

OGv6 uses the correctly-wide poster artwork and resizes it directly to 1200x630.
No crop. No beige padding. No blurred background.

Primary image:

`https://lakefronttahoevista.com/OGv6.jpg`

Test after deploy:

`https://lakefronttahoevista.com/OGv6.jpg`

Then paste this into a brand-new iMessage thread:

`https://lakefronttahoevista.com/?v=6`


## Matching 34 favicon

The favicon now uses the same circular 34 badge from the OG poster artwork.

Primary favicon paths:

`/favicon.ico`
`/favicon-32x32.png`
`/apple-touch-icon.png`
`/site.webmanifest`

If the old favicon still appears after deploying, hard refresh or open a private window. Browsers cache favicons aggressively.




## Bathroom count update

Bathroom count has been updated to read `3-1/2 bathrooms`.


## Matterport embedded

The Matterport 3D tour is now embedded in the `#matterport` section.

Matterport URL:

`https://my.matterport.com/show/?m=UcK6pKLyEj3`


## Final domain update

The production domain is now:

`https://lakefronttahoevista.com`

All Open Graph, Twitter, canonical, robots, and sitemap references have been updated to this domain.

Key test URLs after deploy:

`https://lakefronttahoevista.com/`
`https://lakefronttahoevista.com/OGv6.jpg`
`https://lakefronttahoevista.com/favicon.ico`
`https://lakefronttahoevista.com/success/`
`https://lakefronttahoevista.com/accessibility/`
`https://lakefronttahoevista.com/privacy/`
`https://lakefronttahoevista.com/terms/`
`https://lakefronttahoevista.com/sitemap.xml`

For iMessage testing, paste this into a brand-new thread:

`https://lakefronttahoevista.com/?v=7`

## Postcard brand update

The site has been updated to match the property postcard direction:

- Font family changed to Poppins.
- Hero headline now uses the postcard-style yellow fill and black outline.
- Primary brand yellow: `#F1E12E`.
- Outline / stroke color: `#000000`.
- Supporting palette pulled from the postcard art: forest green, deep teal, warm sky, wood/stone tones.


## Final magazine/video update

Updates included:
- Hero now uses `assets/video/tahoe-long-shot.mp4`.
- Hero video is set to `autoplay muted loop playsinline`.
- Body copy uses Montserrat and displays in all caps.
- Display/hero text keeps the bold postcard-inspired Poppins treatment.
- Site palette updated from the magazine/postcard direction.
- Black background treatments have been replaced with deep Tahoe teal/forest tones.
- A new `#story` section uses the supplied Chateau Chamonix listing narrative.

Hero video compressed: `True`.

## No-magazine / audience toggle update

The visible Property Magazine section has been removed from the site.

The hero buyer-profile toggle has been restored with three choices:
- Owner
- Second Home
- Investor

The site still keeps the hero video, Matterport embed, Montserrat body copy, final domain, OG image, price, bathroom count, and 34 favicon.

## Eyebrow contrast update

Eyebrow labels now use a high-contrast yellow pill treatment:
- Fill: `#F1E12E`
- Text and border: `#000000`
- Removed the low-contrast decorative line before the eyebrow text.

## Financing role and hero eyebrow spacing update

- Moved the hero address/price eyebrow down slightly.
- Changed the lender-card role text, including "Your financing guide," to deep Tahoe teal for better contrast on the light card background.

## Hero address / toggle / nav fix

- Reduced and tightened the hero address/price pill.
- Moved the hero address/price pill down from the nav.
- Improved contrast for the "I'm looking as..." label.
- Tightened desktop nav spacing so links do not clip on wide/tablet viewports.


## Expanded gallery update

Added 20 new optimized gallery images:
- aerial shoreline and private beach views
- pool and waterfront amenities
- lower-level living, kitchenette, laundry and interior images

Optimized full images are in:
`assets/images/gallery/`

Optimized thumbnails are in:
`assets/images/gallery/thumbs/`

The lightbox automatically includes the new images because it reads every image inside `.gallery-grid`.


## Second expanded gallery update

Added 14 more optimized gallery images:
- dining and kitchen views
- primary bedroom and bathrooms
- front door, covered balcony and lake views
- walkout patio, lawn, hammock, shoreline and kayak storage

Gallery now includes 50 images total.


## OGv7 full-site share image update

The new share image is now the primary OG/Twitter image across every HTML page.

Primary image:

`https://lakefronttahoevista.com/OGv7.jpg`

Also saved as:

`/assets/images/meta/OGv7.jpg`
`/assets/images/meta/og-image.jpg`

After deployment, test:

`https://lakefronttahoevista.com/OGv7.jpg`
`https://lakefronttahoevista.com/?v=8`

Use a brand-new iMessage thread because Apple caches link previews aggressively.

## Mobile selector, map, and gallery thumbnail update

- Fixed the mobile Owner / Second Home / Investor selector so it displays as a compact three-tab segmented control.
- Added a Google Maps embed section for 7600 N Lake Blvd, Unit 34.
- Updated the Location nav link to jump to the map section first.
- Gallery image paths are now root-relative.
- Gallery thumbnail URLs include `?v=50` to avoid stale cached 404s.
- Gallery thumbnails now fall back to the full image if the thumbnail fails.
- `_headers` explicitly serves WebP gallery images as `image/webp`.

## Thumbnail dependency removed

The gallery no longer uses `/assets/images/gallery/thumbs/`.

All gallery grid images now load directly from:

`/assets/images/gallery/`

This avoids broken thumbnails when GitHub or Netlify uploads miss the `thumbs` folder.

## Gallery image tag fix

Fixed malformed gallery image tags caused by a misplaced `onerror` attribute after the self-closing slash.

Gallery images now use valid HTML like:

`<img src="/assets/images/gallery/file.webp?v=52" ...>`

Verified:
- 50 gallery image `src` paths
- 50 gallery `data-full` paths
- 0 missing image files

## Gallery visible fix

This version forces gallery images to render visibly on the page:
- removed gallery cache-busting query strings
- removed lazy loading from gallery images
- made first 12 gallery images eager/high priority
- added final CSS override to force gallery images visible inside each tile
- verified 50 gallery image paths and 50 lightbox image paths

## Mobile hero / CTA contrast update

- Mobile sticky "Book Showing" text on the yellow side now uses deep green for contrast.
- Mobile hero content has been moved closer to the nav bar.
- The map disclaimer line remains removed.
- Added a Google Analytics placeholder comment in `index.html`.
- Added `GOOGLE_ANALYTICS_INSTRUCTIONS.txt`.
