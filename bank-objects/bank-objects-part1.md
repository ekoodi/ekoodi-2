# Bank Objects - Part 1

Ennen aloitusta
- Asenna Microsoft SQL Server Express
- Asenna Microsoft SQL Server Management Studio

## Tietokanta

<img src="https://raw.githubusercontent.com/ekoodi/ekoodi-2/master/assets/bankdb-diagram.png"/>

### Tietokannan perustaminen
1. Luo uusi tietokanta (bankdb)
2. Suunnittelu. Luo uusi tietokantadiagrammi (ks. kuva yllä), jossa määrittelet seuraavat taulut ja niiden väliset relaatiot:
    - Bank
    - Customer
    - BankAccount
    - BankAccountTransaction
3. Luo diagrammista varsinaiset taulut tietokantaan (== tallenna diagrammi)

### SQL-kyselyt
Tee seuraavat käyttäen SQL-kyselyitä. Älä oikaise käyttämällä Management Studion graafista Table Designeria, jolla pystyy myöskin ylläpitämään taulun sisältöä.

1. Lisää Bank-tauluun kaksi uutta pankkia
2. Lisää Customer-tauluun kolme uutta asiakasta
3. Lisää BankAccount-tauluun jokaista asiakasta kohden yksi pankkitili. Pankkitilillä on relaatio asiakkaan lisäksi johonkin pankkiin.
4. Lisää BankAccountEvent-tauluun tilitapahtumarivejä


## Console App + Entity Framework
1. Tutustu [Entity Frameworkiin]((https://docs.microsoft.com/en-us/ef/core/))
2. Asenna Visual Studioon [EF Core Power Tools](https://github.com/ErikEJ/SqlCeToolbox/wiki/EF-Core-Power-Tools) Extension
3. Tee uusi Console App -sovellus
4. Lisää solutioniin luokkakirjasto, johon rakennetaan tietokannan käpistely
5. Lisää luokkakirjastoon nugetilla dependency Microsoft.EntityFrameworkCore
6. Käytä Power Toolsin "Reverse engineering" toimintoa ja generoi aiemmin luodusta tietokannasta model-luokat ja DatabaseContext luokkakirjastoon
    - "Project path" == Models (luo uuden kansion luokkakirjaston alle, generoidut tiedostot tupsahtavat tänne)
    - Täppä kohtaan "Use Data Annotation attributes to configure the model"
7. Tee luokkakirjastoon luokat ja funktiot, joilla saat hoidettua seuraavat toiminnot:
    - lisää/päivitä/poista pankki
    - lisää pankkiin uusi asiakas ja asiakkaalle tili
    - hae pankissa olevat tilit
    - hae pankin asiakkaat
    - päivitä/poista asiakastiedot
    - poista asiakkaan tili
    - hae asiakkaan tilit ja niiden saldot
    - luo asiakkaalle tilitapahtumia
    - hae asiakkaan tilitapahtumat
    <br><br>Huom! mieti toiminnallisuuden jakamista useampiin luokkiin, ettei yhden luokan koodimäärä paisu liian suureksi.
    Esim. tiettyyn tauluun kohdistuvat toiminnot omaan luokkaansa.<br>
    
8. Testaa tekemiäsi funktioita console-sovelluksen pääohjelmassa.


## Links
[Entity Framework Core](https://docs.microsoft.com/en-us/ef/core/)
<br>
[SQL Server Management Studio](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms)
<br>
[SQL Tutorial](https://www.w3schools.com/sql/)