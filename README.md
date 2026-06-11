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
