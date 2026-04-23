# ElitPort - Magánrendelő Menedzsment Rendszer (EP_004)

Ez a projekt egy komplex egészségügyi foglalási rendszer, amely lehetővé teszi a páciensek számára az időpontfoglalást, az orvosok számára pedig a naptár- és kompetenciakezelést.

## Projekt struktúra

A projekt három fő egységre tagozódik:

* **/api**: Node.js / Express alapú RESTful API. Itt található az üzleti logika, az adatbázis-kezelés és a hitelesítés.
* **/web**: Angular alapú reszponzív kliensoldali alkalmazás.
* **/doc**: Teljes körű dokumentáció, beleértve a tesztelési jegyzőkönyvet, fejlesztői dokumentaciót (PDF és MD formátumban).

## Főbb funkciók
- Dinamikus idősáv generálás (14 napos gördülő naptár).
- Szerepkör alapú hozzáférés (Admin / Páciens).
- Intelligens orvosi kompetencia-mapping.
- Analitikai dashboard az adminisztrátorok számára.

## Telepítés és futtatás
A rendszert helyi környezetben az alábbi módon indíthatja el:

### 1. Backend (api) indítása
Lépjen be az `api` mappába, és futtassa az alábbi parancsokat sorrendben:

```bash
npm install
node op conf:generate
node op key:generate
node op migrate
node op db:seed
npm run dev
```

2. Web: `cd web && npm install && ng serve -o`