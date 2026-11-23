PVH DIGITÁLIS NÉVJEGYRENDSZER – VERCEL

A csomag tartalma:
- index.html: nyilvános, reszponzív munkatársi címtár és egyedi névjegyoldal
- data/contacts.json: szerkeszthető munkatársi adatállomány
- vercel.json: /egyedi-nev URL-ek kiszolgálása

A projekt egyelőre a beszélgetésben megadott, ismert PVH-s névjegyet tartalmazza: Jedlicska Zsófia Melinda. Más munkatárs adatait nem találtam ki; a további 49–99 rekordot a contacts.json fájlba kell felvenni.

ÚJ MUNKATÁRS HOZZÁADÁSA
A data/contacts.json fájl egy JSON-tömb. Másold le a meglévő objektumot, és töltsd ki az adatokat:
{
  "slug": "kovacs-anna",
  "name": "Kovács Anna",
  "title": "Projektmenedzser",
  "organization": "Pécsi Vagyonhasznosító Zrt.",
  "department": "Projektmenedzsment",
  "phone": "+36301234567",
  "email": "anna.kovacs@pelda.hu",
  "website": "",
  "linkedin": "",
  "photo": ""
}
Minden slug legyen egyedi, kisbetűs, ékezet nélküli, szóköz nélküli. A JSON-ban az objektumok között vessző legyen, az utolsó után ne legyen vessző. A department mező opcionális; ez alapján működik a szervezeti egység szűrő.

VERCEL TELEPÍTÉS
1. Töltsd fel a projekt teljes tartalmát egy GitHub repository gyökerébe.
2. Vercelben: Add New → Project → importáld a repositoryt.
3. Framework Preset: Other. Build Command és Output Directory maradjon üres/alapértelmezett.
4. Deploy.
5. A címtár a projekt gyökér-URL-jén érhető el.
6. Egyedi névjegy például: https://SAJAT-DOMAIN.vercel.app/jedlicska-zsofia

ADATFRISSÍTÉS
A GitHubon módosítsd a data/contacts.json fájlt, majd commitold. A GitHubhoz kapcsolt Vercel projekt automatikusan újradeployol.

NFC
Minden munkatárs NFC-kártyájára a saját teljes HTTPS névjegy-URL-je kerüljön NDEF URL/URI rekordként.
NFC Tools → Write → Add a record → URL/URI → Write.
A névjegyoldal Kapcsolat mentése gombja a böngészőben állít elő vCard 3.0 fájlt.

ADATVÉDELEM
A címtár nyilvános: csak olyan munkahelyi adatokat tegyetek közzé, amelyek publikálására a szervezet jogosult, és az érintettek jóváhagyták.
Nincs adminfelület és nincs adatbázis; a contacts.json fájl a központi adatforrás.
A logó a megadott külső SVG URL-ről töltődik be.
