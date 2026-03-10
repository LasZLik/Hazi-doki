# HázDoki – Website

Single-page marketing website for **HázDoki**, a Hungarian home-maintenance and emergency repair service.

---

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire website – HTML structure, CSS styles, and JavaScript in one file |
| `README.md` | This documentation |

---

## How to run

No build process or server required. Open `index.html` directly in any modern browser, or deploy the file to any static web host (e.g. Netlify, GitHub Pages, shared hosting).

---

## Changing images

All image URLs are stored in **one central place** at the top of the `<script>` block inside `index.html`:

```js
const IMAGES = {
    hero:   'https://...',   // Full-screen hero background
    whyUs:  'https://...',   // "Why us" section side image
    services: [
        { src: 'https://...', alt: '...', icon: 'fa-droplet', title: '...', items: [...] },
        { src: 'https://...', alt: '...', icon: 'fa-border-all', title: '...', items: [...] },
        { src: 'https://...', alt: '...', icon: 'fa-bolt', title: '...', items: [...] },
        { src: 'https://...', alt: '...', icon: 'fa-key', title: '...', items: [...] },
    ]
};
```

To swap an image, change the `https://...` URL for the relevant entry. The page renders all images from this config – no image URLs exist anywhere else in the file.

To add or remove a service card, add or remove an object from the `services` array. The slider adjusts automatically.

---

## Contact form

The form currently simulates a submission (shows a success message then resets). To make it actually send an email, choose one of these options:

**Formspree (recommended – free, no server needed)**
1. Sign up at [formspree.io](https://formspree.io)
2. Create a form and copy your endpoint URL (e.g. `https://formspree.io/f/xabcdefg`)
3. Change the `<form>` tag to: `<form action="https://formspree.io/f/xabcdefg" method="POST">`
4. Remove `onsubmit="submitForm(event)"` and the `submitForm` JS function

**PHP (requires PHP hosting)**
Create a `send.php` file next to `index.html` and point the form's fetch call to it.

---

## Fonts & icons

| Resource | Provider | How to change |
|----------|----------|---------------|
| Raleway (headings) | Google Fonts | Edit the `<link>` tag in `<head>` |
| Poppins (body) | Google Fonts | Edit the `<link>` tag in `<head>` |
| Icons | Font Awesome 6 Free | Change `fa-*` class names on `<i>` elements |

---

## Sections (top to bottom)

1. **Navbar** – Fixed, blurred background, collapses to hamburger on mobile
2. **Hero** – Full-screen background image with animated headline and stats
3. **Strip** – 4 trust badges (invoice, speed, guarantee, location)
4. **Services** – Draggable/swipeable card slider (arrows + dots + touch)
5. **Banner** – Red highlight with the key selling message
6. **Why us** – Side-by-side image and 4 feature bullet points
7. **Contact** – Contact details + message form
8. **Footer** – Logo, copyright, nav links

---

## Contact details (to update)

Located in the HTML inside `<section id="contact">`:

- **Phone:** `+36 30 233 1508`
- **Email:** `hazdoki2024@gmail.com`
- **Hours:** Monday – Friday, 08:00 – 20:00
- **Service area:** 17. kerület, Ecser, Pécel, Maglód, Gyömrő, Péteri, Mende, Pusztaszentistván, Sülysáp, Monor

The same phone number also appears in the navbar CTA and floating button – search for `+36302331508` to find all occurrences.
