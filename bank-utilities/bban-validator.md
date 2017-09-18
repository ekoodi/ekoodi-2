## BBAN-tarkistus

Toteuta C#-ohjelmointikielellä .NET Core konsolisovellus, joka muuntaa käyttäjän syöttämän BBAN-muotoisen tilinumeron konekieliseen muotoon ja tarkistaa syötetyn tilinumeron tarkisteen.

### Vaatimukset

Sovelluksen tulee tukea suomalaisen BBAN-muotoisen tilinumeron muuntamista perusmuodostaan konekieliseen muotoon ja tilinumeron tarkisteen tarkistamista.

Suomalainen BBAN-muotoinen tilinumero koostuu perusmuodossaan 6 numerosta, väliviivasta ja 2-8 numerosta. Käyttäjä voi syöttää tilinumeron väliviivalla tai ilman.

Sovellus muuntaa syötetyn tilinumeron konekieliseen muotoon ja laskee syötetyn tilinumeron tarkisteen, jonka perusteella tarkistetaan, että syötetty tilinumeron on oikea.

Sovellus tulostaa käyttäjän syöttämän tilinumeron konekielisessä muodossa ja tiedon siitä, onko tilinumeron tarkiste oikea.

### Määrittelyt

Suomalaisen BBAN-muotoisen tilinumeron rakenteen ja tarkisteen määrittely jaetaan Flowdockin kautta.
