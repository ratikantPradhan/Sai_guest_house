# 🏨 Sai Guest House – Official Website

A modern, minimalist, and fully offline-capable website for **Sai Guest House**, Daspalla, Nayagarh, Odisha. Built with pure HTML, CSS, and Vanilla JavaScript — no frameworks, no backend, no build tools.

---

## 🚀 Live Demo

> Deploy to Netlify and add your URL here.  
> Example: `https://ratikantpradhan.github.io/Sai_guest_house/`

---

## 📁 Project Structure

```
sai-guest-house/
├── index.html        ← Complete website (single file)
└── README.md         ← This file
```



---

## ✨ Features

### 🌐 Website Pages
| Page | Description |
|------|-------------|
| **Home** | Hero section, about, room category preview |
| **Rooms** | Live room availability with color-coded status tiles |
| **Amenities** | 12 facility cards |
| **Explore** | Nearby attractions (Baisipalli, Kuanria Dam, etc.) |
| **Reviews** | 6 guest testimonials with ratings |
| **Contact** | Enquiry form (via WhatsApp), address, map link, FAQ |

### 🏠 Room Management
- **AC Double** — 11 rooms @ ₹1,200/night
- **AC Duplex** — 1 room @ ₹2,500/night
- **Non-AC Single** — 6 rooms @ ₹500/night
- **Non-AC Double** — 12 rooms @ ₹800/night
- **Meeting Hall** — Capacity 50 @ ₹3,000/session

### 🎨 Room Status Colors
| Color | Meaning |
|-------|---------|
| 🟢 Green | Available |
| 🟠 Orange | Booked |
| 🟣 Purple | Reserved (shows date) |

### 🔐 Manager Login (PIN-based)
- 6-digit PIN pad — no plaintext password in source code
- PIN stored as a hashed value only
- Session expires automatically after **8 hours**
- Session persists on page refresh within the window
- Works on `file://`, `http://localhost`, and deployed HTTPS

### 💾 Data Persistence
- All room status, rates, and reservation dates saved to **localStorage**
- Data survives page refresh and browser restart

---

## 🔐 Manager PIN Setup

### Default PIN
```
112233
```
> ⚠️ Change this before going live!

### How to Change Your PIN

1. Open your deployed site in a browser
2. Open **DevTools → Console** (`F12` or `Ctrl+Shift+I`)
3. Run:
   ```js
   console.log(simpleHash('yourNewPin'))
   ```
4. Copy the output (looks like: `a1b2c3d4_sgh_6`)
5. In `index.html`, find this line:
   ```js
   const MANAGER_PIN_HASH = simpleHash('112233');
   ```
6. Replace it with:
   ```js
   const MANAGER_PIN_HASH = "a1b2c3d4_sgh_6"; // your copied hash
   ```
7. Save and redeploy

> ✅ Your actual PIN is **never stored** anywhere — only the hash is in the code.

---

## 🛠️ Manager Capabilities (After Login)

- Click any room tile to edit:
  - Change status → Available / Booked / Reserved
  - Update room rate (₹)
  - Set reservation end date
- Changes save instantly to localStorage
- All changes persist after page reload

---

## 🚢 Deployment

### Option 1 — Netlify Drop (Fastest)
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag and drop your project folder
3. Your site is live in under 60 seconds ✅

### Option 2 — Netlify via GitHub
1. Push project to a GitHub repository
2. Go to [app.netlify.com](https://app.netlify.com) → **Add new site → Import from Git**
3. Select your repo → Deploy

### Option 3 — Local Testing
Simply open `index.html` directly in any browser:
```
file:///path/to/sai-guest-house/index.html
```
> All features including PIN login work on `file://` — no server needed.

---

## 📱 PWA / Add to Home Screen

To make the site installable as an app on Android/iOS:

1. Create a square icon image (512×512 px) — save as `icon-192.png` and `icon-512.png`
2. Create a `manifest.json` file:
   ```json
   {
     "name": "Sai Guest House",
     "short_name": "SGH",
     "start_url": "./index.html",
     "display": "standalone",
     "background_color": "#3D2B0A",
     "theme_color": "#B8960C",
     "icons": [
       { "src": "icon-192.png", "sizes": "192x192", "type": "image/png" },
       { "src": "icon-512.png", "sizes": "512x512", "type": "image/png" }
     ]
   }
   ```
3. Add inside `<head>` of `index.html`:
   ```html
   <link rel="manifest" href="manifest.json">
   <meta name="apple-mobile-web-app-capable" content="yes">
   <meta name="apple-mobile-web-app-title" content="SGH">
   <link rel="apple-touch-icon" href="icon-192.png">
   ```
4. Deploy all files together

---

## 📞 Contact Details (Pre-configured)

| Field | Value |
|-------|-------|
| Phone | +91 94384 84811 |
| Email | saiguesthousedaspalla@gmail.com |
| Address | NH-57, Main Road, Daspalla, Nayagarh, Odisha – 752091 |
| Proprietor | PURNACHANDRA PRADHAN |
| Account No | 2984001700015896 |
| IFSC Code | PUNB0298400 |
| WhatsApp | [Chat Link](https://wa.me/919438484811) |

> To update these, search for the relevant value in `index.html` and replace.

---

## 🖼️ Adding Real Photos (Gallery)

The gallery currently uses emoji placeholders. To add real photos:

1. Place your images in the project folder (e.g. `photos/room1.jpg`)
2. In `index.html`, find the gallery section with `.gal-item` divs
3. Replace each emoji div with:
   ```html
   <div class="gal-item">
     <img src="photos/room1.jpg" alt="Room 1" style="width:100%;height:100%;object-fit:cover;">
   </div>
   ```

---

## 🧰 Tech Stack

| Technology | Usage |
|------------|-------|
| HTML5 | Structure & markup |
| CSS3 | Styling, animations, responsive layout |
| Vanilla JavaScript | Logic, PIN auth, localStorage, rendering |
| Web Crypto API | SHA-256 PIN hashing (HTTPS/localhost) |
| localStorage | Room data persistence |
| sessionStorage | Login session management |

**No frameworks. No npm. No build step. No backend.**

---

## 🔮 Future Enhancements (Roadmap)

- [ ] Real photo gallery with lightbox
- [ ] Online booking form with date picker
- [ ] SMS/WhatsApp booking confirmation
- [ ] GST invoice generation (integrate with billing app)
- [ ] Multi-language support (Odia / Hindi)
- [ ] Google Reviews embed
- [ ] Dark mode toggle

---

## 📄 License

This project is built for **Sai Guest House, Daspalla** and is intended for private use.  
© 2026 Sai Guest House · All Rights Reserved.

---

*Built with ❤️ for Sai Guest House, Daspalla, Nayagarh, Odisha.*
