# contacts-app authentication

Toteutetaan sovellukseen autentikointi Azuren Active Directorya vasten. Suojataan API autentikoinnilla.

"<b>Authentication</b> is the process of ascertaining that somebody really is who he claims to be.
<br><b>Authorization</b> refers to rules that determine who is allowed to do what."

<img src="https://raw.githubusercontent.com/ekoodi/ekoodi-2/master/assets/Authentication.png"></img>

## Azure
### Azure Active Directory
- Lisää AD:hen uusi käyttäjä, jota käytetään sisäänkirjautumisessa ja autentikoinnissa.
- Anna Back-endille lupa käyttää AD:ta, rekisteröimällä se AD:ta käyttäväksi sovellukseksi (ks. linkki alla). Anna tarvittavat oikeudet autentikoinnin mahdollistamiseksi.
- Etsi Azure AD:sta seuraavat tiedot, joita tarvitaan autentikoinnissa:
    - Application id
    - Directory id
    - Key / Client secret (pitää luoda)
    
### Access Token

Tutustu [OAuth2 protokollaan](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-protocols).

Testaa autentikointia postmanilla. Esimerkki löytyy [flowdockista](https://www.flowdock.com/app/saimia/webapps/threads/sM5uD3l6YC9ZtDG1KaF4H3J-qbc).
- Http Post osoitteeseen https://login.windows.net/directoryId/oauth2/token.
- bodyyn:
    -  username: aiemmin luodun AD-käyttäjän käyttäjätunnus
    -  password: aiemmin luodun AD-käyttäjän salasana
    -  client_id: rekisteröidyn sovelluksen application id
    -  resource: directory id
    -  grant_type: password
    -  client_secret: AAD:ssa generoitu key
- Vastauksena saat access tokenin ([kohta "Successful Response"](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-protocols-oauth-code#oauth-20-authorization-flow)).
Se sisältää [JWT-muotoisen](https://jwt.io/introduction/) tokenin, jonka sisältöä voit tutkailla vaikka [tällä](https://jwt.io/) työkalulla.

## Web API
### Autentikointirajapinta

Toteuta back-end sovellukseen autentikointirajapinta (AuthenticationController), johon voidaan Http Post -requestilla lähettää käyttäjätunnus ja salasana.
Back-end autentikoi käyttäjän Microsoftin autentikointi-palvelua vasten tekemällä samanlaisen Http-requestin kuin aiemmin Postmanilla testatessa.
Onnistuneen autentikoinnin jälkeen rajapinta palauttaa access tokenin. Muuten palautetaan "401 Unauthorized".

Tämän toteutukseenkin löytyy apuja [flowdockista](https://www.flowdock.com/app/saimia/webapps/threads/sM5uD3l6YC9ZtDG1KaF4H3J-qbc).
Tokenin hakuun liittyvät toiminnot kannattaa laittaa omaan serviceensä (esim. TokenService), jota kutsutaan controllerilta.

### Autentikoinnin konfigurointi .NET Core Web API:ssa

Suojaa back-endin rajapinta autentikoinnilla. Tähän löytyy ohjetta mm. [täältä](https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/web-api) ja [flowdockista](https://www.flowdock.com/app/saimia/webapps/threads/sM5uD3l6YC9ZtDG1KaF4H3J-qbc).
Testaa rajapinnan kutsumista Postmanilla. Kokeile tokenilla ja ilman tokenia. [Ohjeet](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-protocols-oauth-code#use-the-access-token-to-access-the-resource) tokenin välittämiseen Http-requestin headerissa.

Huom! Rajapinnan täytyy palauttaa HTTP status code 401 Unauthorized, jos autentikointi ei onnistu (käyttäjätunnus/salasana ei täsmää).


## Web app
### Web App autentikointi ja kirjautuminen
Toteuta web-sovellukseen kirjautumisnäyttö (uusi route), jolla käyttäjä syöttää käyttäjätunnuksen ja salasanan.
Kirjaudu-painikkeen klikkauksella sovellus autentikoi käyttäjän kutsumalla edellisessä vaiheessa tehtyä autentikointirajapintaa.
Jos autentikointi onnistui, käyttäjä pääsee sisään sovellukseen. Samalla sovellus ottaa talteen autentikoinnissa saadun access tokenin. 

Mikäli autentikointi epäonnistuu, annetaan käyttäjälle virheilmoitus. Käytä virheiden nappaamiseen/käsittelyyn seuraavan kohdan HttpInterceptoria. 
Virheilmoituksen voi näyttää vaikka Angular Materialin [dialogissa](https://material.angular.io/components/dialog/overview).


### Web App HttpInterceptor ja tokenin lähetys
Jotta autentikoinnilla suojattua rajapintaa api/contacts voidaan kutsua, täytyy autentikoinnissa saatu token välittää jokaisessa
rajapintakutsussa. Token asetetaan HTTP-kutsun Authorization headeriin.

Hyödynnä tokenin välityksessä Angularin [HttpInterceptoria](https://angular.io/api/common/http/HttpInterceptor), jolla tokenin saa keskitetysti lisättyä jokaisen kutsun headeriin.
Esimerkki HttpInterceptorin käytöstä löytyy [täältä](https://www.intertech.com/Blog/angular-4-tutorial-handling-refresh-token-with-new-httpinterceptor/) ja
lisää ohjeita [täältä](https://www.google.com).

Huom! HttpInterceptor on kätevä myös HTTP-kutsuissa tapahtuvien virheiden käsittelemiseen keskitetysti.

# Links
[Azure AD App Registrations](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-integrating-applications)

[Azure OAuth 2](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-protocols).

[FlowDock]([flowdockista](https://www.flowdock.com/app/saimia/webapps/threads/sM5uD3l6YC9ZtDG1KaF4H3J-qbc))

[JWT](https://jwt.io/introduction/)

[Angular HttpInterceptor](https://angular.io/api/common/http/HttpInterceptor)
