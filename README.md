# ✈ YatraBook — India Travel Booking Platform

A fully structured React.js travel booking web app featuring flights, hotels,
vacation packages, reviews, payments, user dashboard, and an admin panel —
all focused on Indian destinations with ₹ INR pricing.

---

## 📁 Project Structure

```
yatrabook/
├── public/
│   └── index.html              ← HTML shell, Google Fonts import
│
├── src/
│   ├── index.js                ← ReactDOM entry point
│   ├── App.jsx                 ← Root component: routing + global state
│   │
│   ├── styles/
│   │   └── global.css          ← CSS variables, reset, animations
│   │
│   ├── data/                   ← Static mock databases (replace with API calls)
│   │   ├── flights.js          ← Flight listings
│   │   ├── hotels.js           ← Hotel listings
│   │   ├── packages.js         ← Vacation packages
│   │   ├── reviews.js          ← Seed reviews
│   │   └── destinations.js     ← City list + featured destinations
│   │
│   ├── utils/
│   │   └── formatters.js       ← formatINR, generateBookingId, avgRating, etc.
│   │
│   ├── hooks/
│   │   ├── useToast.js         ← Toast notification hook
│   │   └── useBookings.js      ← Booking state management hook
│   │
│   ├── components/             ← Reusable UI components
│   │   ├── Navbar.jsx
│   │   ├── Footer.jsx
│   │   ├── Toast.jsx
│   │   ├── StarRating.jsx
│   │   ├── Badge.jsx
│   │   ├── SearchBox.jsx
│   │   └── ReviewSection.jsx
│   │
│   └── pages/                  ← One file per route/page
│       ├── HomePage.jsx        ← Hero, featured packages, destinations, reviews
│       ├── SearchPage.jsx      ← Filterable flight / hotel / package results
│       ├── DetailPage.jsx      ← Full item detail + booking card + reviews
│       ├── PackagesPage.jsx    ← All vacation packages grid
│       ├── BookingPage.jsx     ← 3-step: Details → Payment → Confirmation
│       ├── DashboardPage.jsx   ← User bookings + profile
│       ├── LoginPage.jsx       ← Login / Register
│       └── AdminPage.jsx       ← Admin dashboard, listings, review moderation
│
├── package.json
├── .gitignore
└── README.md
```

---

## 🚀 Local Setup (Step-by-Step)

### Prerequisites

Make sure these are installed on your computer:

| Tool       | Version  | Download                         |
|------------|----------|----------------------------------|
| Node.js    | v18+     | https://nodejs.org               |
| npm        | v9+      | comes with Node                  |
| Git        | any      | https://git-scm.com              |

Verify installations:
```bash
node -v
npm -v
git --version
```

---

### Step 1 — Download / Clone the project

If you already have the folder, skip to Step 2.

```bash
# If cloning from GitHub (after pushing):
git clone https://github.com/YOUR_USERNAME/yatrabook.git
cd yatrabook
```

---

### Step 2 — Install dependencies

```bash
npm install
```

This reads `package.json` and installs React, React Router, and all other
packages into the `node_modules/` folder.

---

### Step 3 — Start the development server

```bash
npm start
```

- Opens **http://localhost:3000** in your browser automatically.
- Hot-reloads whenever you save a file — no need to restart.

---

### Step 4 — Build for production

```bash
npm run build
```

Creates an optimised `/build` folder ready to deploy to any static host
(Netlify, Vercel, GitHub Pages, Firebase Hosting, etc.).

---

## 🐙 Push to GitHub (Step-by-Step)

### Step 1 — Create a new GitHub repository

1. Go to **https://github.com/new**
2. Repository name: `yatrabook`
3. Keep it **Public** (or Private — your choice)
4. ❌ Do NOT check "Add a README" (we already have one)
5. ❌ Do NOT check "Add .gitignore" (we already have one)
6. Click **Create repository**

GitHub will show you a page with your repo URL, e.g.:
`https://github.com/YOUR_USERNAME/yatrabook.git`

---

### Step 2 — Initialise Git in the project folder

Open a terminal inside the `yatrabook/` folder and run:

```bash
# Initialise a new git repo
git init

# Stage every file
git add .

# Create the first commit
git commit -m "Initial commit: YatraBook travel platform"
```

---

### Step 3 — Link your local repo to GitHub

```bash
# Replace YOUR_USERNAME with your actual GitHub username
git remote add origin https://github.com/YOUR_USERNAME/yatrabook.git

# Rename the default branch to 'main' (modern convention)
git branch -M main
```

---

### Step 4 — Push to GitHub

```bash
git push -u origin main
```

- `-u origin main` sets the upstream so future pushes are just `git push`.
- GitHub may ask for your username + password / token the first time.

✅ Refresh `https://github.com/YOUR_USERNAME/yatrabook` — all files are live!

---

### Step 5 — Subsequent pushes (after making changes)

```bash
# See what changed
git status

# Stage changed files
git add .

# Commit with a message describing what you changed
git commit -m "Add: hotel filter by price range"

# Push
git push
```

---

## 🌐 Deploy to Netlify (Free)

```bash
# 1. Build the project
npm run build

# 2. Install the Netlify CLI
npm install -g netlify-cli

# 3. Login to Netlify
netlify login

# 4. Deploy
netlify deploy --prod --dir=build
```

Or drag-and-drop the `/build` folder at **https://app.netlify.com/drop**

---

## 🔑 Admin Access

Log in with any email that contains the word **admin**, e.g.:
- `admin@yatrabook.in`
- `superadmin@test.com`

The admin panel unlocks at `/admin` in the navbar.

---

## 🗺 Routes

| URL                    | Page                        |
|------------------------|-----------------------------|
| `/`                    | Home                        |
| `/search`              | Search results              |
| `/packages`            | All vacation packages       |
| `/detail/:type/:id`    | Item detail + booking card  |
| `/booking`             | Booking details + payment   |
| `/dashboard`           | User bookings + profile     |
| `/login`               | Login / Register            |
| `/admin`               | Admin panel (admin only)    |

---

## 🛠 Tech Stack

| Layer       | Technology                         |
|-------------|------------------------------------|
| UI          | React 18, React Router v6          |
| Styling     | CSS Variables, inline styles       |
| State       | React hooks (useState, useEffect)  |
| Data        | Static JS files (mock DB)          |
| Fonts       | Crimson Pro (Google Fonts)         |
| Currency    | ₹ INR via Intl.NumberFormat        |
| Build tool  | Create React App (react-scripts)   |

---

## 📌 Notes for Production

To convert this into a full production app, replace the `src/data/*.js` files
with real API calls to a **Node.js + Express + MongoDB** backend:

```
src/data/flights.js   →  GET /api/flights
src/data/hotels.js    →  GET /api/hotels
src/data/packages.js  →  GET /api/packages
src/data/reviews.js   →  GET /api/reviews
useBookings.js        →  POST /api/bookings
```

Add JWT authentication by storing the token in `localStorage` and sending it
as `Authorization: Bearer <token>` on protected API calls.

---

Made with ❤️ for Incredible India 🇮🇳
