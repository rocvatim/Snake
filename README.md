# Pygame Snake 

## Setup 

Om dit python script te runnen is de volgende library nodig:

1. `Pygame`

## De code ##

Ik heb de game onderverdeeld in 3 classes:

1. `Square`
2. `Grid`
3. `Snake`

Ik heb er voor gekozen om de appel geen aparte klas te geven omdat deze uiteindelijk gewoon een Square is met een andere kleur.

### Square ###
Een `Square` kan gebruikt worden voor de volgende dingen: 

1. Als achtergrond (een grijze square)
2. Als onderdeel van de Snake (een groene square)
3. Als appel (een rode square)

De `Square` class heeft de functie `draw_it` deze krijgt een locatie mee (x, y) een kleur (color) en een width die ook gebruikt wordt om de hoogte van een square te bepalen.


### Grid ###
De `Grid` class maakt gebruik van squares om een speelveld te bouwen. als je bijvoorbeeld een size van 5 meegeeft krijg je een speelveld van 5**2 dus 25 squares.

De `Grid` class heeft `draw_grid` functie die iedere square de kleur meegeeft en dan de `draw_it` functie van de `Square` class aanroept.


### Snake ###
De `Snake` class maakt ook gebruik van de `Square` class om een plek op het speelveld te krijgen. Een `Snake` heeft een kleur en een lengte. iedere `Square` waar de snake uit bestaat wordt opgeslagen in een array.

De `Snake` class maakt gebruik van een `draw_it` functie die voor iedere `Square` in de array de `draw_it` van de `Square` class aanroept.

De `Snake` class maakt gebruik van een `move_it` functie die de locatie van de `Snake` veranderd door gebruik de maken van de globale variabelen `x_speed` en `y_speed` deze functie zorgt er ook voor dat de `Snake` niet in de tegenovergestelde richting kan bewegen. Want dit zou ervoor zorgen dat de `Snake` zichzelf opeet.

De `Snake` class maakt gebruik van een `check_food` functie om te controleren of de `Snake` zich op dezelfde locatie bevindt als een appel.

de `Snake` class maakt gebruik van een `check_die` functie om te controleren of de `Snake` zich op dezelfde locatie bevindt als een van de squares van de `Snake`. Als dit wel het geval is wordt de score en de snake gereset.

### Andere functies ###

De `Movement` functie controleert of er arrow keys worden ingedrukt en past de `x_speed` en `y_speed` variabelen aan gebaseerd op de richting.

De `apple_xy` wordt gebruikt om op een willekeurige locatie op het spelveld een appel te plaatsen.

De `check_event` controleert of de input van de speler een `KEYDOWN` is of een `QUIT`

## Problemen waar ik tegen aan liep ##

Het lukte mij eerst niet om de game af te sluiten door op het kruisje te drukken. Het probleem was dat als een speler al een `KEY` had ingedrukt de event niet meer kon veranderen naar `QUIT`.  Dit heb ik opgelost door de `check_event` functie te maken. Deze controleert eerst of de event niet `QUIT` is voordat het de `movement` functie aanroept.

## Waarom ik voor pygame heb gekozen ##

Ik heb gekozen voor pygame omdat ik in het verleden al een space invader game heb geprogrammeerd met behulp van pygame.
Het is erg makkelijk in gebruik en heeft heel veel functionaliteiten al ingebouwd daarom leek het mij de juiste keuze voor deze opdracht.
