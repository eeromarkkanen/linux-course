# Viikko1 - Oma Linux

## Raportointi ja Free Software Definition

Kurssilla on tavoitteena kirjoittaa selkeitä raportteja, jotka kuvaavat tehtävien tekoa hyvin tarkasti. Tavoitteena olisi pitää kirjaa milloin ja miten mikäkin vaihe on tehty.
Varsinkin ongelmakohdista on hyvä olla olemassa tarkka selostus. 

Raportin on siis hyvä olla toistettava, täsmällinen, helppolukuinen ja lähteisiin on viitattava oikein.

Free Software Definition tarkoittaa, että käyttäjällä on oikeus käyttää, kopioida, jakaa, opiskella, vaihtaa ja kehittää ohjelmistoa. 
Eli "free" tarkoittaa tässä tapauksessa vapaata, ei ilmaista. Tärkeimmät pointit ovat siis:
Vapaus käyttää ohjelmaa mihin tahansa tarkoitukseen
Vapaus tutkia, opiskella ja vaihtaa ohjelman lähdekoodia
Vapaus jakaa kopioita edelleen jotta voi auttaa muita
Vapaus jakaa muunneltuja versioita edelleen muille, jotta muutkin voivat hyötyö näistä muutoksista

## VirtualBox ja Debian

Aloitin lataamalla Debian Live - levykuvan koneelle. Käytössä on Lenovo Vantage -läppäri ja Windows 11. 
Seuraavaksi latasin ja asensin VirtualBoxin.

Valitsin VirtualBoxin valikosta New ja täytin seuraavat tiedot ohjeiden mukaan: 
Nimi : DebianEeroMarkkanen
Muisti : 4000MB
Create Virtual Hard Disk Now
Tämän kooksi 60GB.
File Type VDI

<img width="475" alt="viikko1 4eero" src="https://github.com/user-attachments/assets/fd9facf0-fb4e-46f1-8ace-da9fa5437b74">

Tämän jälkeen menin Settings -> Storage ja klikkasin Attributes kohdan vieressä olevaa CD-levy-ikonia. Täältä valitsin ISO disk imagen joka ladattiin alussa.

<img width="470" alt="viikko1 2" src="https://github.com/user-attachments/assets/da181407-1868-4d68-877e-a1fd1160cc4c">

Sitten bootattiin virtuaalikone ja valittiin Live. Kokeilin avata hs.fi ja kaikki toimi hyvin. Sen jälkeen painoin Install Debian. Tein asetukset
ohjeiden mukaisesti eli valitsin kieleksi englannin ja näppäimistöksi suomalaisen näppäimistön. Erase Disk -> Yes ja Encrypt -> No sekä Boot loader location ohjeiden mukaisesti
ja tämän jälkeen loin itseni käyttäjäksi. Tämän jälkeen voitiin aloittaa asennus.

<img width="526" alt="viikko1 10" src="https://github.com/user-attachments/assets/0ab2e2ee-fe24-46b5-ab6c-63711e0d0cad">

## First Login

Minulla oli aluksi ongelmana, että ohjelma ei hyväksynyt sisäänkirjautumista vaan herjasi väärää salasanaa. Käynnistin ohjelman uudelleen ja ongelma hävisi ja pääsin kirjautumaan
luodulle käyttäjälle.

Avasin Applications -> Terminal Emulator ja ajoin $ sudo apt-get update. Seuraavaksi ajoin $ sudo apt-get -y dist-upgrade. Ohjeessa sanottiin, että tässä menisi jonkun aikaa, mutta 
minulla ei tullut mitään.

<img width="392" alt="viikko1 11" src="https://github.com/user-attachments/assets/c24f680e-27c3-41a3-87ee-bbc918a67e0c">

Palomuurin asennuksen ja käyttöönoton jälkeen tein vielä VirtualBox Guest Additions, että saan näytön resoluution paremmaksi. Tässä lopputulos.

<img width="568" alt="viikko1 final" src="https://github.com/user-attachments/assets/3be44c23-f54d-49b4-ac40-ae85349d3522">

## Lähteet

Karvinen, Tero: Oppitunti 21.08.2024

Karvinen, Tero: Raportin Kirjoittaminen, https://terokarvinen.com/2006/raportin-kirjoittaminen-4/ Luettu 26.08.2024

Karvinen, Tero: Install Debian on VirtualBox, https://terokarvinen.com/2021/install-debian-on-virtualbox/ Luettu 26.08.2024





