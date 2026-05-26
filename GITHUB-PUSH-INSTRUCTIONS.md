# Jak nahrát materiály na GitHub

Repozitář: **https://github.com/partyskincz-code/ALGAonboarding.git**

## Krok za krokem (Terminál na Macu / PowerShell na Windows)

### 1. Otevři terminál a přejdi do složky s materiály

**Mac (Terminal):**
```bash
cd ~/Documents/MBU\ onboarding
```
(uprav cestu podle toho, kde máš tu složku — můžeš v ní napsat `pwd` v terminálu a uvidíš plnou cestu)

**Windows (PowerShell):**
```powershell
cd "C:\Users\TvojeJmeno\Documents\MBU onboarding"
```

### 2. Smaž rozbitý `.git` (vznikl při pokusu z Claude prostředí)

**Mac:**
```bash
rm -rf .git
```

**Windows:**
```powershell
Remove-Item -Recurse -Force .git
```

### 3. Nastav Gitu, kdo jsi (jen poprvé, jednorázově)

```bash
git config --global user.email "partyskincz@gmail.com"
git config --global user.name "Jana Budinova"
```

### 4. Inicializuj repo a přidej soubory

```bash
git init -b main
git add README.md .gitignore algatech-vitejte.html algatech-vitejte-preview.pdf algatech-welcome-en.html algatech-welcome-en-preview.pdf algatech-checklist-cs.html algatech-checklist-cs.pdf algatech-checklist-en.html algatech-checklist-en.pdf
```

### 5. Vytvoř první commit

```bash
git commit -m "Initial commit: bilingual onboarding materials"
```

### 6. Propoj s GitHubem a pošli

```bash
git remote add origin https://github.com/partyskincz-code/ALGAonboarding.git
git push -u origin main
```

GitHub se tě zeptá na přihlášení — buď zadáš heslo, nebo (na novějším Gitu) tě pošle do prohlížeče, kde to odsouhlasíš. Pokud se zeptá na heslo a normální heslo nefunguje, potřebuješ tzv. **Personal Access Token** — návod níže.

---

## Pokud potřebuješ Personal Access Token (PAT)

GitHub od roku 2021 nepřijímá obyčejné heslo přes terminál. Pokud ti to napíše chybu, postupuj takto:

1. Přihlas se na **github.com** ve svém prohlížeči
2. Vpravo nahoře klikni na svůj avatar → **Settings**
3. Úplně dole vlevo → **Developer settings**
4. **Personal access tokens** → **Tokens (classic)** → **Generate new token (classic)**
5. Pojmenuj ho (např. "MacBook"), zaškrtni oprávnění **`repo`**, vygeneruj a **zkopíruj** (zobrazí se jen jednou!)
6. Když se tě terminál v kroku 6 zeptá na heslo, **vlož tento token** místo hesla

---

## Bonus: zapnout GitHub Pages (webová stránka)

Pokud chceš, aby ty HTML soubory fungovaly jako živý web (lidi je mohli rovnou otevírat v prohlížeči):

1. Na GitHub.com otevři repozitář **ALGAonboarding**
2. **Settings** → **Pages** (vlevo dole)
3. Pod **Source** vyber **Deploy from a branch**
4. Branch: **main** / Folder: **/ (root)** → **Save**
5. Za chvilku ti GitHub Pages vygeneruje adresu typu:
   `https://partyskincz-code.github.io/ALGAonboarding/algatech-vitejte.html`

Tu adresu pak můžeš posílat novým kolegům přímo (žádné stahování PDF nepotřeba).

---

## Pomoc

Když něco zaškobrtne, dej mi do dalšího chatu screenshot chyby z terminálu a já ti řeknu, co s tím.
