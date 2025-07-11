# 🧪 Uvod v Git in delo s projektnim repozitorijem

## 📌 Cilj vaje
Študent bo skozi praktično delo:
- spoznal osnovne pojme in ukaze v Gitu,
- inicializiral lokalni repozitorij in ga povezal z oddaljenim na GitHubu,
- uporabljal veje, merge in rebase,
- reševal konflikt med vejami,
- pripravil končno poročilo s kodo in diagramom poteka.

---

## 📝 Navodila za delo

### 1️⃣ Priprava okolja
✅ Namestite ali preverite, da imate nameščen Git (ukaz: `git --version`).  
✅ Ustvarite si račun na [GitHub](https://github.com) (če ga še nimaš).  
✅ Ustvarite mapo za projekt: `my-first-git-project`.

---

### 2️⃣ Inicializacija repozitorija
✅ V ukazni vrstici pojdite v mapo projekta in inicializirajte lokalni repozitorij:
```bash
git init
```

✅ Ustvarite datoteko `README.md` s kratkim opisom projekta in jo committajte:
```bash
echo "# My First Git Project" > README.md
git add README.md
git commit -m "Add README"
```

✅ Ustvarite nov repozitorij na GitHubu z enakim imenom kot lokalni projekt.  
✅ Povežite lokalni repozitorij z GitHub:
```bash
git remote add origin https://github.com/USERNAME/my-first-git-project.git
git branch -M main
git push -u origin main
```

---

### 3️⃣ Osnovno delo
✅ Ustvarite datoteko `index.html` in vpišite preprost HTML dokument.  
✅ Committajte in pushaj spremembe.  
✅ Ustvarite datoteko `.gitignore`, vanjo vpišite `node_modules/` in `*.log`, committajte.  
✅ Na GitHubu preveri, ali so spremembe vidne.

---

### 4️⃣ Delo z vejami
✅ Ustvarite novo vejo `feature-1` in nanjo preklopi:
```bash
git checkout -b feature-1
```

✅ V veji `feature-1` dodajte datoteko `style.css`, povežite jo z `index.html`, committajte in pushaj novo vejo na GitHub.  
✅ Ustvarite še vejo `feature-2`, v kateri dodate datoteko `script.js`, committajte in pushaj.  
✅ Preklopite na `main`, združi `feature-1`:
```bash
git checkout main
git merge feature-1
```

✅ Združite še `feature-2`, vendar jo najprej spremenite tako, da povzroči konflikt:
- v `main` spremenite `<h1>` na `index.html` v nekaj drugega in committajte.
- v `feature-2` naredite isto, ampak drugače.

✅ Poskusite merge `feature-2` v `main`:
```bash
git merge feature-2
```

✅ Rešite konflikt ročno (odpri `index.html`, uredi besedilo), committajte popravek.

---

### 5️⃣ Delo z rebase
✅ Ustvarite novo vejo `feature-3` iz `main`.  
✅ Dodajte datoteko `about.html`, committajte.  
✅ V `main` dodaj še `contact.html` in committajte.  
✅ V `feature-3` naredi rebase na `main`:
```bash
git checkout feature-3
git rebase main
```

✅ Pushajte vse spremembe in preveri zgodovino:
```bash
git log --oneline --graph --all
```

---

### 6️⃣ Priprava poročila
✅ V datoteko `report.md` zapišite:
- Kaj ste naredili v posameznem koraku.
- Seznam uporabljenih ukazov.
- Posnetke zaslona ali izpis `git log --graph`.
- Kratek opis, kaj ste se naučil o:
  - commitih in stageanju,
  - vejah in merge/rebase,
  - konfliktih in njihovem reševanju.

Oddajte projekt z vsemi datotekami in `report.md` na GitHub.

---

## 📄 Oddaja
Študent odda:
- povezavo do repozitorija na GitHubu (javni repozitorij),
- datoteko `report.md` v repozitoriju.

---