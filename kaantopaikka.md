# h4 Kääntöpaikka (Tero)

## x) Lue/katso/kuuntele ja tiivistä. (Tässä x-alakohdassa ei tarvitse tehdä testejä tietokoneella, vain lukeminen tai kuunteleminen ja tiivistelmä riittää. Tiivistämiseen riittää muutama ranskalainen viiva.)
### Hammond 2022: Ghidra for Reverse Engineering ([PicoCTF 2022 #42 'bbbloat'](https://www.youtube.com/watch?v=oTD_ki86c9I)) (Video, noin 20 min)
- Ghidran asennus ja käyttöönotto
- Kuinka löytää heksadesimaalin koodista
- Hyvä ohje ensimmäisen oikean tehtävän tekemiseen

## a) Asenna Ghidra
- sudo apt-get install ghidra tai kalilla pelkkä ghidra komentoriville

## b) rever-C. Käänteismallinna packd-binääri C-kielelle Ghidralla. Etsi pääohjelma. Anna muuttujielle kuvaavat nimet. Selitä ohjelman toiminta. Ratkaise tehtävä binääristä, ilman alkuperäistä lähdekoodia. ezbin-challenges.zip
Ezpin-challenges.zip:iä käytettiin jo viime tehtävissä, mutta asensin ne uudelleen ja unzippasin, koska halusin aloittaa puhtaalta pöydältä. Avataan packd ghidralla.

<img width="1917" height="887" alt="Näyttökuva 2025-09-14 123446" src="https://github.com/user-attachments/assets/5c761520-4365-4805-b4d0-c2cd928f96f1" />

Selailin tietämättömyyttäni Listingiä alaspäin ja sieltä tulikin jo osa salasanasta esille (piilos-An). Tiesin että minun pitää unpakata ohjelma, niin kuin viime tehtävissä (https://github.com/MikoLiukk/Sovellusten-hakkerointi/blob/main/No%20strings%20attached.md)

<img width="1911" height="825" alt="Näyttökuva 2025-09-14 123505" src="https://github.com/user-attachments/assets/52cf0c1c-80df-4237-9753-efbd2c9d6913" />

Sittenhän unpakatun decomptin mainista löyty salasana ja flägi.

<img width="1858" height="731" alt="Näyttökuva 2025-09-14 132940" src="https://github.com/user-attachments/assets/99bc59d7-c984-4eb8-b79a-43b872c2b1ee" />

Testasin vielä varmuuden vuoksi, että salasana toimi

<img width="584" height="101" alt="Näyttökuva 2025-09-14 133352" src="https://github.com/user-attachments/assets/6d97db8d-fd68-424e-b96d-9919a02bb48e" />

## c) Jos väärinpäin. Muokkaa passtr-ohjelman binääriä (ilman alkuperäistä lähdekoodia) niin, että se hyväksyy kaikki salasanat paitsi oikean. Osoita testein, että ohjelma toimii. ezbin-challenges.zip
Tämä onneksi käytiin pikaisesti tunnilla. Pitää vain löytää oikea JNZ ja vaihtaa se JZ. Tässä onneksi Decompilla löyty nopeasti oikea JNZ. Binaryn Patchaamiseen ohjeet vielä tässä. (https://materials.rangeforce.com/tutorial/2020/04/12/Patching-Binaries/)

<img width="1898" height="688" alt="Näyttökuva 2025-09-14 133832" src="https://github.com/user-attachments/assets/f2d88462-2c3d-4445-b2aa-ef92cd1058c8" />

Exportataan ohjelma ja testataan, että toimii:

<img width="612" height="367" alt="Näyttökuva 2025-09-14 134417" src="https://github.com/user-attachments/assets/3526c118-5d5b-4450-852c-e6f248fa3e05" />

## d) Nora CrackMe: Käännä binääreiksi Tindall 2023: NoraCodes / crackmes (https://github.com/NoraCodes/crackmes). Lue README.md (https://github.com/NoraCodes/crackmes/blob/master/README.md): älä katso lähdekoodeja, ellet tarvitse niitä apupyöriksi. Näissä tehtävissä binäärejä käänteismallinnetaan. Binäärejä ei muokata, koska muutenhan jokaisen tehtävän ratkaisu olisi vaihtaa palautusarvoksi "return 0".
Noran crackme:t voi ladata ihan git clone:lla tai wget:illä. Itse latasin git clone:lla. (git clone https://github.com/NoraCodes/crackmes.git). Tämän jälkeen README.md mukaan muutettiin muutettiin ohjelmat make <nimi> ja nimeksi laitettiin crackme01, crackme01e tai crackme02.

<img width="834" height="647" alt="Näyttökuva 2025-09-14 135454" src="https://github.com/user-attachments/assets/5ed3f0e6-dcdf-4de6-bf77-099be35f9fa4" />

## e1) Nora crackme01. Ratkaise binääri.
Salasanan näköinen ehdokas löytyi heti Decompilen mainista. 

<img width="1644" height="666" alt="Näyttökuva 2025-09-14 135909" src="https://github.com/user-attachments/assets/3947d8ec-0ab2-41a9-af42-ea3aa53efd0e" />

Eipä toiminut heti, kunnes tajusin koodista, että salasana pitää syöttää heti kun ajaa ohjelmaa, tai se antaa "Need exactly one argument."
Joten ajoin ohjelman salasanan kanssa.

<img width="563" height="126" alt="Näyttökuva 2025-09-14 135936" src="https://github.com/user-attachments/assets/c1ebfc2b-f682-44cd-af29-5ccd00d827aa" />

## e2) Nora crackme01e. Ratkaise binääri.
Tässä sama juttu kuin edellisessä, mutta pitää huomioida, että huutomerkki (!) liittyy yleensä komentohistoriaan tai komentojen uudelleenkäyttöön. Kun yrittää syöttää salasanan, tietokone luulee ! uudeksi komennoksi, jota ei ole.
Tämän kiertämiseen tarvitaan hipsukat. '

<img width="417" height="126" alt="Näyttökuva 2025-09-14 140427" src="https://github.com/user-attachments/assets/ef63e1ec-f7e5-4cff-aaad-e33e420c26d4" />

## f) Nora crackme02. Nimeä pääohjelman muuttujat käänteismallinnetusta binääristä ja selitä ohjelman toiminta. Ratkaise binääri.
Tämän kanssa oli sen verran ongelmia, että jouduin katsomaan ratkaisuja Noralta itseltään (
