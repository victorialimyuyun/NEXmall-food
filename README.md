# NEX Care & Share Food Directory 🌈

A Care Bears–themed food directory prototype for **nex** mall at Serangoon MRT.
Search outlets, filter by Halal certification, browse by cuisine, call a stall
to check reservations, and jump to each outlet's menu/website.

This is a static, single-page site (`index.html`) — no build step, no backend,
no dependencies. It runs anywhere a static file can be served.

## 🚀 Deploy to Vercel via GitHub

### 1. Unzip and push to a new GitHub repo

```bash
unzip nex-food-directory.zip
cd nex-food-directory
git init
git add .
git commit -m "Initial commit: NEX Care Bear food directory"
git branch -M main
git remote add origin https://github.com/<your-username>/nex-food-directory.git
git push -u origin main
```

(Create the empty repo on GitHub first at https://github.com/new — don't
initialize it with a README, or you'll need to `git pull --rebase` before
pushing.)

### 2. Import into Vercel

1. Go to https://vercel.com/new
2. Click **Import Git Repository** and select the repo you just pushed
3. Framework preset: choose **Other** (it's a static site — Vercel will
   auto-detect `index.html` at the root)
4. Leave build settings as default (no build command needed)
5. Click **Deploy**

Vercel will give you a live URL like `nex-food-directory.vercel.app` within
about a minute.

### Alternative: Deploy without GitHub (Vercel CLI)

```bash
npm i -g vercel
cd nex-food-directory
vercel --prod
```

## 📁 Project structure

```
nex-food-directory/
├── index.html      # the entire app (HTML + CSS + JS, no build step)
├── vercel.json      # static deployment config
├── package.json     # metadata only — no real dependencies
├── .gitignore
└── README.md
```

## ✏️ Updating outlet data

All outlet data lives in the `OUTLETS` array near the bottom of `index.html`
(inside the `<script>` tag). Each entry looks like:

```js
{ name:"Jollibee", unit:"#B1-28/29", cuisine:"Fast Food", halal:true,
  tel:"+6569706578", telDisplay:"6970 6578",
  website:"https://www.facebook.com/JollibeeSG/" }
```

- Set `tel` to `null` if there's no number to call — the card will show
  "Walk-in only" instead of a call button.
- Cuisine categories and their icons/colors are defined in the `CUISINES`
  object just above `OUTLETS`.

## ⚠️ Data accuracy

Stall numbers, hours, and reservation availability are compiled from public
food-guide sources and may change. Verify with nex's official directory
before relying on this for a visit.
