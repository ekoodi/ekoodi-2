## IBAN-muunnos ja -tarkistus

Toteuta ensin C#-ohjelmointikielellä .NET Core konsolisovellus, joka muuntaa käyttäjän syöttämän BBAN-muotoisen tilinumeron IBAN-muotoon. Laajenna tämän jälkeen sovelluksen toteutus tukemaan myös käyttäjän syöttämän IBAN-muotoisen tilinumeron tarkistusta ja tilinumeroon liittyvän BIC-koodin tunnistamista.

### Vaatimukset

#### IBAN-muunnos

Sovelluksen tulee tukea suomalaisen BBAN-muotoisen tilinumeron muuntamista IBAN-muotoon.

Käyttäjä voi syöttää BBAN-muotoisen tilinumeron samoin, kuin BBAN-tarkistimen tapauksessa.

Sovellus hyödyntää BBAN-tarkistimessa toteutettuja toiminnallisuuksia tilinumeron muuntamiseksi konekieliseen muotoon ja tilinumeron tarkisteen laskemiseksi.

Mikäli käyttäjän syöttämä tilinumeron on oikea, sovellus muuntaa BBAN-muotoisen tilinumeron IBAN-muotoon ja tulostaa IBAN-muotoisen tilinumeron.

#### IBAN-tarkistus

Sovelluksen tulee tukea suomalaisen IBAN-muotoisen tilinumeron tarkistamista ja BIC-koodin tunnistamista.

### Määrittelyt

Tutustu Finanssialan Keskusliiton oppaisiin:
http://www.finanssiala.fi/maksujenvalitys/dokumentit/Suomalaiset_rahalaitostunnukset_ja_BIC-koodit.pdf
http://www.finanssiala.fi/maksujenvalitys/dokumentit/IBAN_ja_BIC_maksuliikenteessa.pdf
