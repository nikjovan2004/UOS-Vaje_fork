# 🧪 Vaja: Cloudflare Pages – statično gostovanje (upload + Git deploy)

## 📌 Cilj vaje
Študent bo:
- gostoval statično spletno stran na Cloudflare Pages (brezplačno),
- razumel razliko med upload deploy in Git deploy,
- povezal GitHub repozitorij s Cloudflare,
- objavil javno dostopno spletno stran.

---

## 📝 Navodila

## 1️⃣ Priprava statične strani
✅ Prenesi predlogo strani iz: https://html5up.net/  
✅ Izberi eno temo in jo prenesi (.zip).  
✅ Razširi ZIP datoteko in preveri, da vsebuje `index.html`.

---

## 2️⃣ Cloudflare Pages (upload način)

### 🔹 Ustvari račun
- Pojdi na https://dash.cloudflare.com  
- Ustvari brezplačen račun

### 🔹 Ustvari Pages projekt
- Klikni **Workers & Pages**
- Klikni **Create application**
- Izberi **Pages**
- Klikni **Upload assets**

### 🔹 Upload
- Povleci mapo (razširjen HTML template) v upload
- Počakaj deploy

### 🔹 Test
- Odpri URL (npr. `https://ime.pages.dev`)
- Preveri, da stran deluje

---

## 3️⃣ GitHub repozitorij

### 🔹 Ustvari repo
- Na GitHub ustvari repo (npr. `cloudflare-pages-test`)

### 🔹 Naloži kodo
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/USERNAME/cloudflare-pages-test.git
git push -u origin main
```

---

## 4️⃣ Cloudflare Pages (Git deploy)

### 🔹 Ustvari nov projekt
- Ponovno pojdi na **Workers & Pages**
- Klikni **Create application**
- Izberi **Pages**
- Klikni **Connect to Git**

### 🔹 Poveži GitHub
- Izberi repozitorij
- Izberi branch: `main`

### 🔹 Nastavitve
- Build command: (pusti prazno)
- Output directory: `/`

### 🔹 Deploy
- Klikni **Deploy**
- Počakaj, da se stran objavi

---

## 5️⃣ Preverjanje
✅ Odpri URL (pages.dev)  
✅ Preveri:
- stran se naloži
- spremembe iz GitHub delujejo (če narediš commit)

---

## 📄 Oddaja
Študent odda:
- URL prve strani (upload)
- URL druge strani (Git deploy)
- GitHub repo link

---

## ⏳ Čas izvedbe
- Upload deploy: ~30 min  
- GitHub + Git deploy: ~45 min  
- Skupaj: ~1.5 h
