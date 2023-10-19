# Angular Gyakorlat Haladó 01 

## Hasznos tudnivalók
- A feladatok nehezedő sorrendben vannak. Először olvasd el az összeset, és számodra egyre nehezedő sorrendben oldd meg.
- Minden feladat önállóan is megoldható, ha az egyik nem sikerül, az nem 
befolyásolja a másik sikerességét.
- De! Ha nem sikerült egy feladat és ki akarod hagyni, állítsd vissza abba az 
állapotba a feladathoz kapcsolódó kódot, ahogy az előtt a feladat előtt volt ;-)
- Az alkalmazás figyeli a fájlokat, és amikor szerkeszted a backendet, újra 
is indítja azt. Ez a funkció az `npm run dev` indítóparancs esetén működik. 
Ha hiba lépne fel, akkor használhatod az `npm run docker-compose:up` 
parancsot is, de ebben az esetben a backendet minden változtatás után 
_MANUÁLISAN ÚJRA KELL INDÍTANOD_!

## Előkészítés

### Backend
- Lépj be a terminálon a `/backend` mappába és futtasd az `npm i` parancsot.
- Indítsd el a Docker Desktop alkalmazást.
- Lépj be a `/backend` mappába és állítsd be gyökérmappának: `code . -r`.
- Indítsd el az API-t a következő paranccsal: `npm run dev`.

### Frontend
- Lépj be a terminálon a `/frontend` mappába és futtasd az `npm i` parancsot.
- Nyiss egy új VSCode-ot az adott mappában, itt fogod szerkeszteni a frontend -et: 
`code .`
- Indítsd el a frontendet a következő paranccsal: `npm start`

## Feladatok

### 1. feladat
- BACKEND FELADAT!
- API-útvonal: `http://localhost:3000/services`
- Pótold a Mongoose-modellt a `backend/src/models/service.model.js` fájlban.
- A modell pontosan kövesse a kapcsolódó adatmodelljének a mintáját a frontendről.
- A `backend/src/server.js` fájlban módosítsd a `/services` URL-re érkező 
kérések esetén a router-t, hogy a service router szolgálja ki a kéréseket.

### 2. feladat
- BACKEND FELADAT!
- API-útvonal: `http://localhost:3000/races`
- Pótold a backenden a `backend/src/controllers/race` mappában a hiányzó 
service-t, router-t és controller-t.
- A validálásnak és a működésnek a többi controller-ét kell követnie.
- A modellt készen kapod: `backend/src/models/race.model.js`.
- A `backend/src/server.js` fájlban módosítsd a `/races` URL-re érkező 
kérések esetén a router-t, hogy a race router szolgálja ki a kéréseket.

### 3. feladat
- FRONTEND FELADAT!
- API-útvonal: `http://localhost:3000/cars`
- A Frontend VSCode-jában kell dolgoznod!
- Pótold a hiányzó részeket a `frontend/src/app/page/car-edit` komponensben, 
hogy lehetővé váljon a járművek szerkesztése. A TS- és a HTML-fájlban is 
dolgoznod kell.
- A szerkesztő oldalra az autók listájából jutsz el, a sorok végén látható 
kék gombra kattintva.
- A következő tulajdonságokat kell szerkeszthetővé tenned: 
`model`, `year`, `maker`, `price`.
- Légy óvatos! A carService-nek küldött objektumban mindenképp legyen `_id`, 
mert a BaseService a kapott objektum alapján küldi el a kérést a szervernek.
- Minta:  
![elonezet](./img/str-final-exam-01.JPG)

### 4. feladat
- FRONTEND FELADAT!
- API-útvonal: `http://localhost:3000/customers`
- Listázd ki a Frontenden a Customer-eket!
- Pótold a hiányzó részeket a `frontend/src/app/page/customer` komponensben, 
hogy lehetővé váljon a vásárlók listázása. A TS- és a HTML-fájlban is 
dolgoznod kell.
- Táblázatos formában jelenítsd meg a vásárlókat, minden sor végén legyen egy 
gomb, amire kattintva a szerkesztő oldalra jutunk (ez az oldal készen van).
- A táblázat oszlopaiban a következő adatok jelenjenek meg: 
`firstName`, `lastName`, `email`, `job`.
- Minta:  
![elonezet](./img/str-final-exam-02.JPG)

### 5. feladat
- BACKEND FELADAT!
- A `backend/src/docs/swagger.yaml` fájlban dolgozz.
- A Backenden pótold a `/race` végpontra küldhető kérések listáját.
- Készítd el a kapcsolódó Mongoose-modell alapján a Race schema-t is és arra 
hivatkozz az egyes URL-eknél.
- Minden metódus és URL-variáció szerepeljen, tehát az egy entitás lekérése, az 
összes lekérése, a létrehozás, frissítés és a törlés is. Tehát 5 végpontot 
kell definiálnod.
- Ahol request body-t kér, ott pontosan legyenek feltüntetve a kötelező mezők.
- Ahol szükséges paraméter (pl. _id), ott pedig azt is meg lehessen adni.
