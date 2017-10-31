# contacts-app

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

#### contact-list.component
Component, joka kysyy ContactServiceltä contact-objectit ja listaa ne templatella. 
Listaus tapahtuu looppaamalla (*ngFor) ContactListItemComponenttia, jolle välitetään contact-object käyttäen property bindingia.


#### contact-list-item-component
Component, joka ottaa inputtina (@Input()) contact-objectin ja esittää sen tiedot templatella (interpolation binding) 

## Links
