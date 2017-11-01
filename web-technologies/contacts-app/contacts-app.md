# contacts-app

Toteutetaan Angular-sovellus, jolla käyttäjä pystyy katselemaan tallettamiaan yhteystietoja.


## Tiedostot ja hakemistot
<img height=500 src="https://raw.githubusercontent.com/ekoodi/ekoodi-2/master/assets/contacts-app-files.png"></img>

#### contact
Luokka, josta muodostetaan contact-objecteja
- id
- firstName
- lastName
- phone
- streetAddress
- city

#### contact.service
Service, joka tarjoaa työkalut contact-objectien varastoimiseen selaimen local storageen.
- findContacts
- findContactById
- saveContact
- deleteContact

Contact-objectit kannattaa tallettaa local storageen JSON muodossa. Tässä voi hyödyntää JavaScriptin [JSON-objectia](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify).

#### contact-list.component
Component, joka kysyy ContactServiceltä contact-objectit ja listaa ne templatella. 
Listaus tapahtuu looppaamalla (*ngFor) ContactListItemComponenttia, jolle välitetään contact-object käyttäen property bindingia.


#### contact-list-item-component
Component, joka ottaa inputtina (@Input()) contact-objectin ja esittää sen tiedot templatella (interpolation binding). 


## UI/UX
Toteuta mieleisesi käyttöliittymä, joka noudattaa Google Material Design käyttöliittymäohjeistusta. 
Hyödynnä käyttöliittymässä Angular Materialin käyttöliittymäkomponentteja. Yhteystietojen listan voisi toteuttaa esim. 
Angular Materialin Card tai List komponenteilla.

## Linkit

[Angular](https://angular.io/guide/architecture)
<br>
[Angular Material](https://material.angular.io/guide/getting-started)
<br>
[Google Material Design](https://material.io/guidelines/)
<br>
[Local Storage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
<br>
[Inspect Local Storage using Google Developer Tools](https://developers.google.com/web/tools/chrome-devtools/manage-data/local-storage)
<br>
[JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify)
<br>
