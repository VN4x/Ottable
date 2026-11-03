# Plaan: Estplast.ee Eesti-keelne Visuaalne Auditiraport (PDF) ja Uue Kodulehe Visuaalsed Mockup-vaated

## 1. Eesmärk ja Strateegiline Fookus
Koostada **eestikeelne, esinduslik ja visuaalselt kujundatud PDF-auditiraport** (`estplast-veebiaudit-ja-visioon.pdf`) koos **3 täispika (long-screenshot) visuaalse mockup-pildiga**, mis näitavad, milline peaks välja nägema Eesti juhtiva EPS-soojustusmaterjalide tootja **Estplast Tootmine OÜ** kaasaegne korporatiivne veebileht.

### Kliendi Äriline Positsioneerimine (Raporti keskne sõnum)
1. **Turu liider ja suurettevõte (Finnfoam OY grupp):** Estplast on alates 2004. aastast tegutsev Eesti üks suurimaid ja olulisemaid ehitusmaterjalide tootjaid. Praegune (2019. aasta Elementoril põhinev, uduse `logo.gif` failiga ja kolmekordse menüüga) veebileht ei peegelda ettevõtte tegelikku mastaapi, tootmisvõimekust ega usaldusväärsust.
2. **Mitte e-pood, vaid Nr. 1 Tehniline Tõeallikas (Source of Truth):** Estplast ei müü otse lõpptarbijale läbi e-poe, vaid läbi ehituskaupluste (Decora, Ehituse ABC, Bauhof, Espak, Ehituskaup24 jt). Seetõttu ei vaja koduleht ostukorvi, vaid peab olema **autoriteetne insenertehniline teabekeskus** projekteerijatele, arhitektidele, ehitusjärelevalvele, ehitajatele ja ekspertiiside/vaidluste lahendajatele.
3. **Nähtavus otsingumootorites (SEO) ja tehisintellekti otsingus (GEO):** Kui arhitekt, ehitusekspert või AI-assistent (ChatGPT, Perplexity, Google AI) otsib EVS-EN 13163 standardeid, survepingeid, $\lambda_D$ soojusjuhtivust, DWG-sõlmejooniseid või toimivusdeklaratsioone (DoP), peavad Estplasti andmed olema masinloetaval HTML-kujul, mitte peidetud mobiilis mittetöötavatesse `<object>` PDF-akendesse.

---

## 2. Loodavad Failid (Deliverables)

Teostusetapis genereeritakse töökausta (`/workspace/app/output/` või juurkausta) järgmised failid:

1. **`estplast-audit-raport-et.pdf`** – Kõrgkvaliteediline, mitmeleheküljeline A4 formaadis visuaalne PDF-raport (eesti keeles), mis sisaldab:
   - Tiitellehte ja juhtkonna kokkuvõtet (Executive Summary) koos skoorikaartidega.
   - Süvaanalüüsi: **Miks praegune 2019. a visuaalne identiteet kahjustab turuliidri kuvandit** ja kuidas kaasaegne B2B korporatiivne disain tõstab usaldust arhitektide ja ehitajate silmis.
   - Struktuuri, SEO, GEO (AI-otsingu) ja tehnilise turvalisuse analüüsi koos konkreetsete tõenditega praeguselt lehelt (`<html lang="en-US">`, 0 `<h1>` pealkirja, 3 dubleeritud menüüd, katkised lingid, PDF-lõksud).
   - Manustatud võrdlusvaateid ja **3 uue disaini mockup-kuvatõmmist** koos selgitustega.
   - Tegevuskava (3 faasi) Nr. 1 eksperdiplatvormi loomiseks.
2. **3 täispikka visuaalset mockup-pilti (PNG, 1440px laiusega long-screenshotid):**
   - **`mockup-1-avaleht-korporatiivne.png`** – *Kaasaegne B2B Avaleht ja Positsioneerimine:*
     - Puhas, ühtne päis (SVG logo, Finnfoam & Warmotech grupi märgis, nutikas `EST | РУС | ENG` keelevahetaja, selge navigatsioon).
     - Autoriteetne Hero-sektsioon: *"Eesti juhtiv EPS-soojustusmaterjalide tootja ja insenertehniline kompetentsikeskus alates 2004. aastast"* koos kiirviidetega: **Projekteerijale (CAD/DWG & BIM)**, **Tootekataloog & kalkulaator**, **Toimivusdeklaratsioonid (DoP) & Katselabor**.
     - Interaktiivne "Vali lahendus konstruktsiooni järgi" (Vundamendid, Põrandad, Fassaadid, Katused, Karkassid, Tehnovõrgud) koos ristlõike joonistega.
     - Kvaliteedigarantii plokk: Tinius Olsen H5K-T UTM katselabori andmed, EVS-EN 13163 vastavus, EPD keskkonnadeklaratsioon.
     - Edasimüüjate plokk (Decora, Ehituse ABC, Bauhof, Espak, Ehituskaup24) – selge suunamine jaekaubandusse ilma e-poe mürata.
   - **`mockup-2-tooteleht-insenerile.png`** – *Tehniline Tooteleht (nt EPS 100 / EPS 60 Silver) – "Source of Truth" vaade:*
     - Selge `<h1>` pealkiri, kasutusvaldkonna ikoonid ja lühikokkuvõte.
     - **HTML-põhine tehniliste näitajate tabel** (Soojusjuhtivus $\lambda_D$, survepinge $\text{CS(10)}$, paindetugevus $\text{BS}$, tuleklass E, veeimavus, mõõtmed ja pakenditabel $m^2/m^3$) – koheselt loetav nii telefonis ehitusplatsil kui ka AI-ootoritele ja Google'ile.
     - Otseallalaadimise keskus: **Toimivusdeklaratsioon (DoP PDF)**, **Tooteleht (PDF)**, **Keskkonnadeklaratsioon (EPD)** ja seotud **DWG/PDF sõlmejoonised**.
     - "Kus seda kasutada / Kus mitte kasutada" eksperdiplokk vaidluste ja ehitusvigade ennetamiseks + nupp "Leia lähim edasimüüja (Decora, Ehituse ABC, Bauhof...)".
   - **`mockup-3-teadmiste-ja-ekspertiisikeskus.png`** – *Arhitekti, Ehitusjärelevalve ja Ekspertiisi Teabekeskus ("Inseneri Töölaud"):*
     - Otsitav ja filtreeritav **CAD / DWG / PDF sõlmejooniste pank** (vundamendid, soklid, tuulduvad ja krohvitavad fassaadid, katused, Warmotech aknasõlmed) koos eelvaatega.
     - **Normatiivid, standardid ja vaidluste ennetamine:** Ehitusfüüsikalised uuringud, niiskusrežiimi/hingamise arvutused, tuleohutusklassid ja ametlikud paigaldusnõuded (allikas ehitusvaidluste ja järelevalve jaoks).
     - **Katselabor & Sertifikaadid (DoP arhiiv):** Kiirpäring toote ja aasta järgi (sh ajaloolised deklaratsioonid vanemate objektide ekspertiisiks).
     - Otsekontakt Estplasti tehnilise konsultandiga / projektijuhiga.

---

## 3. Eestikeelse Raporti Struktuur (`estplast-audit-raport-et.pdf`)

1. **Tiitelleht:** *ESTPLAST.EE Digitaalne Audit ja Kaasaegse Eksperdiplatvormi Visioon* (Kuupäev, koondhinnang, fookus: Tootja korporatiivne kuvand & tehniline teabekeskus).
2. **Juhtkonna kokkuvõte (Executive Summary):**
   - Praeguse olukorra diagnostika skoorikaardina (Visuaalne disain & bränd 3.5/10, Struktuur & UX 4.5/10, SEO 3.0/10, GEO / AI-otsing 3.5/10, Tehnoloogia & turvalisus 4.0/10).
   - Strateegiline vastuolu: Estplast on reaalsuses Eesti turu liider (Finnfoam grupp, unikaalne Tinius Olsen katselabor Maardus), kuid digitaalselt näeb välja nagu 2010ndate väikeettevõte.
3. **1. Visuaalne Disain ja Korporatiivne Kuvand (Süvaanalüüs):**
   - **Miks 2019. aasta visuaal töötab turuliidri vastu:** Udune `logo.gif`, kolmekordne dubleeritud menüü, juhuslikud taustapildid (`couple.png`), kokkusurutud nupud (`letter-spacing: -0.9px`), katkine "Vundamendid" kaart (`href="#"`).
   - **Tootja vs. E-pood:** Miks Estplast ei vaja e-poodi, vaid peab suunama ostusoovi sujuvalt partneritele (Decora, Ehituse ABC, Bauhof, Espak), hoides ise **Nr. 1 tehnilise eksperdi ("Source of Truth")** positsiooni.
   - **Kasu kaasaegsest korporatiivsest visuaalist:** Kuidas puhas Põhjamaade tööstusdisain (Finnfoam grupi vääriline) loob kohese usalduse arhitektide, projekteerijate, korteriühistute ja ehitusjärelevalve silmis.
4. **2. Veebilehe Struktuur ja Kasutajakogemus (Arhitekt, Ehitaja, Ekspert):**
   - Navigatsioonikaose lahendamine (3 menüü asemel 1 selge süsteem).
   - Mobiilikogemus ehitusplatsil: Miks `<object type="application/pdf">` ei tööta nutitelefonides ja kuidas ehitusjärelevalve või töödejuhataja peab saama parameetrid kätte 3 sekundiga.
   - Keelevahetuse (`EST | РУС | ENG`) ja URL-struktuuri (`/est/` vs juurkaust) korrastamine.
5. **3. SEO ja GEO (Nähtavus Google'is ja AI-assistentides):**
   - Kriitilised SEO vead: `<html lang="en-US">` kõigil lehtedel, `<h1>` pealkirjade ja meta-kirjelduste täielik puudumine, Elementori sisemiste mallide (`?elementor_library=...`) lekkimine Google'i indeksisse.
   - **GEO (Generative Engine Optimization):** Kuidas teha Estplastist Nr. 1 viidatav allikas AI-mootoritele (HTML-tabelid PDF-ide asemel, `ManufacturingBusiness` ja `Product` Schema.org JSON-LD, `/llms.txt` fail, ekspertiisi- ja standardite andmebaas).
6. **4. Tehnoloogia ja Turvalisus:**
   - 7 aastat vana Elementor (`v2.5.4`) riskid, administraatori e-posti leke (`/wp-json/wp/v2/users`), DOM-i puhastamine (6x menüükood) ja GDPR/küpsiste teavituse lisamine.
7. **5. Uue Kodulehe Visuaalne Kontseptsioon (3 Täispikka Mockup-vaadet):**
   - Detailne ülevaade ja täismõõdus visuaalid:
     1. *Mockup 1: Kaasaegne Korporatiivne Avaleht*
     2. *Mockup 2: Insenertehniline Tooteleht (HTML andmetabelid + DoP keskus)*
     3. *Mockup 3: Projekteerija, Ehitusjärelevalve ja Ekspertiisi Teabekeskus*
8. **6. Tegevuskava (3 Etappi):** Konkreetne teekaart kiiretest parandustest kuni täieliku platvormi uuenduseni.

---

## 4. Tehniline Teostusplaan (Implementation Steps)

1. **Tööriistade ettevalmistus (`/tmp/kilo` või lokaalne töökeskkond):**
   - Kasutada Node.js-i ja headless brauserit (`playwright` või `puppeteer`), et renderdada HTML/CSS-põhised kõrgresolutsiooniga täispikad mockup-ekraanipildid (`1440px` laius, täispikkus) ning genereerida puhta tüpograafia ja leheküljevahetustega PDF-raport (`page.pdf({ format: 'A4', printBackground: true })`).
2. **3 Visuaalse Mockupi loomine ja renderdamine PNG-piltideks:**
   - Kujundada detailse HTML/CSS-iga 3 terviklikku veebivaadet (Estplasti rohelise `#007548`, tumehalli `#1e293b`, valge ja tehnilise halli `#f8fafc` toonides, geomeetriliste konstruktsioonijooniste, reaalsete EPS 60 / EPS 100 Silver andmete, Tinius Olsen labori ja Decora / Ehituse ABC / Bauhofi edasimüüjate viidetega).
   - Salvestada täispikad kuvatõmmised:
     - `/workspace/app/mockup-1-avaleht-korporatiivne.png`
     - `/workspace/app/mockup-2-tooteleht-insenerile.png`
     - `/workspace/app/mockup-3-teadmiste-ja-ekspertiisikeskus.png`
3. **Eestikeelse Visuaalse Auditiraporti (`estplast-audit-raport-et.pdf`) koostamine ja genereerimine:**
   - Koostada trükikvaliteediga HTML/CSS raport, mis sisaldab kogu tõlgitud ja täiendatud analüüsi, skoorigraafikuid, "Enne vs. Pärast" võrdlustabeleid ja manustatud 3 mockup-pilti.
   - Genereerida PDF fail `/workspace/app/estplast-audit-raport-et.pdf` (ning salvestada ka HTML-versioon `/workspace/app/estplast-audit-raport-et.html` mugavaks brauseris vaatamiseks).
4. **Kvaliteedikontroll (Verification):**
   - Kontrollida, et kõik 3 PNG mockup-pilti ja PDF-raport on loodud, mittetühjad, korrektse eesti keele ja terminoloogiaga (soojustusplaadid, toimivusdeklaratsioon, survepinge, soojusjuhtivus, külmasild, ehitusfüüsika) ning vastavad täpselt kliendi nõuetele (ei mingit e-poodi; fookus Nr. 1 eksperdi ja tootja staatusel).
