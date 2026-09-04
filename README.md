# The Matcha Games

Eine kleine Live-Counter-Web-App für **Mila vs. Chrissy**.

- `index.html` = öffentlicher Zuschauer-Link (nur ansehen)
- `admin.html` = dein Master-/Admin-Link (Punkte +1 / -1, Reset)
- `firebase-config.js` = Firebase-Verbindung
- `firestore.rules` = sorgt dafür, dass nur dein Admin-Account schreiben darf

## 1) Kostenloses Firebase-Projekt anlegen

1. Öffne https://console.firebase.google.com/
2. **Projekt hinzufügen** → z. B. `the-matcha-games`.
3. Im Projekt: **Build → Firestore Database → Datenbank erstellen**.
4. Starte in **Production mode**. Region möglichst in Europa wählen.
5. **Build → Authentication → Sign-in method → Email/Password** aktivieren.
6. Unter **Authentication → Users → Add user** deinen privaten Admin-Login anlegen.
7. Kopiere die **UID** dieses Users.
8. Öffne **Firestore Database → Rules** und ersetze den Inhalt durch `firestore.rules`.
9. Die Admin-UID ist in diesem Paket bereits eingetragen. Klicke anschließend auf **Publish**.

## 2) Firebase Web-App verbinden

1. Firebase: Zahnrad → **Project settings**.
2. Unter **Your apps** auf `</>` (Web) klicken und eine Web-App registrieren.
3. Firebase zeigt dir ein `firebaseConfig`-Objekt.
4. `firebase-config.js` ist in diesem Paket bereits mit deinem Firebase-Projekt verbunden.

## 3) Kostenlos online stellen

### Einfachste Variante: GitHub Pages

1. Kostenloses GitHub-Konto nutzen/anlegen.
2. Neues Repository erstellen, z. B. `the-matcha-games`.
3. Alle Dateien aus diesem Ordner hochladen.
4. Repository → **Settings → Pages**.
5. `Deploy from a branch` wählen → Branch `main` → Ordner `/root` → Save.
6. Nach kurzer Zeit bekommst du eine URL wie:
   `https://DEINNAME.github.io/the-matcha-games/`

Dann gilt:

- Zuschauer: `https://DEINNAME.github.io/the-matcha-games/`
- Nur für dich: `https://DEINNAME.github.io/the-matcha-games/admin.html`

Die Zuschauer müssen sich nicht anmelden. Nur du loggst dich auf `admin.html` ein.

## Wichtig

Der Admin-Link allein ist **kein Geheimschutz**. Die eigentliche Sicherheit kommt durch Firebase Authentication + Firestore Rules. Deshalb kann selbst jemand, der `admin.html` kennt, ohne deinen Login keine Punkte verändern.

## Optional: Als iPhone-App auf den Homescreen

Safari → Teilen → **Zum Home-Bildschirm**. So wirkt der Counter fast wie eine kleine App.
