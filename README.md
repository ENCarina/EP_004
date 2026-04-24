# ElitPort - Magánrendelő Foglalási Rendszer (EP_004)

Ez a projekt egy **Angular** és **Node.js** alapú webes alkalmazás, amely egy komplex egészségügyi foglalási rendszert valósít meg. A szoftver lehetővé teszi a páciensek számára az intuitív online időpontfoglalást, az orvosi személyzet számára pedig a rugalmas naptárkezelést és a szakterületi kompetenciák adminisztrációját.

## Projektstruktúra

A projekt három fő egységre tagozódik:

* **/api**: A backend réteg (Node.js, Express, SQLite adatbázis) / Express alapú RESTful API. Itt található az üzleti logika, az adatbázis-kezelés és a hitelesítés.
* **/web**: Angular alapú reszponzív kliensoldali alkalmazás.
* **/doc**: Teljes körű dokumentáció, beleértve a tesztelési jegyzőkönyvek, fejlesztői dokumentació és felhasználói dokumentációk (PDF és MD formátumban).
# EPort Telepítési Útmutató

## 🛠 Alkalmazott technológiák

- **Frontend:** Angular 18+, TypeScript, Bootstrap, CSS3
- **Backend:** Node.js, Express keretrendszer
- **Adatbázis:** SQLite (fájlalapú relációs adatbázis)
- **Dokumentáció:** Markdown, PDF

## 🚀 Telepítés és futtatás

### Előfeltételek
- Node.js (LTS verzió javasolt)
- npm (Node Package Manager)

### Backend indítása
1. Lépjen be az `api` könyvtárba: `cd api`
2. Telepítse a függőségeket: `npm install`
3. majd futtassa az alábbi parancsokat sorrendben:
```bash
node op conf:generate
node op key:generate
node op migrate
node op db:seed
```
4. Indítsa el a szervert: `npm run dev`
5. A backend alapértelmezetten a http://localhost:8000`  érhető el.

### Frontend indítása
1. Lépjen be a `web` könyvtárba: `cd web`
2. Telepítse a függőségeket: `npm install`
3. Indítsa el a fejlesztői szervert: `ng serve`
4. Az alkalmazás alapértelmezetten a `http://localhost:4200` címen érhető el.

## 🔑 Tesztadatok a bejelentkezéshez

A teszteléshez az alábbi előre rögzített tesztfiókok használhatók:
| Szerepkör | E-mail cím | Jelszó |
| :--- | :--- | :--- |
| **Páciens** | user@ep.com | test987 |
| **Orvosok** | dr.toth@ep.com | doctor123 |
| **Adminisztrátor** | admin@ep.com | joyEtna |

## 📝 Dokumentációk

A részletes projektleírások a `/doc` mappában találhatóak:
1. [Dokumentáció_Összesített](./doc/DOKUMENTACIO.md)
2. [Dokumentáció_pdf](./doc/DOKUMENTACIO.pdf)
3. [Fejlesztői kézikönyv](./doc/DEVELOPER_GUIDE.md)
4. [Felhasználói kézikönyv](./doc/felhasznaloidokumentacio_VL.md)
5. [Tesztelési jegyzőkönyv](./doc/tesztdokumenum0423_VL.md)
6. [Tesztelési dokumentáció](./doc/TEST_final.md)
7. [Manualis Tesztesetek](./doc/TEST_manual_test_report.md)
8. [Artifacts_csatolmányok](./doc/emails/ ./doc/screenshots)
   
### 💡 Fontos megjegyzések a teszteléshez

* **E-mail küldés (SMTP):** A rendszer fejlesztői és tesztelési fázisban **Mailtrap Sandbox** környezetet használ. A funkció teljes körű működéséhez érvényes `EMAIL_USER` és `EMAIL_PASS` környezeti változók (vagy kapcsolódó SMTP beállítások) szükségesek.
* **Korlátozások:** Az e-mail küldési adatok hiányában a rendszer zavartalanul elindul és használható, azonban az automatikus e-mail visszaigazolások nem kerülnek kiküldésre.
* **Fiókaktiválás:** A saját e-mail címmel történő regisztrációhoz szükséges az SMTP konfiguráció. A zökkenőmentes tesztelés érdekében a rendszerben található **seedelt tesztfiókok (Admin, Páciens) már alapértelmezetten verifikált állapotban vannak**, így ezekkel minden funkció azonnal elérhető.



