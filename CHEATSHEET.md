# Git Cheat Sheet – Repo Lectures

## 🔼 Locale → GitHub (caricare modifiche locali)
Quando aggiungi o modifichi file sul tuo computer:

```bash
cd "/Users/Leonardo/GitHub/Lectures"
git status                              # vedi cambiamenti
git add .                               # aggiungi tutto
git commit -m "Descrizione modifiche"
git push                                # carica su GitHub (branch master)
```

---

## 🔽 GitHub → Locale (scaricare modifiche da remoto)
Quando fai modifiche su GitHub.com o un collega aggiorna:

```bash
cd "/Users/Leonardo/GitHub/Lectures"
git pull origin master
```

---

## ⚠️ Se hai modifiche locali non ancora committate

- **Committa prima, poi pull**:
```bash
git add .
git commit -m "WIP: salvataggio provvisorio"
git pull origin master
```

- **Oppure usa stash**:
```bash
git stash
git pull origin master
git stash pop
```

---

## 🧩 Risolvere conflitti di merge
Succedono se tu e GitHub avete cambiato le stesse righe.

1. Nei file vedrai marker tipo:
```
<<<<<<< HEAD
(tua versione)
=======
(versione su GitHub)
>>>>>>> origin/master
```

2. Scegli cosa tenere, elimina i marker.
3. Poi:
```bash
git add file_conflitto
git commit -m "Risolto conflitto"
```

- Tenere la **versione remota**:
```bash
git checkout --theirs -- path/file
git add path/file
```

- Tenere la **versione locale**:
```bash
git checkout --ours -- path/file
git add path/file
```

Se vuoi annullare del tutto il merge:
```bash
git merge --abort
```

---

## 🧭 Routine consigliata (se lavori da solo)
1. **Prima di lavorare**:
```bash
git pull origin master
```

2. **Dopo le modifiche**:
```bash
git add .
git commit -m "Aggiornamenti <corso/cartella>"
git push
```

---

*(Mantieni questo file `CHEATSHEET.md` nella cartella Lectures per avere sempre a portata i comandi principali.)*
