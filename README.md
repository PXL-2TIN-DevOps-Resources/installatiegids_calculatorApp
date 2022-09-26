# Installatiegids calculator app
Voor deze installatiegids maken we gebruik van een Ubuntu 20.04 machine.

## Installatie NodeJS & NPM
Voor de installatie van onze calculator applicatie maken we gebruik van NodeJS 14. Om deze te installeren voer je volgende commando's uit:
```
$ sudo apt-get update
$ curl -sL https://deb.nodesource.com/setup_14.x | sudo bash -

```
_tip: je kan met bovenstaande eender welke versie van NodeJS eenvoudig installeren. Als alternatief zou kunnen werken met een tool zoals [nvm](https://github.com/nvm-sh/nvm)._

Vervolgens kunnen we zowel NodeJS als npm installeren met het volgende commando:
```
$ sudo apt-get install nodejs
```

## installeren van de dependencies

Zorg ervoor dat de prompt in de folder van de code zit. Dit is de folder waarin de `package.json` file staat en voer volgend commando uit:
```
$ npm install
```
Hiermee worden de dependencies van de applicatie geinstalleerd. Je kan dit bevestigen door te controleren of er nu een `node_modules` folder aanwezig is.

## uitvoeren van de unittesten
in de `package.json` file zal je zien dat er een aantal scripts aanwezig zijn. Deze kunnen we gebruiken om onder andere de unittesten uit te voeren via volgend commando:
```
$ npm test

> calculator-app@1.0.0 test /home/dries/Calculator-app-main
> jest

Browserslist: caniuse-lite is outdated. Please run:
  npx browserslist@latest --update-db
  Why you should do it regularly: https://github.com/browserslist/browserslist#browsers-data-updating
 PASS  tests/calculator.test.js
  Test if frontend server works
    ✓ It should respond with statuscode 200 (14 ms)
  Test the add path
    ✓ It should response the GET method (4 ms)
  Test the add logic
    ✓ It should respond with '7' (2 ms)
  Test the subtract path
    ✓ It should response the GET method (3 ms)
  Test the subtract logic
    ✓ It should respond with '3' (2 ms)

Test Suites: 1 passed, 1 total
Tests:       5 passed, 5 total
Snapshots:   0 total
Time:        0.31 s, estimated 1 s
Ran all test suites.
```

### Code versie les 1
Bij de versie van de eerste les zal één van de unittesten falen. Je dient hier de code in de file `routes.js` aan te passen zodat de `subtract` functie aftrekt in plaats van optelt.

## Uitvoeren van de applicatie
Het opstarten van de applicatie kunnen we doen aan de hand van het script `npm start` dat gedefinieerd staat in de `package.json` file of door het uitvoeren van het commando `node server.js`

### Code versie les 1
In deze versie staat in de output na het uitvoeren van de applicatie dat de app draait op poort `3000`. Dit is incorrect (hij draait standaard op poort `3300`). Je kan de juiste poort configureren in de file `server.js`.

Na deze configuratie kan je naar het ip adres van je server surfen. Hier kan je de calculator applicatie gebruiken.


# Alternatieven
Oplettende studenten hebben mogelijks de `Dockerfile` en `docker-compose.yml` file zien staan in de root van ons project. Je kan de applicatie ook heel eenvoudig opstarten na het installeren van [Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04) & [docker-compose](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04) met het commando:
```
$ docker-compose up -d
```
