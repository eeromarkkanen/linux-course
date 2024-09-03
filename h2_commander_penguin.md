## Command line basics

x) Aloitin lukemalla kotitehtävän kokonaan ja tarkastelemalla mitä ymmärrän heti. Sen jälkeen luin Command Line Basics Revisited (https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited)
kokonaan. Tämä artikkeli käy läpi komentorivin tärkeimpiä toimintoja.

- Ensin liikkuminen komentorivillä: pwd, ls, cd jne.
- Tiedostojen ja kansioiden tekeminen, siirtäminen ja poistaminen: mkdir, mv, cp, rm jne.
- Turvatun etäyhteyden ottaminen: ssh
- Apua: man, --help
- Historia: history
- Tärkeät directoryt
- Hallinnalliset komennot kuten sudo apt-get update

  Artikkelissa käytiin läpi lähes kaikki tarvittava kotitehtävän suorittamiseen. Lopussa myös näytettiin miten ohjelmia asennetaan ja kuinka voidaan asentaa monta ohjelmaa kerralla.

  ** a)

  Aloitin ajamalla sudo apt-get -y install micro

  ![Näyttökuva 2024-09-03 093954](https://github.com/user-attachments/assets/5b4163db-98ec-4c40-b1f5-ef15715062f9)

  ** b)

  En tiennyt, mitä ohjelmia asentaa joten kopioin suoraan kolme ohjelmaa Command Line Basics sivun alalaidasta. Valitsin kolme ensimmäistä eli krita, blender ja vlc.

  Ajoin sudo apt-get -y install krita blender vlc. Sitten avasin ohjelmat komennoilla krita, blender ja vlc erikseen.

  Krita:

  <img width="572" alt="viikko2 1" src="https://github.com/user-attachments/assets/c6e6c7a0-36c3-4475-af99-71952f623d85">

  Blender:

  <img width="682" alt="viikko2 2" src="https://github.com/user-attachments/assets/60cdd72e-65a3-47de-a84f-5ee461c524ce">

  VLC:

  <img width="501" alt="viikko2 3" src="https://github.com/user-attachments/assets/dabaa77b-c92c-4f9a-a8cf-58f5edd25b09">

  Lisäksi kysyin tekoälyltä esimerkkejä ohjelmista mitä voisi asentaa, joten asensin ohjelman nimeltä cmatrix. Se vain täyttää näytön Matrix-tyylisellä valuvalla tekstillä:

  <img width="679" alt="viikko2 4" src="https://github.com/user-attachments/assets/dfb92797-ae29-4a09-ae2d-f58d3cbc6eb2">

  ** c)

  Kävin komentorivillä läpi seuraavat directoryt ja yritin katsella tiedostoja niiden sisällä.

  /

  <img width="389" alt="viikko2 5" src="https://github.com/user-attachments/assets/580f8fb5-4aa0-46d1-a0b1-a09674baaecb">

  Kokeilin cd dev:

  <img width="647" alt="viikko2 6" src="https://github.com/user-attachments/assets/100abbd9-5170-48d5-ac40-979f396cf372">

  Seuraavana /home/

  <img width="132" alt="viikko2 7" src="https://github.com/user-attachments/assets/dce2832c-7bd6-4456-a79c-6ba7f49914c8">

  Sieltä en päässyt kuin home/eerom/ , jossa kaikki kansiot olivat tyhjiä.

  <img width="397" alt="viikko2 8" src="https://github.com/user-attachments/assets/1c6062e9-1223-46f3-8ad8-20c927b2514c">

  Sitten menin /etc/

  <img width="680" alt="viikko2 9" src="https://github.com/user-attachments/assets/825b0196-7917-45d4-98c9-c48f947a16ff">

  Menin tutkimaan mitä löytyy vaikkapa fonts-kansiosta. En ymmärtänyt paljoakaan niin menin pois.

  <img width="533" alt="viikko2 10" src="https://github.com/user-attachments/assets/49ea87b5-c7dd-49d7-a12e-4711f498c03a">

  /media/ en löytänyt sisältä mitään.

  <img width="400" alt="viikko2 11" src="https://github.com/user-attachments/assets/560f2fec-2093-4f1c-818a-7b1de0c5b234">

  Lopuksi vielä /var/log/

  <img width="647" alt="viikko2 13" src="https://github.com/user-attachments/assets/b1a86967-6274-467f-be34-e9a54c371b1d">

  Kokeilin less README ja siitä aukesi tämä:

  <img width="443" alt="viikko2 12" src="https://github.com/user-attachments/assets/25aeb333-1412-4f31-ab70-26b90053a232">

  ** d)

  Seuraavaksi opettelin grep toiminnon käyttöä. Ensin avasin man grep ja tutkin sitä hetken. Todettuani sen hyvin pitkäksi tekstiksi lähdin etsimään netistä ohjeita. Google
  tarjosi verkkosivua digitalocean.com ja luinkin sieltä ohjeita.

  Ensin loin nanolla tekstitiedoston tiedosto.txt, mihin kirjoitin muutaman kerran "testi" ja numeroita. Ensin kokeilin grep "kaksi" tiedosto.txt. Se palautti rivit, joissa oli
  "kaksi" kirjoitettuna. Digitalocean myös opetti värjäämään tulokset joten kokeilin sitä: grep --color "testi" tiedosto.txt ja se palautti punaisella rivit, joissa oli sana "testi".
  Kokeilin vielä kolmantena muokata tekstitiedostoa, että sana "testi" esiintyy myös isoilla kirjaimilla ja samalla rivillä numeroiden kanssa. Ajoin grep -i --color "testi" tiedosto.txt ja
  se palautti kaikki rivit, joissa "testi" oli miten tahansa kirjoitettuna. Alla olevassa screenshotissa näkyy kaikki kokeilut.

  <img width="410" alt="viikko2 16" src="https://github.com/user-attachments/assets/0f6b697f-670b-4d70-9d68-181aa3af5812">

  ** e)

  Kokeilin esimerkissä ollutta ls /etc|less ja se listasi kaiken sisällön samalla sivulle. En vielä ihan ymmärtänyt putkien käyttöä joten googletin ja kysyin tekoälyltä helppoja
  ohjeita. Tämän jälkeen vasta ymmärsin, että | voi yhdistää komentoja. Joten jatkoin edellisestä tehtävästä ja yhdistin grep ja |. Kokeilin grep "testi" tiedosto.txt | wc -l ja
  tuloksena oli 5 riviä.

  <img width="295" alt="viikko2 17" src="https://github.com/user-attachments/assets/20ae1f56-4dfd-48c2-bc67-0186968050c2">

  ** f)

  Ajoin ensin sudo apt-get install lshw. Sitten ajoin sudo lshw -short -sanitize ohjeen mukaan. En ymmärrä kovinkaan paljoa tuloksesta. Tulos listaa H/W path, device, class ja description.
  Tunnistin kyllä että systeemi on VirtualBox, muistina asetettu muisti ja prosessorina oma tietokoneeni. Muista kohdista en paljoa ymmärtänyt.

  <img width="437" alt="viikko2 18" src="https://github.com/user-attachments/assets/a3979b44-b924-4297-85db-299e2b8c5a0d">

  ** Lähteet

  Command Line Basics Revisited. https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited Luettu 3.9.2024

  Grep Command in Linux. DigitalOcean. https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix Luettu 3.9.2024

  Tekoäly. ChatGPT. Esimerkkejä ladattavista ohjelmista komentorivillä ja esimerkki putken käytöstä. chat.openai.com

  

  
  

  


  



  

