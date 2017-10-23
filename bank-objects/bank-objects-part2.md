# Bank Objects - Part 2

Tässä harjoituksessa hyödynnetään edellisessä vaiheessa tehtyä tietokantaa ja luokkakirjastoa.

## Web App

Luo Web-tekniikoilla (HTML, CSS, JS) käyttöliittymä, jossa näytetään
1. Pankit
2. Valitun pankin asiakkaat
3. Valitun asiakkaan tilitiedot ja tilitapahtumat

Ensimmäisessä vaiheessa ei vielä käytetä oikeaa tietokannassa olevaa dataa. 
Luo "kovakoodaten" tarivittavat objectit sovelluksen käynnistyessä ja käytä niitä käyttöliittymän rakentamisessa.

#### Lisähommat
- Tietojen näyttämisen lisäksi toteuta käyttöliittymään mahdollisuus ylläpitää tietoja
    - Pankissa olevien käyttäjien ja tilien luonti/muokkaus/poisto
    - Uusien tilitapahtumien luonti
- Tyylitä sovellus käyttäen [Googlen Material Design tyylejä](https://material.io/components/web/). Valmiiden komponenttien lista [täällä](https://material-components-web.appspot.com/).

## .NET Core Web API

Luo uusi Web API-projekti samaan Visual Studio solutioniin edellisen tehtävän Console Appin ja luokkakirjaston kanssa.
Ohjeet löytyvät [täältä](https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-web-api). 
Tavoitteena olisi luoda [rajapinta](http://www.restapitutorial.com/), jonka kautta web-sovellus pystyisi hakemaan/päivittämään kannassa olevaa dataa.
Tässä voidaan hyödyntää aiemmassa vaiheessa (part1) luotua luokkakirjastoa.

- Client lähettää rajapintaan Http-kutsun. [Esimerkki](https://www.kirupa.com/html5/making_http_requests_js.htm)
- Web API -sovellukseen tehdään rajapinta, joka ottaa Http-kutsun vastaan (Controller)
    - Huom! Tee jokaista model-luokkaa kohti oma controller (BankController, CustomerController, AccountController, TransactionController)
- Web API käyttää olemassa olevaa luokkakirjastoa datan hakuun/päivitykseen.
- Web API palauttaa vastauksen clientille
- Client käsittelee Http responsen.

[Postman](https://www.getpostman.com/) on näppärä työkalu, jolla pystyy helposti testailemaan Http kutsujen lähetystä.


## Links
##### Web App
[HTML](https://www.w3schools.com/html/default.asp)
<br>
[CSS](https://www.w3schools.com/css/css_intro.asp)
<br>
[JavaScript](https://www.w3schools.com/js/default.asp)
<br>
[Material Components for the web](https://material.io/components/web/)
<br>
[Material Design Guide](https://material.io/guidelines/)

##### Web API
[.NET Core Web API](https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-web-api)
<br>
[REST Tutorial](https://www.tutorialspoint.com/restful/restful_introduction.htm)
<br>
[REST API Tutorial](http://www.restapitutorial.com/)
