# DJ site template

One page: a 3D market-street hero, a booking form, a playlist with a player, upcoming gigs.
Everything lives in `index.html`. No build step and nothing to install.

## 1. Customise it for a DJ (about 15 minutes)

Open `index.html` and edit two places, both near the top:

1. **The `<title>` and `<meta>` tags** (marked `✏️ EDIT`). These control the browser tab and the preview shown when the link is shared on WhatsApp or Instagram.
2. **The `window.DJ = { ... }` block** (also marked `✏️ EDIT`):

| Field | What it does |
|---|---|
| `nameHindi` | Big title over the shop. Any script works (Devanagari, Gurmukhi, English). |
| `nameEnglish` | Used in the footer and in booking emails. |
| `tagline` | The small line under the title. |
| `bookingEmail` | Where requests go if there's no form service. Also shown in the footer. |
| `formEndpoint` | A Formspree URL, so bookings arrive in the DJ's inbox (see step 2). |
| `links` | Spotify, YT Music, Instagram and SoundCloud. Set one to `''` to hide it. |
| `spotifyEmbed` | Optional Spotify player under the playlist. In Spotify: Share → Embed → copy the `src` URL. |
| `sets` | Set types with their lengths. These also become the event-type buttons in the form. |
| `tracks` | Playlist. Add `audio: 'audio/track.mp3'` to play a real preview. Tracks without one play a generated demo beat. |
| `gigs` | Upcoming shows. Dates in the past hide themselves. Add `url` for a ticket link. |

**Real audio previews:** make a folder called `audio` next to `index.html`, put 30–60 second MP3 clips in it, and set each track's `audio` to `'audio/filename.mp3'`. Only use clips the DJ owns or is allowed to share.

## 2. Make the booking form deliver (5 minutes, free)

1. Sign up at https://formspree.io. The free plan allows 50 submissions a month.
2. Create a form and set its email to the DJ's booking address.
3. Copy the form URL (it looks like `https://formspree.io/f/abcdwxyz`) into `formEndpoint`.
4. Send yourself one test booking. Formspree asks you to confirm the first one.

If `formEndpoint` is empty, the form opens the visitor's email app with the request already written.

## 3. Put it online (free)

**Fastest, Netlify Drop:** go to https://app.netlify.com/drop and drag the whole folder in. You get a live link in about 30 seconds. Make a free account so the site stays up.

**GitHub Pages:** create a repository, upload the folder's files, then go to Settings → Pages → Deploy from branch → `main`.

**Vercel:** at https://vercel.com/new, import the repository. No settings are needed.

**Custom domain:** buy one (for example `djname.in` on GoDaddy, Hostinger or Namecheap, about ₹500–900 a year). Add it under the host's Domain settings, then copy the DNS records it shows into the domain registrar. HTTPS is switched on automatically.

## 4. Check before sending to a DJ

- Open the link on a phone. Most DJs will see it there first.
- Press play and submit one test booking.
- Paste the link into WhatsApp to check the preview text.

## Pitching tip

Keep one copy of this folder per DJ (for example `dj-rahul/`, `dj-sana/`) and deploy each one separately. A demo with the DJ's own name and tracks gets far more replies than a generic template.
