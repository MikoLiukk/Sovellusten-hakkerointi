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

<img width="591" height="89" alt="image" src="https://github.com/user-attachments/assets/0e2fa79b-36f0-4414-913c-6859ba4bc449" />

