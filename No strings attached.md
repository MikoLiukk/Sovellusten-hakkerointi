# H3 No strings attached

Ladattava zip-paketti on ladattavissa tehtävänannosta. https://terokarvinen.com/sovellusten-hakkerointi/

## a) Strings. Lataa ezbin-challenges.zip Aja 'passtr'. Selvitä oikea salasana 'strings' avulla. Selvitä myös lippu.

Ensin ladattiin Teron sivuilta (linkki ylhäällä) ezbin-challenges.zip paketti. Sitten unzipattiin paketti niinkin yksinkertaisella komennolla kuin unzip ezbin-challenges.zip. Tämän jälkeen avattiin käyterttiin strings komento passtr ohjelmaan. (strings passtr) Lippu ja salasana löytyi. Testasin vielä salasanaa ohjelmaan (./passtr) ja sekin antoi lipun minulle. 

<img width="590" height="402" alt="Näyttökuva 2025-09-02 173544" src="https://github.com/user-attachments/assets/0eb94303-575f-4153-9a2c-86ac9d92ea3c" />

<img width="560" height="93" alt="Näyttökuva 2025-09-02 173616" src="https://github.com/user-attachments/assets/3e9abd4d-2434-4f62-af7e-83ec92244092" />



## b) Tee passtr.c -ohjelmasta uusi versio, jossa salasana ei näy suoraan sellaisenaan binääristä. Osoita testillä, että salasana ei näy. (Obfuskointi riittää.)

Aloitin tutkimalla mitä Obfuskointi tarkoittaa ja miten se voidaan tehdä. Obfuskointihan ei tarkoita datan salaamista vaan sen sekoittamista/hämäystä. Päädyin kuitenkin siihe, että tekoäly osaa (https://www.chatgpt.com) Laitoin prompiin koodin ja pyysin sen obfuskoimisesta. Kuvassa takasin saatu XOR-obfuskoitu koodi.

<img width="789" height="582" alt="Näyttökuva 2025-09-02 181510" src="https://github.com/user-attachments/assets/810ca7aa-6f07-472a-bbb4-a373ef960c18" />

Se toimii.

<img width="436" height="463" alt="Näyttökuva 2025-09-02 181738" src="https://github.com/user-attachments/assets/698db31b-b064-4012-acc2-4c83a6923150" />


## c) Packd. Aja 'packd' paketista ezbin-challenges.zip. Mikä on salasana? Mikä on lippu? (Tämä tehtävä on hieman haastavampi. Kirjaa ylös kokeilemasi lähestymistavat ja keksimäsi hypoteesit. Toivottavasti pääset itse maaliin, mutta jos et, läpikävely paljastuu tunnilla...)

Yritin aluksi strings-komenolla avata tehtävää, en tiennyt sitä silloin mutta sain sillä jo salasanan ensimmäisen osan. 

<img width="436" height="463" alt="Näyttökuva 2025-09-02 181738" src="https://github.com/user-attachments/assets/e3840acd-7788-48c5-bfdb-b37b815e9b4f" />

Tämän jälkeen muistin, että tunnilla oli käyty file-komentoa, se oli tyhjä arpa.

<img width="821" height="153" alt="Näyttökuva 2025-09-02 181840" src="https://github.com/user-attachments/assets/7e0d7e2a-16e4-4a35-ad98-57cf9c9cf60c" />

Tämän jälkeen tutkin lisää sovellusta strings-komennolla ja siellä osui silmään pakkausohjelma UPX. (https://github.com/upx/upx) UPX Packerissä on myös unpack ominaisuus, joten latasin upx linuxille (sudo apt-get install upx). Unpack ominaisuus toimi ihan komennolla upx -d packd -0 packd_unpacked. 

<img width="691" height="595" alt="Näyttökuva 2025-09-02 182101" src="https://github.com/user-attachments/assets/3779a49d-92a1-4ba7-86aa-14035755bd25" />

Sitten taas strings packd, ja salasana löytyi.

<img width="588" height="352" alt="Näyttökuva 2025-09-02 183036" src="https://github.com/user-attachments/assets/c2a87d31-c3bf-41fb-9ebf-b26f79bf8aba" />

Ja se toimikin.

<img width="579" height="86" alt="Näyttökuva 2025-09-02 183043" src="https://github.com/user-attachments/assets/c398fa46-a5d2-4b54-95cc-3f4351e43b41" />


### Lähteet:
https://terokarvinen.com/sovellusten-hakkerointi/
https://www.chatgpt.com
https://github.com/upx/upx
