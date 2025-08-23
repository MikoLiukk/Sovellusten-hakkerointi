# H1 Korkeat standardit
## a) Tutustu kurssin sanastoon, joka on määritelty SFS-EN ISO/IEC 27000:2020:en standardissa
- 3.2 Attack: Yritys tuhoa, paljastaa, muuttaa, estää tai saada luvaton pääsy omaisuuteen.
- 3.31 Information security event: Yksittäinen tai useampi haitallinen tai yllättävä tietoturva tapahtuma, joka voi vaarantaa liiketoiminen ja uhkaa tietoturvaa.
- 3.56 Requirement: Tarve tai odottama, joka on täytettävä tietoturvan vahvistamiseksi
- 3.58 Review: Toiminto, jonka tarkoituksena on selvittää kohteen sopivuus, riittävyys ja tehokkuus.
- 3.77 Vulnerability: Omaisuuden tai suojauksen heikkous, jota yksi tai useampi uhka voi uhka voi hyödyntää. 

## b) Tutustu standardiin ISO 27034-1 - 5
ISO/IEC 27034 antaa ohjeistusta sovellusturvallisuuden hallintaan. Se koostuu kuudesta osasta(Yleiskuva ja käsitteet, Organisaation hallinnollinen viitekehys, Sovellusturvallisuuden hallintaprosessi, Sovellusturvallisuuden validointi, Protokollat ja sovellusturvallisuuden valvontarakenne ja Sovellusturvallisuuden ohjeistus erityistilanteisiin). Nämä tarjoavat ohjeistuksen sovellusturvallisuuden hallintaan eri organisaatioissa. Eri osien avulla organisaatiot voivat integroida sovellusturvallisuuden osaksi ohjelmistokehitystä, elinkaarta ja varmistaa sovellusten turvallisuuden.

## c) Laatulöpinät 30: Tietoturvallisuus ohjelmistokehityksessä. 
- Huomioi, että jakso on julkaistu 25.lokakuuta 2021, joten jakson väittämät voivat olla vanhaa tietoa.
- 1. Väittämä: "Mikään ohjelmisto ei ole täysin tietoturvallinen." Itse uskon, että tämä on täysin totta, harvoin tietoturva ratkaisut vanhenevat kuin viini.
- 2. Väittämä: "Hallinnollinen tietoturva on teknisen tietoturvan onnistumisen edellytys." Ensin avataan termit, mitä hallinnollinen ja tekninen tietoturva tarkoittaa. Hallinnollinen tietoturva keskittyy prosesseihin, standardeihin ja koulutukseen, eli hallinnollinen tietoturva ohjaa tietoturvan toteuttamista ja ylläpitoa. Kun taas tekninen tietoturva sisältää palomuurit, pääsynhallintajärjestelmät, todennusmekanismit, yms. Uskon tämänkin väittämän olevan totta, koska tietoturvan heikoin lenkki on kuitenkin ihminen ja sen sinisilmäisyys.
- 3. Väittämä: "Automaatio testaus on ohjelmisto tietoturvan kannalta erittäin tärkeää." Minun mielestä automaatio testaus on yhtä tärkeää kuin kuin manuaalisesti tehty testaus. On tärkeää käyttää automaattista ja manuaalista testausta. 
- 4. Väittämä: "Ohjelmistoa suunniteltaessa, voidaan tehdä paljonkin auttamaan käyttäjää toimia tietoturvallisesti. Usein nämä toimenpiteet kuitenkin vaikuttavat negatiivisesti käytettävyyteen." Tähän en osaa ottaa itse kantaa, koska en ole ollut mukana suunnittelemassa ohjelmistoa.
- 5. Väittämä: "Ohjelmiston tietoturvan suunnitteluun, vaikuttaa se kuinka arkaluontoisia tietoa ohjelmistolla on tarkoitus käsitellä." Tämän kanssa olen samaa mieltä, koska tässä puhutaan resurssien käytöstä. Esimerkkiksi pankki käyttää paljon enemmän resursseja tietoturvaan kuin yhden miehen mobiilipeli yritys. Jos henkilötietoja käsittelevän yrityksen tietoturva pettää, voi käydä Case Vastaamo tapaus. Tea-sovellus on myös hyvä esimerkki mitä voi käydä jos tietoturvaa ei oteta vakavasti. (https://www.nbcnews.com/tech/social-media/tea-app-hacked-13000-photos-leaked-4chan-call-action-rcna221139) 
- 6. Väittämä: "Ohjelmistokehittäjät näkevät aina omat ohjelmistonsa merkittävästi riskialttiimpina, kuin muiden tekemät ohjelmistot." Uskon tämän väittämän olevan totta, koska kehittäjä tuntee oman ohjelmistonsa paremmin kuin jonkun muun tekemän ohjelmiston. Kehittäjä tunnistaa helpommin heikkoudet ja mahdolliset riskit.

## d) Tee itsellesi riskienhallintasuunnitelma.

| Riski                     | Todennäköisyys (1–5) | Vaikutus (1–5) | Riskipiste (T x V) | Hallintakeinot                                                                                                      |
| ------------------------- | -------------------- | -------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------- |
| Aikataulu venyminen       | 3                    | 4              | 12                 | Laaditaan realistinen aikataulu, varataan puskuria ja suoritetaan väliarviointeja edistymisestä                     |
| Teknologiset ongelmat     | 3                    | 4              | 12                 | Käytetään luotettavia virtuaalikoneita ja harjoitussovelluksia; varmuuskopioidaan snapshotit ennen kokeiluja        |
| Osaamattomuus             | 3                    | 5              | 15                 | Seurataan ohjeita tarkasti, hyödynnetään opettajan ja materiaalien tukea, harjoitellaan ensin pienillä esimerkeillä |
| Tietoturvariskit          | 2                    | 5              | 10                 | Käytetään erillistä virtuaalikonetta; vältetään tuntemattomien ohjelmien ja tiedostojen lataamista                  |
| Eettiset/Lailliset riskit | 1                    | 5              | 5                  | Testataan vain luvallisia harjoitussovelluksia; harjoitukset kohdistetaan vain eristettyihin ympäristöihin          |
Tehty ChatGPT antamalla riskeiksi Aikataulu, teknologiset ongelmat, osaamattomuus, tietoturvariskit ja lailliset riskit


### Lähteet:
https://terokarvinen.com/sovellusten-hakkerointi/
https://www.arter.fi/podcast/laatulopinat-podcast-tietoturvallisuus-ohjelmistokehityksessa-tarkastele-kokonaisuutta-ja-hyodynna-viitekehykset/
https://www.youtube.com/playlist?list=PLfPH7bJ3QKSo5D5RPFIKGHHBGxo6Ydc_P
https://www.securitycompass.com/blog/detailed-guide-to-iso-27034/
https://www.dataguard.com/blog/iso-27034/
https://chatgpt.com/
INTERNATIONAL STANDARD ISO/IEC 27034-1, First edition 2011-11-15


