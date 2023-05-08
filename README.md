# random-card-game-logic

Card game logic for a Warhammer game

## How to use

Modify the JSON object in the `index.html` file and add it to the query params of the URL. 

Example:

Go to the local file on your local file system: `../Documents/GitHub/random-card-game-logic/index.html`

Modify the JSON in the `template.json` file to get something you like and then copy and paste that into the url: `../Documents/GitHub/random-card-game-logic/index.html?params={"cards": [{"name": "Aggressive Melee","details": ["Attack (If base contact)","Move towards nearest enemy"]},{"name": "Aggressive Charge","details": ["Attack (If base contact)","Move towards nearest enemy","Charge (If turn 1)"]},{"name": "Aggressive Shoot","details": ["Shoot at nearest (If in range)","Move towards nearest enemy"]},{"name": "Aggressive Aim","details": ["Shoot at nearest (If in range)","Move towards nearest enemy","Aim and Shoot at nearest (If turn 1 and can aim)"]},{"name": "High Ground","details": ["Move toward higher ground"]},{"name": "Higher Ground","details": ["Move toward higher ground","Shoot at nearest (if turn 2)"]},{"name": "Cover Melee","details": ["Attack (If base contact)","Move toward nearest cover"]},{"name": "Cover Shoot","details": ["Shoot at nearest (If in range)","Move toward nearest cover (Except in cover)","Aim and Shoot at nearest (if turn 1 and can aim)"]},{"name": "Retreat Full","details": ["Retreat (If base contact)"]},{"name": "Retreat Studied","details": ["Attack (If base contact)","Retreat (If base contact)","(and weaker the combined woudns of characters in base contact)"]}],"deckBuildingDetails": {"cards": {"Aggressive Melee": {"percent_in_deck": 0.25,"color": "rgb(140, 167, 255)"},"Aggressive Charge": {"percent_in_deck": 0.15,"color": "rgb(140, 167, 35)"},"Aggressive Shoot": {"percent_in_deck": 0.15,"color": "rgb(100, 167, 35)"},"Aggressive Aim": {"percent_in_deck": 0.15,"color": "rgb(100, 167, 35)"},"High Ground": {"percent_in_deck": 0.05,"color": "rgb(100, 100, 35)"},"Higher Ground": {"percent_in_deck": 0.05,"color": "rgb(100, 100, 100)"},"Cover Melee": {"percent_in_deck": 0.05,"color": "rgb(150, 100, 100)"},"Cover Shoot": {"percent_in_deck": 0.05,"color": "rgb(150, 150, 100)"},"Retreat Full": {"percent_in_deck": 0.05,"color": "rgb(150, 25, 100)"},"Retreat Studied": {"percent_in_deck": 0.05,"color": "rgb(100, 150, 25)"}},"total_cards_in_deck": 40}}`


You'll then have a shuffled deck based on the parameters sent in the `params` query param in the url.


## Dev Details

### Adding a card
To add a new card to the mix, simply add to two areas. 

```
"cards": [
        {
            "name": "New Card Name",
            "details": [
                "I am a new card",
                "I do stuff"
            ]
        },
        ...
]
```

and 

```
"deckBuildingDetails": {
        "cards": {
            "New Card Name": {
                "percent_in_deck": 0.25,
                "color": "rgb(140, 167, 255)"
            },
        }
}
```

the "name" of the two places have to match - aka "New Card Name" in both. 

### Do's and Dont's of adding a new card. 

Only stick with A-Z and 0-9 chars for the template. Other characters are reserved words in the url - like `&` and `?` and much much more. If you add a char like this the url will get angry and the game will break.

