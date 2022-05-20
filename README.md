# Pokemon Tracker Exercise
---

## Purpose

> This exercise provides a complete Angular application for the tracking of Pokemon Trainers and their pokemon. Those attempting the exercise will need to create a RESTful API to service the requests made by the Angular client and persist information. 

## General Client Expectations

> The Angular client application has the following general expectations about how the backend API will function and where it will be available. 

* The client expects a RESTful api that returns JSON. 
* The client expects the API to be hosted at localhost:8083 with no context path.
* The client expects to be able to access the PokeAPI from wherever it is hosted. 
* The client expects the follow JSON models: 
  <details>
  <summary> Pokemon: </summary>

  ```
  {
    "pokedexId": 95,
    "name": "onix",
    "baseXP": 88,
    "trainer":{
        "tId": 5,
        "name": "Brock",
        "party": []
      }
  }
  ```
  </details>
  <details>
  <summary>Trainer: </summary>

  ```
  {
    "tId": 4,
    "name": "Misty",
    "party": [
      {
        "pokeId": 4,
        "pokedexId": 121,
        "name": "starmie",
        "baseXP": 182
      }
    ]
  }
  ```
  </details>


## Required Endpoints

> The required endpoints to handle the Client request and their expected returns are as follows:

### **/pokemon:** GET, POST, PUT

`GET` - Returns a JSON array of all Trainers in the database with their pokemon. 

Example Request Body: none. 
<details>
<summary>Example Response Body: </summary>

```
[
    {
        "tId": 3,
        "name": "Ash",
        "party": [
            {
                "pokeId": 2,
                "pokedexId": 25,
                "name": "pikachu",
                "baseXP": 112
            },
            {
                "pokeId": 3,
                "pokedexId": 6,
                "name": "charizard",
                "baseXP": 267
            }
        ]
    },
    {
        "tId": 4,
        "name": "Misty",
        "party": [
            {
                "pokeId": 4,
                "pokedexId": 121,
                "name": "starmie",
                "baseXP": 182
            }
        ]
    },
    {
        "tId": 5,
        "name": "Brock",
        "party": []
    }
]
```
</details>  
<br>

`POST` - Adds a new trainer to the application and returns the updated array of all trainers. 

<details>
<summary>Example Request Body:</summary>

```
{
  "name": "Brock",
  "party": []
}
```
</details>

<details>
<summary>Example Response Body: </summary>

```
[
    {
        "tId": 3,
        "name": "Ash",
        "party": [
            {
                "pokeId": 2,
                "pokedexId": 25,
                "name": "pikachu",
                "baseXP": 112
            },
            {
                "pokeId": 3,
                "pokedexId": 6,
                "name": "charizard",
                "baseXP": 267
            }
        ]
    },
    {
        "tId": 4,
        "name": "Misty",
        "party": [
            {
                "pokeId": 4,
                "pokedexId": 121,
                "name": "starmie",
                "baseXP": 182
            }
        ]
    },
    {
        "tId": 5,
        "name": "Brock",
        "party": []
    }
]
```
</details>
<br>
 
`PUT` - Accepts a new pokemon object to be added to a trainer's team. Returns the updated array of all trainers. 

<details>
<summary>Example Request Body:</summary>

```
{
  "pokedexId": 95,
  "name": "onix",
  "baseXP": 88,
  "trainer":{
      "tId": 5,
      "name": "Brock",
      "party": []
    }
}
```
</details>

<details>
<summary>Example Response Body: </summary>

```
[
    {
        "tId": 3,
        "name": "Ash",
        "party": [
            {
                "pokeId": 2,
                "pokedexId": 25,
                "name": "pikachu",
                "baseXP": 112
            },
            {
                "pokeId": 3,
                "pokedexId": 6,
                "name": "charizard",
                "baseXP": 267
            }
        ]
    },
    {
        "tId": 4,
        "name": "Misty",
        "party": [
            {
                "pokeId": 4,
                "pokedexId": 121,
                "name": "starmie",
                "baseXP": 182
            }
        ]
    },
    {
        "tId": 5,
        "name": "Brock",
        "party": [
            {
                "pokeId": 5,
                "pokedexId": 95,
                "name": "onix",
                "baseXP": 88
            }
        ]
    }
]
```
</details>  
<br>

### **/pokemon/{id}:** GET

`GET` - Returns a single Trainer object based on the id provided.

Example Request Body: none. 

<details>
<summary>Example Response Body: </summary> 

```
{
    "tId": 3,
    "name": "Ash",
    "party": [
        {
            "pokeId": 2,
            "pokedexId": 25,
            "name": "pikachu",
            "baseXP": 112
        },
        {
            "pokeId": 3,
            "pokedexId": 6,
            "name": "charizard",
            "baseXP": 267
        }
    ]
}
```
</details>