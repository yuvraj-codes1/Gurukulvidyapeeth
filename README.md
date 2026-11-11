# Gurukul Vidyapeeth Coaching Institute – Dwarka Mor

Official website for Gurukul Vidyapeeth Coaching Institute, Dwarka Mor, New Delhi. It is a fast, single-page site built with plain HTML, CSS and JavaScript, with no framework and no database.

## Features

- Sections: About, Courses (Class 6 to 12, IIT JEE, NEET, Commerce), Teaching method, Faculty, Facilities, Admission process, Batches, Reviews, FAQ and Enquiry
- Enquiry form and call-back form, delivered to email through [Web3Forms](https://web3forms.com), with WhatsApp as a backup
- Loading screen, scroll animations, hover effects and smooth scrolling ([Lenis](https://github.com/darkroomengineering/lenis))
- Fully responsive, with a bottom Call / WhatsApp / Enquire bar on phones
- Privacy notice and consent checkboxes written for India's Digital Personal Data Protection (DPDP) Act, 2023
- SEO basics: meta description, Open Graph tags and structured data (schema.org)
- Security headers set in `vercel.json` (CSP, X-Frame-Options, X-Content-Type-Options, Referrer-Policy, Permissions-Policy)

## Project structure

```
.
├── index.html      The whole website (HTML, CSS and JS in one file)
├── build.js        Inserts the Web3Forms access key at build time
├── vercel.json     Build settings and security headers
├── package.json
├── .gitignore
└── README.md
```

## Deploying on Vercel

1. Push this repository to GitHub.
2. In Vercel, choose **Add New → Project** and import the repository.
3. Set **Framework Preset** to **Other**. Leave the build command and output directory as they are, because `vercel.json` already sets them.
4. Open **Settings → Environment Variables** and add:

   | Name | Value |
   |------|-------|
   | `WEB3FORMS_ACCESS_KEY` | Your Web3Forms access key |

5. Deploy.

To change the key later, update the variable in Vercel and redeploy.

### About the access key

Get a free key at [web3forms.com](https://web3forms.com) by entering the email address that should receive enquiries. The key is kept out of this repository and is inserted into the page by `build.js` when Vercel builds the site. Web3Forms access keys are designed to be public in the browser, so the deployed page will contain the key. It only allows sending a form to your inbox and cannot be used to read submissions.

If `WEB3FORMS_ACCESS_KEY` is not set, the forms fall back to sending the enquiry through WhatsApp.

## Running locally

You need [Node.js](https://nodejs.org) 18 or newer.

```bash
# optional: use your key for a local build
export WEB3FORMS_ACCESS_KEY=your-key-here

node build.js
```

Then open `dist/index.html` in a browser. The `dist` folder is generated and is not committed.

## Editing the content

All content is in `index.html`. Search for these to update them:

| What | Search for |
|------|-----------|
| Phone number | `085271 23412` and `918527123412` |
| Address | `Building No. 22` |
| Course cards | `id="courses"` |
| Faculty | `id="faculty"` |
| Batch timings | `id="batches"` |
| FAQ | `id="faq"` |
| Reviews | `class="slide` |
| Privacy notice | `id="pvd"` |
| Colours | `:root{--navy` at the top of the stylesheet |

## Security headers

`vercel.json` adds a Content-Security-Policy and other headers. If you add a new outside service (analytics, a map, a chat widget), you must also allow its address in the policy, or the browser will block it. For example, forms need `https://api.web3forms.com` in `connect-src`, which is already included.

## Data protection (DPDP Act)

The site collects the student's and parent's name, mobile number, class, course of interest and an optional email and message, only to contact people about admission. Both forms ask for consent before sending, including a confirmation that the person is 18 or older or the student's parent or guardian. The privacy notice in `index.html` should be reviewed by a legal professional and kept up to date, especially if you add analytics or change how long enquiry data is kept.

## Third-party services

| Service | Used for |
|---------|----------|
| Web3Forms | Delivering form submissions to email |
| Google Fonts | Plus Jakarta Sans and Nunito Sans fonts |
| jsDelivr | Loading the Lenis smooth-scroll library |
| WhatsApp | Optional chat link for enquiries |

## Contact

Gurukul Vidyapeeth Coaching Institute – Dwarka Mor
Building No. 22, NSUT Campus Road, behind Main Bus Stand, Dwarka Mor, Block A, Sewak Park, Dwarka, New Delhi 110059
Phone: 085271 23412

© 2026 Gurukul Vidyapeeth Coaching Institute. All rights reserved.
