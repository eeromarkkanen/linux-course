# x) Tiivistelmä

Susannan [Teoriasta käytäntöön pilvipalvelimen avulla](https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/) ja Teron [First Steps on a New Virtual Private Server](https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/) antavat hyvät yksityiskohtaiset ohjeet:

* Miten vuokrata pilvipalvelin
* Palomuuriin tehtävät asetukset
* Käyttäjän lisääminen ja sudo-oikeudet
* Rootin lukitseminen
* Softan päivitys
* Ja lopulta nimipalvelimen vuokraus

## a) Oman virtuaalipalvelimen vuokraus

Ensimmäinen askel oman virtuaalipalvelimen luomiseen on valita palveluntarjoaja. Valitsin myös oppitunnilla käytetyn [Digitaloceanin.](https://www.digitalocean.com/) Alkuun minun täytyi luoda tunnus, joten valitsin Sign up ja 
vaihtoehdoista valitsin kirjautumisen GitHubin avulla. 

<img width="458" alt="viikko4 1" src="https://github.com/user-attachments/assets/0059f01a-d4f3-4e0c-b403-8a854040ac16">

Ensimmäiseksi Digitalocean kysyi peruskysymyksiä, kuten mihin palvelua käytän. Tämän jälkeen piti täyttää luottokorttitiedot sekä palvelimen vuokraamista ja yhden dollarin testimaksua varten. Tämän jälkeen verkkosivu ilmoitti "Card Added Succesfully" (en onnistunut saamaan tästä screenshottia) ja sitten aukesi jonkunnäköinen työpöytä/etusivu.

<img width="950" alt="viikko4 2" src="https://github.com/user-attachments/assets/cc7c72e7-6f01-434f-9ff9-a4211b4355a7">

Tämän jälkeen kävin Susannan esimerkin mukaisesti Billing-välilehdellä, ja laitoin Billing alerts hälyttämään minua, kun tietyn verran rahaa on käytetty. Sitten kokeilin ensimmäisen kerran lisätä rahaa tililleni. Onnistuinkin tässä suht helposti, sillä luottokorttitiedot olivat valmiina.

![viikko4 3](https://github.com/user-attachments/assets/5736a30b-7f6e-4b42-991b-df2ac9e64534)

Sitten oli aika luoda virtuaalipalvelin, eli Digitaloceanin sivuilla "Droplet." Se löytyi ylhäältä Create-valikosta. Seuraavaksi piti valita, mistä maasta palvelin vuokrataan. Valitsin Amsterdamin, koska oppitunnilla ja ohjeessa mainittiin, että palvelimen tulisi olla lähellä asiakkaita.

<img width="654" alt="viikko4 4" src="https://github.com/user-attachments/assets/9aac0a3c-4426-4b4b-8b33-d967fd2085d2">

Seuraavaksi piti valita käyttöjärjestelmä. Valitsin Debian version 12 x64, koska se oli uusin listatuista.

<img width="563" alt="viikko4 5" src="https://github.com/user-attachments/assets/32e6fdfd-c5d8-4910-906b-c6626bde361a">

Tämän jälkeen valitsin Shared Computer -> Basic ja annetuista hintavaihtoehdoista 6$ koneen. Se sisälsi yhden 1GB tietokoneen, jossa on 25GB muistia. Mukaan tuli myös 1000GB siirtoa(transfer.)

<img width="682" alt="viikko4 6" src="https://github.com/user-attachments/assets/e4923670-3858-4d56-a818-a3c8b539ac7a">

Sitten Digitalocen tarjosi erilaisia lisäpalveluita, mutta jätin ne valitsematta. Loin vahvan salasanan ja tämän jälkeen koneelle piti antaa Hostname. Käytin Random word generatoria ja valitsin kaksi ensimmäistä sanaa, jotka olivat directory ja home.

<img width="638" alt="viikko4 7" src="https://github.com/user-attachments/assets/bd40e578-3135-454a-be06-1b63d38d8033">

Hetken kuluttua virtuaalipalvelin oli luotu.

<img width="762" alt="viikko4 8" src="https://github.com/user-attachments/assets/a3e74dfb-46f9-4a6e-86f5-5a84f3c9ff3b">

# b) Alkutoimet omalla virtuaalipalvelimella

Tässä kohdassa minun piti tehdä tarvittavat toimet omalla virtuaalipalvelimella. Nämä olivat tulimuurin päälle asettaminen, root-tunnuksen sulkeminen ja ohjelmien päivitys. Aloitin avaamalla VirtualBoxilla oman virtuaalikoneen. Seuraavaksi avasin komentorivin ja ajoin ensimmäiseksi sudo apt-get -y update.

Sitten oli aika ottaa yhteys omaan virtuaalipalvelimeen. Tämä tapahtui toiminnolla ssh root@178.62.202.242. Minulta kysyttiin olenko varma, haluanko jatkaa. Painoin y, mutta pitikin kirjoittaa yes ja enter.

<img width="507" alt="viikko4 9" src="https://github.com/user-attachments/assets/ddcd17cd-d769-4bce-a11b-a7756c5336d1">

Sisään päästyäni ajoin ensimmäiseksi sudo apt-get -y update.

<img width="783" alt="viikko4 10" src="https://github.com/user-attachments/assets/7fea5f2d-0c3f-4207-8560-9de9f5ba29dc">

Seuraavana tulimuurin asennus, eli sudo apt-get install ufw.

<img width="308" alt="viikko4 11" src="https://github.com/user-attachments/assets/d6639c1e-2d7d-4e7f-8640-9f28bb0eb234">

Sitten sallin portit 22 ja 80 eli ajoin sudo ufw allow 22/tcp ja sudo ufw allow 80/tcp jonka jälkeen sudo ufw enable.

<img width="446" alt="viikko4 13" src="https://github.com/user-attachments/assets/7fa3119b-c286-4a8a-bf43-32a8bc408751">

Sitten lisäsin itseni käyttäjäksi palvelimelle. Tämä tapahtui sudo adduser eerom. Luotuani vahvan salasanan minulta kysyttiin lisätietoja. Annoin koko nimeni mutta muut kohdat jätin tyhjäksi.

<img width="377" alt="viikko4 14" src="https://github.com/user-attachments/assets/a1aea157-735b-467d-8a0a-90af639d3248">

Sitten lisäsin käyttäjän eerom ryhmään sudo toiminnolla sudo adduser eerom sudo.

<img width="365" alt="viikko4 15" src="https://github.com/user-attachments/assets/7ffca193-541d-4187-8a08-9d2601955b4b">

Poistuin palvelimelta ajamalla exit ja kokeilin ottaa yhteyttä käyttäjällä eerom omalta virtuaalikoneeltani. Tämä tapahtui komennolla ssh eerom@178.62.202.242

Sisään päästyäni ajoin sudo apt-get -y update jonka jälkeen lukitsin root-käyttäjän ajamalla sudo usermod --lock root.

<img width="509" alt="viikko4 17" src="https://github.com/user-attachments/assets/a3aa40c8-81bd-4bb6-b637-720970519e61">

## c) Webbipalvelimen asennus

Tässä kohdassa tehtävänä oli asentaa webbipalvelin ja korvata testisivu omalla. Ensimmäisenä ajoin sudo apt-get install apache2

<img width="949" alt="viikko4 18" src="https://github.com/user-attachments/assets/f3bde4b2-f533-447e-a9a2-70e731e998c2">

Kokeilin tämän jälkeen avata omalla puhelimellani osoitteen 178.62.202.242 ja tuloksena oli Apachen testisivu.

<img width="500" alt="viikko4 20" src="https://github.com/user-attachments/assets/b592ac03-147b-45ed-b3ed-c7c3a96bdba2">

Sieltä luin että minun tulisi korvata tiedosto, joka sijaitsee /var/www/html/index.html. 

Ajoin cd /var/www/html ja tämän jälkeen sudo nano index.html. Poistin alkuperäisen tekstin ja korvasin sen yksinkertaisella html-sivulla. (ChatGPT)

<img width="544" alt="viikko4 19" src="https://github.com/user-attachments/assets/1f92906a-ccf9-462e-a971-2720fcd1a94a">

Tämän tallennettuani kokeilin puhelimella tapahtuiko muutoksia.

<img width="500" alt="viikko4 21" src="https://github.com/user-attachments/assets/7f7a6458-7ec0-419a-963a-a26135efc758">

## Lähteitä

Tero Karvinen. First steps on a New Virtual Private Server. https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/ Luettu 16.9.2024

Susanna Lehto. Teoriasta käytäntöön pilvipalvelimen avulla. https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/ Luettu 16.9.2024

ChatGPT. Yksinkertainen HTML-koodi.



















