# 🧪 Priprava aplikacije (frontend + Supabase backend) in Docker

## 📌 Cilj
- ustvariti repozitorij s kodo aplikacije,
- implementirati frontend aplikacijo, ki komunicira z Supabase,
- konfigurirati Supabase projekt (baza + auth),
- pripraviti Docker za lokalni razvoj/deploy aplikacije.

---

## 📝 Koraki

### 1️⃣ Priprava GitHub repozitorija
✅ Na GitHubu ustvari nov repozitorij, npr.:  
`my-supabase-app`

✅ Na lokalnem računalniku kloniraj repozitorij:
```bash
git clone https://github.com/USERNAME/my-supabase-app.git
cd my-supabase-app
```

---

### 2️⃣ Supabase projekt
✅ Prijavi se v [Supabase](https://supabase.io) in ustvari nov projekt.  
✅ Nastavi:
- ime projekta (npr. `my-app`),
- regijo,
- geslo za bazo.

✅ V Supabase:
- ustvari tabelo (npr. `todos`) s stolpci `id`, `title`, `completed`,
- omogoči Row-Level Security (RLS) in dodaj pravila za dostop,
- vklopi auth (email + password).

✅ Zapiši API ključ in URL Supabase projekta — shrani v `.env`.

---

### 3️⃣ Frontend aplikacija
✅ Uporabi React (ali plain HTML/JS za osnovo) za frontend.  
✅ Naj aplikacija omogoča:
- prijavo uporabnika (auth preko Supabase),
- prikaz seznam `todos` iz Supabase baze,
- dodajanje novega `todo` zapisa.

📁 Struktura repozitorija:
```
/my-supabase-app
├── public/
├── src/
│   ├── App.jsx
│   ├── components/
│   └── supabaseClient.js
├── .env
├── package.json
└── README.md
```

✅ `supabaseClient.js`:
```js
import { createClient } from '@supabase/supabase-js'

const supabaseUrl = process.env.REACT_APP_SUPABASE_URL
const supabaseAnonKey = process.env.REACT_APP_SUPABASE_ANON_KEY

export const supabase = createClient(supabaseUrl, supabaseAnonKey)
```

✅ Dodaj `.env`:
```
REACT_APP_SUPABASE_URL=…
REACT_APP_SUPABASE_ANON_KEY=…
```

✅ Na koncu `README.md` opiši:
- kako pognati aplikacijo lokalno (`npm install && npm start`),
- kako nastaviti `.env`.

---

### 4️⃣ Docker za aplikacijo
✅ Ustvari `Dockerfile`:
```dockerfile
# osnovna slika
FROM node:20

# nastavitev delovne mape
WORKDIR /app

# kopiraj datoteke
COPY package*.json ./
RUN npm install
COPY . .

# izpostavi port
EXPOSE 3000

# zaženi
CMD ["npm", "start"]
```

✅ Ustvari `.dockerignore`:
```
node_modules
build
```

✅ Zaženi aplikacijo v Dockerju:
```bash
docker build -t my-supabase-app .
docker run -p 3000:3000 --env-file .env my-supabase-app
```

---

### 5️⃣ Oddaja
Študent odda:
✅ Povezavo do GitHub repozitorija s kodo.  
✅ Posnetek zaslona delujoče aplikacije (frontend prikazuje podatke iz Supabase).