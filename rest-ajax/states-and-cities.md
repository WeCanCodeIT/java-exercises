# States and Cities API

## Objectives:
- Students will be able to wire up a rest application and populate pages with ajax queries
- Students will use a restful api to dynamically access content


Begin this project by using the JSON provided as your data source. Analyze this and choose a direction on how you would like to build your API from the ground up. Think about the necessary relationships needed to build this application out. You can certainly add data for more cities and states to your application.

```javascript
{
    "id": 1,
    "name": "Columbus",
    "location": "Central Ohio",
    "population": 860,000
    "State": {
      "id": 1,
      "name": "Ohio"
      }
}
,
{
    "id": 2,
    "name": "Cleveland",
    "location": "Northern Ohio",
    "population": 400,000
    "State": {
      "id": 2,
      "name": "Ohio"
      }
}

```

## Your tasks
- JPA enable the proper 2 entities and wire up your application
- Be able to display the following endpoints to hit on your data:
	- all states
	- a particular state
	- all cities
	- a particular city
	- a city by name
	- all cities with a population over 500,000
- Enable Ajax calls to populate the information on your web pages 
