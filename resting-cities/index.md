# Cities and States

Create a full stack webapp with a RESTful API that allows for the display of city and state information. Use an HTML form to create new cities. Use AJAX to display city and state information.

## API requirements

Other parts of the company may need to use this API as well. Let's facilitate collaboration by creating endpoints that do the following:

### List states

As states go, we are interested in their state fish as well as their cities.

The url `/states` in your app should have a response similar to the following:

```json
[
	{
		"abbreviation": "OH",
		"name": "Ohio",
		"motto": "Birthplace of Aviation",
		"fish": null,
		"citiesUrl": "/states/oh/cities"
	},
	{
		"abbreviation": "HI",
		"name": "Hawaii",
		"motto": "The Islands of Aloha",
		"fish": {
			"name": "Humuhumunukunukuāpuaʻa",
			"binomialNomenclature": "Rhinecanthus rectangulus",
			"imgUrl":
				"https://upload.wikimedia.org/wikipedia/commons/5/52/Reef_Triggerfish_1.JPG"
		},
		"citiesUrl": "/states/hi/cities"
	}
]
```

Tip: use `@Embedded`/`@Embeddable` ([example](https://stackoverflow.com/questions/35174981/when-to-use-embedded-and-embeddable)) for the state fish. To start, just use a `String` representing the fish's name.

### Show an individual state

Your API should support retrieving an individual state using a URL of the form `/states/{abbreviation}`. For `/states/hi`, the response should look something like this:

```json
{
	"abbreviation": "HI",
	"name": "Hawaii",
	"motto": "The Islands of Aloha",
	"fish": {
		"name": "Humuhumunukunukuāpuaʻa",
		"binomialNomenclature": "Rhinecanthus rectangulus",
		"imgUrl":
			"https://upload.wikimedia.org/wikipedia/commons/5/52/Reef_Triggerfish_1.JPG"
	},
	"citiesUrl": "/states/hi/cities"
}
```

### Show cities for a state

Your API should support retrieving cities for a specified state using a URL of the form `/states/{abbreviation}/cities`. For `/states/hi/cities`, the response should look something like this:

```json
[
	{
		"name": "Honolulu",
		"population": 337256
	},
	{
		"name": "Waipahu",
		"population": 38216
	},
	{
		"name": "Wailuku",
		"population": 15313
	}
]
```
