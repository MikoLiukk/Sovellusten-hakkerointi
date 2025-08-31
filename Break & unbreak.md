# h2 Break & unbreak
## Lue/katso/kuuntele ja tiivistä. 
### OWASP: OWASP Top 10 (https://owasp.org/Top10/A01_2021-Broken_Access_Control/)
 - Broken access controll on todella yleinen haavoittuvuus
 - Least privilege ja deny by default-periaatteet jätetään noudattamatta
### Karvinen 2023 Find Hidden Web Directories - Fuzz URLs with ffuf (https://terokarvinen.com/2023/fuzz-urls-find-hidden-directories/)
 - Artikkelissa paikallinen testipalvelin, joten harjoittelu on turvallista ja laillista.
 - Artikkelissa opetetaan fuzzauksen peruskomentoja ja perusteita.
### https://portswigger.net/web-security/access-control (https://portswigger.net/web-security/access-control)
 - Authentication (tunnistautuminen), Varmistaa käyttäjän henkilöllisyyden.
 - Session management (istunnon hallinta), Pitää yllä tiedon siitä, mitkä HTTP-pyynnöt kuuluvat samalle käyttäjälle.
 - Access control (käyttöoikeuksien hallinta), Päättää, saako käyttäjä suorittaa pyydetyn toiminnon.
### Karvinen 2006 Raportin kirjoittaminen (https://terokarvinen.com/2006/raportin-kirjoittaminen-4/)
 - Raportin tulisi olla toistettava, täsmällinen, helppolukuinen, viittaa lähteisiin, sisältää vakiotekstejä ja viitata mahdollisia pahoja mokia. Yksinkertaisuudessaan raportin avulla, jonkun muun pitäisi pystyä toistaa sama minkä olet itse tehnyt.

## a) Murtaudu 010-staff-only. Ks. Karvinen 2024: Hack'n Fix (https://terokarvinen.com/hack-n-fix/)
Linkistä löytyy ohjeet, kuinka maalit asennetaan koneelle ja kuinka niitä ajetaan.
Aloitin tehtävänannon mukaisesti antamalla pin-koodin 123, tämä palautti käyttäjän Somedude salasanan.
Aikanaan muilla kursseilla olin tehnyt hieman SQL-injektioita ja koska kurssin toisella tunnilla oltiin näitä käyty läpi, ajattelin siitä aloittaa.

Firefoxin developer työkaluissa on Inspector-työkalu, josta saa selaimen HTML rakenteet esille, josta löytyy maalin haavoittuvuus. Sivu on rakennettu siten, että elementtiin voi kirjoittaa vain numeroita, mutta tämä on helposti muutettavissa. kun <input type="number vaihdetaan <input type="text". 
Tämän jälkeen olin jumissa ja jouduin tippumaan jopa "Almost spoilers for 010" kohtaan, jossa silmään iski Limit komentoon. Lopullinen kenttään laitettu syöte oli ' OR 1=1 LIMIT 2,1; --. Limitin ensimmäinen numero on rivi mistä haku aloitetaan ja toinen numero on tietueiden määrä. Katsoin myös Robin Niinemetsin ja Aatuhorellilta mitä he olivat saaneet aikaiseksi (https://askdatdude.github.io/diary/entries/diary.html?entry=SH24-002&week= ja https://github.com/aatuhorelli/ICI012AS3A/blob/main/h2.md). Aatuhorelli oli saannut saman vastauksen kuin allekirjoittanut, mutta päätin myös kokeilla Robin Niinemetsin versiota, sekin vielä toimi.
<img width="958" height="806" alt="Näyttökuva 2025-08-31 170917" src="https://github.com/user-attachments/assets/a5242b79-4ea8-483d-b063-e90651776da5" />

<img width="964" height="805" alt="Näyttökuva 2025-08-31 170955" src="https://github.com/user-attachments/assets/f3a234ff-67f0-4d48-a153-47b1321b9afe" />

## b) Korjaa 010-staff-only haavoittuvuus lähdekoodista. Osoita testillä, että ratkaisusi toimii.
Suljin maalin ja avasin micro-editorilla staff-only.py scriptin (micro staff-only.py). En ole ennen tehnyt myöskään muiden koodien korjaamista tai debuggausta, joten aluksi ei ollut mitään hajua mistä lähteä liikkeelle, joten katsoin ylemmässä tehtävässä mainittujen Robinin ja Aatuhorellin ratkaisuja. Näistä selvisi, että haavoittuvuus saapuu koodin pätkästä "sql = "SELECT password FROM pins WHERE pin = '"+pin+"';"". Tekoälyn avulla tuli selväksi (https://chatgpt.com), että käyttäjän syöte (pin) lisätään suoraan sellaisenaan SQL-kyselyyn ilman muutoksia. Robin oli mielestäni korjannut koodin yksinkertaisemmin, kuin Aatuhorelli (less is more?). Loppujen lopuksi tekoälyn avulla sain koodinpätkän.
sql = text("SELECT password FROM pins WHERE pin = :pin") 
res =db.session.execute(sql.("pin": pin))
Tämä pätkä tekee kyselyistä parametrisoituja, suodattaa erikoismerkit ja liittää pin arvon turvallisesti erikseen SQL-kyselyyn.

Maali päivitetään scripti ja laitetaan maali uudelleen päälle.

<img width="957" height="733" alt="Näyttökuva 2025-08-31 171914" src="https://github.com/user-attachments/assets/e0336b51-898a-4f3c-9673-b42365c5056c" />
<img width="957" height="732" alt="Näyttökuva 2025-08-31 171920" src="https://github.com/user-attachments/assets/2aba3b48-1c14-4edc-9759-bbcf32a99212" />

Korjaukset toimivat molempia injektioita vastaan.

## c) Ratkaise dirfuzt-1 artikkelista Karvinen 2023: Find Hidden Web Directories - Fuzz URLs with ffuf.
Tämä on tehty aikaisemmassa kurssissa. Tehtävän ratkaisu on suoraan kopioitu aikaisemmasta raportistani (https://github.com/MikoLiukk/Tunkeutumistestaus/blob/main/h3_Fuzzy.md)

Ohjeet ffufin käyttöön ja ensimmäiseen fuzzaukseen Terolta (https://terokarvinen.com/2023/fuzz-urls-find-hidden-directories/)
Ohjeissa maalipalvelin ja kuinka tehtävä ratkaistaan.

Ensimmäisellä fuzzauksella huomasin, että kaikki tiedostot olivat 154 kokoisia, joten filtteröin ne pois ```-fs 154```

![Näyttökuva 2025-04-15 185056](https://github.com/user-attachments/assets/3cfa3c88-35b6-4195-8a90-2acbdc4484e9)

Tämän jälkeen 7 kiinnosttavaa kohdetta, kokeilin ensin .git, mutta sieltä ei löytynyt mitään.
.git/ ja wp-admin:istä löytyikin halutut kohteet, joten curlasin ne ja "liput" löytyi.

![Näyttökuva 2025-04-15 185338](https://github.com/user-attachments/assets/aee9ce3f-5d9d-41a8-bf30-18da6ef578e3)
