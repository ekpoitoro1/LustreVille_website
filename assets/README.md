# Meridian Learning Academy

A simple, responsive website for an online tutoring academy serving pupils from Class 1 upward, worldwide. Guardians and pupils can browse subjects and tutors, read the blog, send an enquiry, enrol for tutorials and chat with the site assistant. The design uses a navy-blue and gold palette.

Plain HTML, CSS and JavaScript. There is no build step and nothing to install.

## Features

- **Home**: hero, subject overview, how enrolment works, why families choose us, testimonials, calls to action
- **Subjects**: English, Mathematics, French, IT, Science, Data Science, Coding, Study Skills, with class ranges
- **Our Tutors**: tutor portfolio cards with qualifications, subjects, time zone and rating
- **Blog**: post cards by category
- **Enquiry**: contact form and other contact channels
- **Enrol**: enrolment form with multi-subject selection, class format and time zone
- **Chat widget**: floating assistant with quick replies and keyword answers
- Single-page navigation, mobile menu, visible keyboard focus, reduced-motion support

## Project structure

```
.
├── index.html        # All pages and the chat widget markup
├── css/
│   └── style.css     # Full design (blue and gold theme, responsive layout)
├── js/
│   └── script.js     # Page navigation, form messages, chat widget
├── .gitignore
└── README.md
```

`index.html` loads the other two files with relative paths:

```html
<link rel="stylesheet" href="css/style.css">
<script src="js/script.js" defer></script>
```

Keep the folder structure and the lowercase file names exactly as they are. Vercel and GitHub Pages are case-sensitive, so `CSS/Style.css` would not load.

## Run locally

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

Fonts (Fraunces, Inter, Space Mono) load from Google Fonts, so the first load needs an internet connection. Offline, the site falls back to system fonts.

## Push to GitHub

```bash
git init
git add .
git commit -m "Initial commit: Meridian Learning Academy website"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git push -u origin main
```

Note that GitHub's file view and "Raw" links show source code, not the rendered site. Use Vercel (below) or GitHub Pages to see it running.

## Deploy and preview on Vercel

1. Sign in at [vercel.com](https://vercel.com) and choose **Add New, then Project**.
2. Import your GitHub repository.
3. Set **Framework Preset** to **Other**. Leave **Build Command**, **Output Directory** and **Install Command** empty, and keep the **Root Directory** as `./`.
4. Click **Deploy**.

Vercel serves `index.html` from the repository root. Every push to `main` redeploys the production site, and every pull request or other branch gets its own preview URL. No `vercel.json` is needed.

## Current behaviour and limits

- Forms validate in the browser and show a success message, but **nothing is stored or sent**. Connect a backend before using them for real enquiries.
- The chat assistant is rule-based (keyword replies), not an AI model, and conversations are not saved.
- Tutors, blog posts and testimonials are static content written in `index.html`.
- All pages share one URL, because navigation happens in JavaScript. Refreshing always returns to Home.
- The contact email and phone number are placeholders; replace them.
- Blog "Read the full post" links are placeholders; there is no single-post page yet.

## Troubleshooting

- **Page appears without styling**: check that `css/style.css` exists next to `index.html` with exactly that name and folder. In the browser, press F12, open the Network tab and reload to see if `style.css` returns 404.
- **Old version still showing**: hard refresh with Ctrl+Shift+R (Cmd+Shift+R on Mac).

## License

Add a license of your choice (for example MIT) before making the repository public.
