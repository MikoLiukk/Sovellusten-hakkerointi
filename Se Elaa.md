# h5 Se elää! (Lari)
Labien zip-filet ladattavissa https://terokarvinen.com/sovellusten-hakkerointi/

## a) Lab1. Tutkiminen mikä on ohjelmassa vialla ja miten se korjataan. lab1.zip
Ainoa itse tehty tehtävä. Ohjelman kuuluisi printata jotain järkevää, mutta niin ei ollutkaan. Piti saada ohjelma printtaamaan salakieltä.
<img width="632" height="714" alt="Näyttökuva 2025-09-21 203358" src="https://github.com/user-attachments/assets/186889d7-42cf-47c0-a0a5-d26a2f6c8241" />

Huom tässä pitää korjata ensin microlla .c tiedostoa ja sitten kääntää se alkuperäisen tiedoston muotoon gcc -g -o.

Ainoa mitä tein oli bad.messagen jälkeen kirjoitin siihen Eipä oo enään nullia, viitaten että siinä oli alkuperäisessä koodissa NULL, joka ei toiminut.

<img width="418" height="326" alt="Näyttökuva 2025-09-21 204026" src="https://github.com/user-attachments/assets/cee8884c-b2e4-4d45-a9b9-f6866973ddb3" />

<img width="422" height="626" alt="Näyttökuva 2025-09-21 204752" src="https://github.com/user-attachments/assets/be6584e7-4716-4114-b556-f9e5a0857502" />

## b) Lab2. Selvitä salasana ja lippu + kirjoita raportti siitä miten aukesi. lab2.zip
Kun henkilökohtainen osaaminen loppuu, tulee tekoäly apuun. Linkissä koko keskustelu tekoälyn kanssa. En ees tiennyt mistä itse aloittaa.
Sain kuin sainkin lipun ja salasanan, mutta en tehnyt mielestäni tehtävää onnistuneesti. https://chatgpt.com/share/68d06207-ee00-800b-afd5-33c23251fde2

<img width="666" height="861" alt="Näyttökuva 2025-09-21 211141" src="https://github.com/user-attachments/assets/257af872-561e-4a57-af6c-612b0835be6c" />


Flägi kuitenkin löytyi kun ensimmäisestä breikistä (Whats the password?) kun breikistä asetetaan palautusarvoksi 1 ((gdb) set $eax = 1) ja sitten continue.

<img width="599" height="327" alt="Näyttökuva 2025-09-21 212446" src="https://github.com/user-attachments/assets/6f07de30-d2cb-4fb6-9f8e-29581ffc5dd4" />

Salananakin tuli kokonaan tekoälyltä. Salasanan salattu versio löytyi kun disassemble main --> break mAsdf3a (koska aikaisemmat callit on plt loppuisia (jonkin sortin printf)) ja tarkistettiin mAsdf3a rekistereitä. Tekoäly tajusi kuinka käännetään haluttu "anLTj4u8" oikeaksi salasanaksi.

<img width="609" height="736" alt="Näyttökuva 2025-09-22 001830" src="https://github.com/user-attachments/assets/ac5afe9c-5f1d-48b9-941e-004ba4333346" />

<img width="604" height="732" alt="Näyttökuva 2025-09-22 002129" src="https://github.com/user-attachments/assets/6fa026a8-a2e9-4f38-a0a0-2b28ce157b5a" />

<img width="591" height="89" alt="Näyttökuva 2025-09-22 000606" src="https://github.com/user-attachments/assets/9c2b265b-9a56-42ee-9b04-cfc8ba5aae9e" />

## c) Lab3. Kokeile Nora Crackmes harjoituksia tehtävä 3 ja 4 ja loput vapaaehtoisia. Tindall 2023: NoraCodes / crackmes. (https://github.com/NoraCodes/crackmes)
Jotta edellinen ei ollut liian helppo... Koitin katsoa suoraan ratkaisua Noran omilta ratkaisuista (https://nora.codes/tutorial/an-intro-to-x86_64-reverse-engineering/)
ja omaksi innokseni Radare2 löytyi valmiiksi koneelta, joten päästään seuraamaan ohjeita ja ei mitään. Tekoälyekskusteluun linkki ([https://chatgpt.com/c/68d05918-c584-832c-a50f-03895e384ef5](https://chatgpt.com/c/68d05387-9db4-8331-8a54-842db0cebab8)).
Kopioin sorsan tekoälylle ja pyysin siltä apua.

<img width="928" height="532" alt="Näyttökuva 2025-09-21 225641" src="https://github.com/user-attachments/assets/e9e779db-cd5a-4f7e-b0c6-f37a57e523a9" />

<img width="768" height="845" alt="Näyttökuva 2025-09-21 225658" src="https://github.com/user-attachments/assets/8a3ed316-a7f0-4bd0-99f5-6dcf99c071b9" />

<img width="837" height="851" alt="Näyttökuva 2025-09-21 225709" src="https://github.com/user-attachments/assets/57459c61-9e9c-4e79-a6da-b07e58fa2ae8" />

<img width="732" height="695" alt="Näyttökuva 2025-09-21 225722" src="https://github.com/user-attachments/assets/4e2fd15d-fe13-4d9d-9926-a9b1c0b7b25f" />

<img width="932" height="480" alt="Näyttökuva 2025-09-21 225807" src="https://github.com/user-attachments/assets/acd84574-ce25-49ad-a37a-5b3fac109490" />
