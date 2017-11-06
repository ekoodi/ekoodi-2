# contacts-app layout

## Components
- ContactListComponent
- ContactDetailsComponent (huom! käytetään sekä uuden yhteystiedon lisäyksessä että vanhan muokkauksessa)

## Routes
Konfiguroi sovellukseen routet seuraavia näkymiä varten:
 - yhteystietojen listaus
    - path: contacts
    - component: ContactListComponent
 - yhteystiedon lisäys
    - path: add-contact
    - component: ContactDetailsComponent
 - yhteystiedon muokkaus
     - path: contacts/:id   !!!katso linkki parametrin käytöstä!!!
     - component: ContactDetailsComponent
 
 Lisää <router-outlet></router-outlet> app.component.html:ään. 
 Edellä konffatut routet (routen komponentit) ilmestyvät angular routerin toimesta tähän kohtaan.
 
 ## UI
 - Lisää AppComponentin templateen toolbar ja sidenav, jotka toimivat "kehyksenä" RouterOutletissa vaihtuville komponenteille.
 - Lisää ContactListComponentille "Lisää"-nappi, jolla navigoidaan routeria käyttäen ContactDetailsComponentille ja voidaan perustaa uusi yhteystieto.
 - Lisää ContactListComponentille tai ContactListItemComponentille nappi/linkki, jolla navigoidaan routeria käyttäen ContactDetailsComponentille ja voidaan muokata olemassa olevaa yhteystietoa.
 
 Käyttöliittymän rakentelussa kannattaa hyödyntää [flex-layoutia](https://github.com/angular/flex-layout/wiki/Using-Angular-CLI)
 
 ## Links
 
 [Angular Router](https://angular.io/guide/router)
 <br>
 [Angular Router Parameter](https://angular.io/guide/router#route-definition-with-a-parameter)
 <br>
 [Angular Material Sidenav](https://material.angular.io/components/sidenav/overview)
 <br>
 [Angular Material Toolbar](https://material.angular.io/components/toolbar/overview)
 <br>
 [Angular flex-layout](https://github.com/angular/flex-layout/wiki/Using-Angular-CLI)
 <br>
 