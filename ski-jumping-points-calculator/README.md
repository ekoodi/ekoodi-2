##Laadi C# -ohjelma m‰enlaskun pistelaskentaan. Toteuta graafinen k‰yttˆliittym‰ haluamallasi tavalla.
Mieti millaista tietoa j‰rjestelm‰‰n tarvitaan etuk‰teen ja mit‰ kilpailun aikana. Kilpailun edetess‰ pisteet lasketaan oheisen kuvauksen mukaisesti. 

**Tulokset** ilmoitetaan parhaan tulos ensin jne.

###Hypyn pituus

Jokaisella m‰ell‰ on oma K-pisteens‰ (kriittinen piste), joka kertoo m‰en kokoluokan. Suurm‰eksi luokitellaan m‰et, joissa K-piste on yli 100 metri‰. Lahden suurm‰ess‰ se on 116 metri‰. K-pisteeseen ylt‰neest‰ hypyst‰ saa aina 60 pituuspistett‰. K-pisteen ylitt‰minen tuo lis‰pisteit‰, ja sen alle j‰‰minen johtaa puolestaan pistev‰hennyksiin. Hyvityksen ja v‰hennyksen suuruus vaihtelee m‰en koon mukaan (pienemm‰ss‰ m‰ess‰ suhteessa suurempi kuin isommassa m‰ess‰), ja esimerkiksi suurm‰ess‰ se on 1,8 pistett‰ metri‰ kohden.

**Esimerkki:** Hypp‰‰j‰ A ponkaisee Lahden suurm‰est‰ 124 metri‰. H‰n saa automaattiset 60 pistett‰ K-pisteen ylitt‰misest‰ ja lis‰ksi hyvityst‰ kahdeksasta lis‰metrist‰: 60 + 8 x 1,8 = 74,4 pistett‰.

###Hypyn tyyli

Tyylipisteet m‰‰r‰ytyv‰t ilmalennon, alastulon ja sit‰ seuraavan loppuliun kokonaisuutena. Arvostelijoina toimii viisi tuomaria, mutta hypp‰‰j‰n tyylipisteisiin ei lasketa eniten ja v‰hiten pisteit‰ antaneiden tuomareiden pisteit‰. Virheettˆm‰st‰ suorituksesta saa 20 pistett‰ kultakin tuomarilta, joten hypp‰‰j‰n maksimityylipisteet ovat 60.

**Esimerkki:** Hypp‰‰j‰ A saa tuomareilta tyylipisteet kerran 18, kaksi kertaa 18,5 ja kaksi kertaa 19. Heikoin (18) ja paras (19) pistem‰‰r‰ poistetaan, joten tyylipisteet ovat: 18,5 + 18,5 + 19 = 56.

###Tuulihyvitys/-v‰hennys

Kunkin hypyn aikana tuuli mitataan viidest‰ kohdasta, joiden avulla lasketaan keskiarvo tuulen suunnalle ja voimakkuudelle. Hypp‰‰j‰lle annetaan takatuulesta hyvitysmetrej‰ ja vastatuulesta puolestaan tehd‰‰n v‰hennyksi‰. V‰hennyksen tai hyvityksen kokoon vaikuttavat tuulen voimakkuus ja m‰en K-piste seuraavan kaavan mukaan:

Tuulen vaikutus hypyn pituuteen = Tuulen voimakkuuden keskiarvo x (K-piste - 36)/20

**Esimerkki:** Hypp‰‰j‰ A:n 124 metrin hypyn aikana puhalsi 1,4 metrin takatuuli. H‰n saa siis hyvitysmetrej‰ seuraavanlaisesti: 1,4 x (116 - 36)/20 = 5,6. Metrim‰‰r‰ pyˆristet‰‰n puolen metrin tarkkuudella eli t‰ss‰ tapauksessa 5,5 metriin. Pisteiksi muutettuna se tekee 1,8 x 5,5 = 9,9.

###L‰htˆlavahyvitys/-v‰hennys

L‰htˆlavaa voidaan nyky‰‰n muuttaa kesken hyppykierroksen. Hypp‰‰j‰ saa hyvitysmetrej‰ jos h‰n l‰htee suoritukseensa kilpailun aloituslavaa alempaa ja puolestaan v‰hennyksi‰ l‰htiess‰‰n ylemp‰‰. Hyvityksen tai v‰hennyksen suuruus vaihtelee m‰en koon mukaan, mutta esimerkiksi suurm‰ess‰ metrin muutos vauhdinotossa on katsottu vastaavan viitt‰ metri‰ hypyn pituudessa.

**Esimerkki:** Hypp‰‰j‰ A l‰htee suoritukseensa 1,4 metri‰ ylemp‰‰ kuin mist‰ kilpailu aloitettiin. T‰llˆin h‰nen hypyn pituudesta v‰hennet‰‰n 1,4 x 5 metri‰ = 7 metri‰. Pistein‰ se on 1,8 x 7 = 12,6.

Vihdoinkin kisaorganisaatio on valmis paljastamaan hypp‰‰j‰ A:n hirmuloikan kokonaispisteet: 74,4 + 56 + 9,9 - 12,6 = 127,7.

Ja m‰kimonttu riehaantuu!

**L‰hde:**

www.fis-ski.com

---
**Ja koko yll‰oleva taitaapi olla napsaistu t‰‰lt‰:**

http://www.ess.fi/urheilu/hiihtolajit/2013/03/06/ja-kokonaispisteet-ovat-nain-sujuu-makihypyn-pistelasku