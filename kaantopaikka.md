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
