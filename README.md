# ApparelPro Academy — Static Website

Complete, beginner-editable static website for **ApparelPro Academy**  
Tagline: *Learn Garments. Build Skills. Get Job-Ready.*

Built with plain **HTML, CSS, and JavaScript** — no React, no build step, no npm required.

---

## Folder structure

```
apparelpro-academy/
├── index.html          # Home
├── about.html          # About
├── courses.html        # Courses + filter + fee table
├── career.html         # Career preparation modules
├── learn.html          # Knowledge Hub (search + tags)
├── article.html        # Single article (uses ?slug=)
├── defects.html        # Defect library (search + risk filter)
├── defect.html         # Single defect (uses ?id=)
├── enroll.html         # Enrollment form
├── contact.html        # Contact + request a call
├── css/
│   └── style.css       # All styles (navy / cream / orange)
├── js/
│   ├── data.js         # ★ ALL editable content lives here
│   ├── include.js      # Header + footer injection
│   └── script.js       # Menu, forms, filters, accordion
├── images/
│   ├── hero.jpg        # (add your photos)
│   ├── about.jpg
│   ├── factory.jpg
│   ├── career.jpg
│   ├── learning.jpg
│   ├── measurement.jpg
│   └── defects/
│       ├── open-seam.jpg
│       ├── skip-stitch.jpg
│       └── broken-stitch.jpg
└── README.md
```

---

## How to run locally

1. Download / clone this folder.
2. Open `index.html` in a browser  
   **or** serve the folder with any static server:

```bash
# Python
python3 -m http.server 8080

# VS Code: “Open with Live Server”
```

No install, no build.

---

## How to edit (most important file: `js/data.js`)

### 1. Business name, tagline, contact

Open `js/data.js` → object `SITE`:

- `name`, `shortName`, `tagline`, `description`
- `phone`, `phoneHref`, `whatsappNumber` (digits only, e.g. `8801712345678`)
- `email`, `facebook`, `messenger`
- `location`, `locationDetail`, `hours`
- `announcement` (top bar text + link)

### 2. Add a new course

In `COURSES` array, copy one object and change:

- `id` (unique, lowercase-hyphens)
- `title`, `track` (`QI` | `QC` | `QA` | `Auditor`)
- `topics`, `duration`, `fee`, `image`

It appears automatically on Home, Courses, and the Enroll dropdown.

### 3. Change course fees

Edit the `fee` field, e.g. `fee: "BDT 12,000"`.

### 4. Change images

Replace files under `images/` using the same names, **or** change paths in `SITE.images` / each course / each defect.

If a file is missing, the site still works (SVG / specimen placeholder).

### 5. WhatsApp / contact

In `SITE`:

```js
whatsappNumber: "8801XXXXXXXXX", // no + or spaces
phone: "+880 1XXX-XXXXXX",
email: "hello@apparelproacademy.com",
```

### 6. Add a defect

Copy an object in `DEFECTS`. Set `image: ""` for a specimen card, or put a photo in `images/defects/`.

### 7. Add a Knowledge Hub article

Copy an object in `ARTICLES`. Set a unique `slug` (used in `article.html?slug=...`).

---

## Deploy / publish

| Host | Steps |
|------|--------|
| **GitHub Pages** | Push this folder to a repo → Settings → Pages → deploy from `main` / root |
| **Netlify** | Drag-and-drop the folder, or connect the GitHub repo |
| **Vercel** | Import the repo → framework: Other → output: root |
| **Any shared hosting** | Upload all files via FTP; point domain to the folder |

No Node.js required on the server.

---

## Forms

Enrollment and “Request a call” validate on the front end and save a copy to `localStorage` (browser).  
They show a success message. To receive real submissions later, connect the forms to Formspree, Google Apps Script, or your own backend.

---

## Design

- Navy `#0B1C33` + cream paper + burnt orange accent `#C44512`
- Fonts: Fraunces (headings) + Manrope (body) via Google Fonts
- Mobile-first, sticky header, FAQ accordion, back-to-top, WhatsApp float

---

## License

Your business content — use and modify freely for ApparelPro Academy.
