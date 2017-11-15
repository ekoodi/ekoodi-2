# contacts-app authentication

Toteutetaan sovellukseen alustava käyttäjän kirjautumiseen liittyvä toiminnallisuus

## Projektin rakenne

kuva

### User

Luokka, joka kuvaa sovelluksen käyttäjää. Alustavassa toteutuksessa käyttäjän tiedot voivat olla esimerkiksi:
- firstName
- lastName
- userName
- password

Käyttäjä kirjautuu käyttäjänimen tai sähköpostiosoitteen (userName) ja salasanan (password) perusteella.

### Login component

Komponentti, joka toteuttaa käyttäjän kirjautumiseen liittyvän käyttöliitymän. Esimerkiksi:

kuva

### Authentication Service

Palvelu, joka toteuttaa alustavassa toteutuksessa toiminnallisuuden käyttäjän sisään kirjautumiseen, ulos kirjatumiseen ja kirjautumisstatuksen tarkistamiseen. Palveluun voi toteuttaa myös toiminnallisuuden kirjautuneen käyttäjän tietojen hakemiseen, toiminnallisuutta voidaan käyttää kirjautuneen käyttäjän tietojen esittämiseen käyttöliittymässä. Alustavassa toteutuksessa käyttäjän kirjautumistietojen tarkistus tehdään palvelun toimesta, käyttäen palvelun toteutukseen koodattuja kirjautumistietoja, joita vasten käyttäjän syöttämät kirjautumistiedot tarkistetaan. Metodit, esimerkiksi:
- login
- logout
- isAuthenticatedUser
- getAuthenticatedUser

### Routing

Optionaalisesti, toteutetaan lisäksi sovelluksen reititystoiminnallisuuteen suojaus, joka sallii suojattujen näkymien näyttämisen vain kirjauneille käyttäjille. Esimerkiksi kontaktilista-näkymä näytetään vain kirjautuneelle käyttäjälle, muutoin näkymään navigointi on estetty.

#### Authentication Guard, CanActivate

Toteuta sovellukseen AuthenticationGuard, jonka avulla sallitaan suojattuihin näkymiin navigointi vain kirjautuneille käyttäjille. AuthenticationGuard toteuttaa Angularin routerin CanActivate rajapinnan mukaisen toiminnallisuuden, toteutuksessa voidaan tarkistaa käyttäjän kirjautumissatus käyttäen toteutettua Authentication Servicen metodia.

#### Routes

Ota AuthenticationGuard käyttöön suojattaville routeille, routen määrittelyssä.

## Links

linkit
