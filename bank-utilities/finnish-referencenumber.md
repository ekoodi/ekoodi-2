## Kansallisen viitenumeron tarkistus ja luominen

Toteuta C#-ohjelmointikielellä .NET Core konsolisovellus, joka tukee kansallisten viitenumeroiden tarkistamista ja luomista.

### Vaatimukset

Sovelluksen tulee tukea suomalaisen kansallisen viitenumeron tarkistamista ja luomista.

Sovelluksen tulee toteuttaa seuraavat toiminnallisuudet:

1. Kansallisen viitenumeron tarkistaminen
2. Kansallisen viitenumeron luominen, joko yksittäin tai useita viitenumeroita kerrallaan

__esim. 1.__

Correct input:
- input: 12345672
- output: 123 45672 - OK

Incorrect input:
- input: 12345673
- output: Referencenumber Incorrect

__esim. 2.__

- input: 1234567
- output: 123 45672

__esim. 3.__

Input:

Referencenumber basepart: 123456

Amount of referencenumbers: 10

Output:

Generated referencenumbers:

1. 123 45614
2. 123 45627
3. 123 45630
4. 123 45643
5. 123 45656
6. 123 45669
7. 123 45672
8. 123 45685
9. 123 45698
10. 1234 56104

### Määrittelyt

Tutustu Finanssialan Keskusliiton oppaaseen:
http://www.finanssiala.fi/maksujenvalitys/dokumentit/kotimaisen_viitteen_rakenneohje.pdf
