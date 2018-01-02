# contacts-app Azure Active Directory Graph API

Azuren Active Directoryssa olevan käyttäjän tietojen haku Graph API:n kautta.

## TODO

Toteuta käyttäjärajapinta, joka hakee ja palauttaa autentikoituneen käyttäjän tiedot Azure AD:sta.
- UserController (api/user), kutsuu UserServiceä, joka palauttaa userin. Autentikoituneen käyttäjän käyttäjätunnuksen saa controllerilla seuraavasti: var username = User.Identity.Name;
- UserService, johon rakennetaan tietojen haku Azuresta.
- User-luokka, jolla propertyna ainakin etunimi ja sukunimi. Muodostetaan Azuresta saatavilla tiedoilla.
- Azure AD:sta kysellään tietoja [Graph API:n](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-graph-api) kautta. 
Graph API:n käyttö vaatinee perehtymistä aiheeseen. Näillä pääsee alkuun:
    - https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-graph-api-quickstart
    - https://msdn.microsoft.com/en-us/library/azure/ad/graph/api/users-operations
- Graph API vaatii autentikoitumisen ja tokenin lähettämisen jokaisen kutsun Authorization headerissa.

Kutsu edellä toteutettua käyttäjärajapintaa web-sovelluksesta kirjautumisen yhteydessä heti autentikoinnin jälkeen. 
Näytä käyttäjän tiedot haluamallasi tavalla käyttöliittymässä.

Jos haluaa hifistellä, voisi back-endissä kaikki Azureen liittyvät toiminnot paketoida yhteen luokkakirjastoon, josta niitä sitten kutsutaan serviceiltä.