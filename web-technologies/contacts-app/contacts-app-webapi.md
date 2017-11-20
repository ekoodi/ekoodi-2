#contacts-app back-end (API)
Harjoituksessa toteutetaan .NET Core Web API sovellus, joka toimii back-endinä contacts-app Angular-sovellukselle.

### Repository

Muokkaa olemassa olevaa contacts-app repositorya siten, että luot sinne kaksi uutta hakemistoa:
- webapp
    - tänne tulee client/front-end
    - siirrä olemassa olevan angular-sovelluksen koodit tähän kansioon
- webapi
    - tänne tulee back-end-sovellus
    
<img src="https://raw.githubusercontent.com/ekoodi/ekoodi-2/master/assets/contacts-app-webapi-repo-folders.png"></img>    
    
 ### .NER Core Web API
 
 Luo Visual Studiolla uusi .NER Core Web API -projekti repositoryn web-api hakemistoon.
 Ohjeita [täällä](https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-web-api).
 
<img src="https://raw.githubusercontent.com/ekoodi/ekoodi-2/master/assets/contacts-app-webapi-project-files-folders.png"></img>
 
 Luo projektin sisälle seuraava hakemistorakenne:
 - Controllers
    - Rajapintaluokat, jotka ottavat vastaan HTTP-kutuja. Controllereiden kautta sovellus näkyy ulos päin.
 - Services
    - Service-kerrokseen rakennetaan sovelluksen bisneslogiikkaa. Servicet palauttavat datan controllereille.
 - Repositories
    - Repository-kerros vastaa datan käsittelystä. (Tänne rakennetaan myöhemmin yhteydet tietokantaan)
 - Models
    - Sovelluksen model-luokat (esim. Contact)
    
    
 Luo ContactController, joka tarjoaa seuraavat metodit:
    - HttpGet: Kaikkien contactien haku 
    - HttpGet: Contactin haku id:llä
    - HttpPost: Uuden contactin luonti
    - HttpPut: Vanhan contactin päivitys
    - HttpDelete: Contactin poisto
    
 Metodien testaamiseen ja Http-kutsujen lähettämiseen kannattaa hyödyntää [Postmania](https://www.getpostman.com/).
    
    
 Luo metodien tarvitsemat servicet ja repositoryt ja käytä niitä Dependency Injectionin kautta. 
 Jotta Dependency Injection toimii, täytyy ne lisätä sovelluksen ServiceCollectioniin (startup.cs/ConfigureServices).
 
 Luo repository-luokkaan privaatti _contacts-lista, jossa ylläpidetään contacteja.


### Links

[Web API -projektin luonti](https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-web-api)

[REST API tutorial](http://www.restapitutorial.com/)

[Http Status codes](http://www.restapitutorial.com/httpstatuscodes.html)

[Hyvää juttua ActionResultista ja palautettavista statuskoodeista](http://hamidmosalla.com/2017/03/29/asp-net-core-action-results-explained/#wprar)

