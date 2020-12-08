# Documenu API Docs
 
## Endpoint
 The endpoint for the API is :


`https://api.documenu.com/v2`

## Authentication

There are two options for Authentication

> In The Header

```
{
  X-API-KEY: YOUR_API_KEY_GOES_HERE
}
```

>Or As an URL Query Parameter
```
https://api.documenu.com/v2/restaurant/4072702673999819?key=YOUR_API_KEY_GOES_HERE
```



## Endpoints



#### GET Restaurant `/restaurant/{restaurant_id}`


Get Single Restaurant

**Parameters:**

| Name          | Description  | Type  | Required  | Example  |
| ------------- |:-------------:|:-------------:|:-------------:| -----:|
| **`restaurant_id`** | Numeric ID of the restaurant to get. | **int** | **`true` **|`317120` |


> Example:
```
https://api.documenu.com/v2/restaurant/4072702673999819
```


***

#### GET Search Restaurants Geo `/restaurants/search/geo`


Search Function using location and search radius. Returns list of restaurants sorted by closest

**Parameters:**

| Name         | Description  | Type  | Required  | Example  | default  |
|:------------- |:-------------:|:-------------:|:-------------:|:-------------:| -----:|
| **`lat`** | Latitude of search area   | **number** | **`false`**|`40.68919  ` |
| **`lon`** | Longitude of search area   | **number** | **`false`**|`-73.992378` |
| **`distance`** | Search Area radius (in miles)   | **`number`** | **`false` **|`5` |
| **`cuisine`** | Cuisine To Search For   | **string** | **`false`**|`italian` | N/A|
| **`top_cuisines`** | Show only Cuisines In Search Area  | **`Boolean`** | **`false` **|`true` | `false`|
| **`size`** | Data Size of Results   | **`number`** | **`false` **|`30` | `25` or `10`|
| **`page`** | Page Through Results  | **`number`** | **`false` **|`2` | `1`|
| **`fullmenu`** | include full menus | **`boolean`** | **`false` **|`317120` | `false` |



> Example:
```
https://api.documenu.com/v2/restaurants/search/geo?lat=40.688072&lon=-73.997385&distance=1&fullmenu
```


***

#### GET Restaurants By State `/restaurants/state/{state_code}`


Search Function Returns Restaurants By State Code

**Parameters:**

| Name         | Description  | Type  | Required  | Example  | Default |
|:------------- |:-------------:|:-------------:|:-------------:|:-------------:| -----:|
| **`state_code`** | State Code To Bring Up. | **`String`** | **`true` **|`NY` |
| **`cuisine`** | Cuisine To Search For   | **`string`** | **`false` **|`italian` | N/A|
| **`top_cuisines`** | Show only Cuisines In Search Area  | **`boolean`** | **`false` **|`true` | `false`|
| **`size`** | Data Size of Results   | **`number`** | **`false` **|`30` | `50` or `10`|
| **`page`** | Page Through Results  | **`number`** | **`false` **|`2` | `1`|
| **`fullmenu`** | include full menus | **`Boolean`** | **`false` **|  | `false` |

> Example:
```
https://api.documenu.com/v2/restaurants/state/NY?fullmenu
```


***
#### GET Restaurants By Zip Code `/restaurants/zip_code/{zip_code}`


Search Function Returns Restaurants By Zip Code

**Parameters:**

| Name          | Description  | Type  | Required  | Example  | Default |
|:------------- |:-------------:|:-------------:|:-------------:|:-------------:| -----:|
| **`zip_code`** | Zip Code To Bring Up. | **`number`** | **`true` **|`90210` |
| **`cuisine`** | Cuisine To Search For   | **`string`** | **`false` **|`italian` | N/A|
| **`top_cuisines`** | Show only Cuisines In Search Area  | **`boolean`** | **`false` **|`true` | `false`|
| **`size`** | Data Size of Results  | **`number`** | **`false` **|`30` | `50` or `10`|
| **`page`** | Page Through Results  | **`number`** | **`false` **|`2` | `1`|
| **`fullmenu`** | include full menus | **`Boolean`** | **`false` **|  | `false` |

> Example:
```
https://api.documenu.com/v2/restaurants/zip_code/11211?size=100&page=2
```


***


#### GET Restaurants In Geo Bounding Box `/restaurants/geobbox`


Search Function using Geobounding Box. Returns list of restaurants inside GeoBounding Box.

**Parameters:**

| Name          | Description  | Type  | Required  | Example  | default  |
| ------------- |:-------------:|:-------------:|:-------------:|:-------------:| -----:|
| **`top_left`** | Top Left coordinates of Bounding Box in `lat,lon`  | **`string`** | **`true` **|`40.7636412,-74.016265` |
| **`bottom_right`** |Bottom Right coordinates of Bounding Box in `lat,lon`  | **`string`** | **`true` **|`40.706929,-73.96682` |
| **`cuisine`** | Cuisine To Search For   | **`string`** | **`false` **|`italian` | N/A|
| **`top_cuisines`** | Show only Cuisines In Search Area  | **`boolean`** | **`false` **|`true` | `false`|
| **`size`** | Data Size of Results  | **`number`** | **`false` **|`30` | `25` or `10`|
| **`page`** | Page Through Results  | **`number`** | **`false` **|`2` | `1`|
| **`fullmenu`** | include full menus | **`number`** | **`false` **|`317120` | `false` |



> Example:

```
https://api.documenu.com/v2/restaurants/geobbox?top_left=40.7636412,-74.016265&bottom_right=40.706929,-73.96682
```


***

#### GET Restaurants Within Walking/Driving Time of Coor `/restaurants/distance`


Search Function using mode of transport and minutes to return list of restaurants in that radius.

**Parameters:**

| Name          | Description  | Type  | Required  | Example  | default  |
| ------------- |:-------------:|:-------------:|:-------------:|:-------------:| -----:|
| **`lat`** | Latitude of start point   | **`number`** | **`true` **|`40.68919 ` |
| **`lon`** | Longitude of start point   | **`number`** | **`true` **|`-73.992378` |
| **`minutes`** | Number of minutes   | **`number`** | **`true` **|`5` |
| **`mode`** | Mode of Transport (walking or driving)  | **`string`** | **`true` **| |
| **`cuisine`** | Cuisine To Search For   | **`string`** | **`false` **|`italian` | N/A|
| **`top_cuisines`** | Show only Cuisines In Search Area  | **`boolean`** | **`false` **|`true` | `false`|
| **`size`** | Data Size of Results  | **`number`** | **`false` **|`30` | `25` or `10`|
| **`page`** | Page Through Results  | **`number`** | **`false` **|`2` | `1`|
| **`fullmenu`** | include full menus | **`number`** | **`false` **|`317120` | `false` |



> Example:
```
https://api.documenu.com/v2/restaurants/istance?lat=40.688072&lon=-73.997385&minutes=5&mode=driving&fullmenu
```

## Cuisines Example Response: 

**URL:**
```https://api.documenu.com/v2/restaurants/zip_code/11211?top_cuisines=true```

```json
{
    "num_results": 93,
    "data": [
        {
            "cuisine": "Sandwiches",
            "matching_docs": 68
        },
        {
            "cuisine": "American",
            "matching_docs": 44
        },
        {
            "cuisine": "Coffee &amp; Tea",
            "matching_docs": 43
        },
        {
            "cuisine": "American (New)",
            "matching_docs": 40
        },
        {
            "cuisine": "Bar Food",
            "matching_docs": 40
        },
        {
            "cuisine": "Italian",
            "matching_docs": 38
        },
        {
            "cuisine": "Mexican",
            "matching_docs": 37
        },
        {
            "cuisine": "Pizza",
            "matching_docs": 33
        },
        {
            "cuisine": "Cocktails",
            "matching_docs": 26
        },
        {
            "cuisine": "Deli Food",
            "matching_docs": 23
        },
        {
            "cuisine": "Japanese",
            "matching_docs": 23
        },
        {
            "cuisine": "Chinese",
            "matching_docs": 22
        },
        {
            "cuisine": "Tapas",
            "matching_docs": 22
        },
        {
            "cuisine": "Vegetarian",
            "matching_docs": 22
        },
        {
            "cuisine": "Bakery &amp; Pastries",
            "matching_docs": 18
        },
        {
            "cuisine": "Latin American",
            "matching_docs": 18
        },
        {
            "cuisine": "Desserts",
            "matching_docs": 16
        },
        {
            "cuisine": "Burgers",
            "matching_docs": 15
        },
        {
            "cuisine": "Local/Organic",
            "matching_docs": 14
        },
        {
            "cuisine": "Sushi",
            "matching_docs": 14
        },
        {
            "cuisine": "Asian Fusion",
            "matching_docs": 13
        },
        {
            "cuisine": "Mediterranean",
            "matching_docs": 13
        },
        {
            "cuisine": "Other",
            "matching_docs": 12
        },
        {
            "cuisine": "Smoothies &amp; Juices",
            "matching_docs": 12
        },
        {
            "cuisine": "French",
            "matching_docs": 11
        },
        {
            "cuisine": "Thai",
            "matching_docs": 11
        },
        {
            "cuisine": "Diner",
            "matching_docs": 10
        },
        {
            "cuisine": "Hot Dogs",
            "matching_docs": 10
        },
        {
            "cuisine": "Puerto Rican",
            "matching_docs": 10
        },
        {
            "cuisine": "Soul Food",
            "matching_docs": 10
        },
        {
            "cuisine": "Alcohol",
            "matching_docs": 9
        },
        {
            "cuisine": "Salads",
            "matching_docs": 9
        },
        {
            "cuisine": "Seafood",
            "matching_docs": 9
        },
        {
            "cuisine": "Bagels",
            "matching_docs": 8
        },
        {
            "cuisine": "Bistro",
            "matching_docs": 8
        },
        {
            "cuisine": "Gastropub",
            "matching_docs": 8
        },
        {
            "cuisine": "Wings",
            "matching_docs": 8
        },
        {
            "cuisine": "Healthy",
            "matching_docs": 6
        },
        {
            "cuisine": "Middle Eastern",
            "matching_docs": 6
        },
        {
            "cuisine": "South American",
            "matching_docs": 6
        },
        {
            "cuisine": "Chicken",
            "matching_docs": 5
        },
        {
            "cuisine": "Korean",
            "matching_docs": 5
        },
        {
            "cuisine": "Noodles",
            "matching_docs": 5
        },
        {
            "cuisine": "Nuevo Latino",
            "matching_docs": 5
        },
        {
            "cuisine": "Spanish",
            "matching_docs": 5
        },
        {
            "cuisine": "Vegan",
            "matching_docs": 5
        },
        {
            "cuisine": "Vietnamese",
            "matching_docs": 5
        },
        {
            "cuisine": "Barbecue",
            "matching_docs": 4
        },
        {
            "cuisine": "Breakfast",
            "matching_docs": 4
        },
        {
            "cuisine": "Crepes",
            "matching_docs": 4
        },
        {
            "cuisine": "Eastern European",
            "matching_docs": 4
        },
        {
            "cuisine": "Eclectic &amp; International",
            "matching_docs": 4
        },
        {
            "cuisine": "Indian",
            "matching_docs": 4
        },
        {
            "cuisine": "Pasta",
            "matching_docs": 4
        },
        {
            "cuisine": "Caribbean",
            "matching_docs": 3
        },
        {
            "cuisine": "Cheesesteaks",
            "matching_docs": 3
        },
        {
            "cuisine": "Dim Sum",
            "matching_docs": 3
        },
        {
            "cuisine": "Kosher",
            "matching_docs": 3
        },
        {
            "cuisine": "Polish",
            "matching_docs": 3
        },
        {
            "cuisine": "Steak",
            "matching_docs": 3
        },
        {
            "cuisine": "Argentinean",
            "matching_docs": 2
        },
        {
            "cuisine": "Asian",
            "matching_docs": 2
        },
        {
            "cuisine": "German",
            "matching_docs": 2
        },
        {
            "cuisine": "Malaysian",
            "matching_docs": 2
        },
        {
            "cuisine": "Peruvian",
            "matching_docs": 2
        },
        {
            "cuisine": "Southwestern",
            "matching_docs": 2
        },
        {
            "cuisine": "Teahouses",
            "matching_docs": 2
        },
        {
            "cuisine": "Venezuelan",
            "matching_docs": 2
        },
        {
            "cuisine": "Wraps",
            "matching_docs": 2
        },
        {
            "cuisine": "Australian",
            "matching_docs": 1
        },
        {
            "cuisine": "Austrian",
            "matching_docs": 1
        },
        {
            "cuisine": "Belgian",
            "matching_docs": 1
        },
        {
            "cuisine": "Brazilian",
            "matching_docs": 1
        },
        {
            "cuisine": "British (Modern)",
            "matching_docs": 1
        },
        {
            "cuisine": "British (Traditional)",
            "matching_docs": 1
        },
        {
            "cuisine": "Cajun &amp; Creole",
            "matching_docs": 1
        },
        {
            "cuisine": "Californian",
            "matching_docs": 1
        },
        {
            "cuisine": "Cuban",
            "matching_docs": 1
        },
        {
            "cuisine": "El Salvadoran",
            "matching_docs": 1
        },
        {
            "cuisine": "Fine Dining",
            "matching_docs": 1
        },
        {
            "cuisine": "Fish &amp; Chips",
            "matching_docs": 1
        },
        {
            "cuisine": "Hawaiian",
            "matching_docs": 1
        },
        {
            "cuisine": "Jamaican",
            "matching_docs": 1
        },
        {
            "cuisine": "Lunch Specials",
            "matching_docs": 1
        },
        {
            "cuisine": "Moroccan",
            "matching_docs": 1
        },
        {
            "cuisine": "Organic",
            "matching_docs": 1
        },
        {
            "cuisine": "Potatoes",
            "matching_docs": 1
        },
        {
            "cuisine": "Pub Food",
            "matching_docs": 1
        },
        {
            "cuisine": "Russian",
            "matching_docs": 1
        },
        {
            "cuisine": "Scandinavian",
            "matching_docs": 1
        },
        {
            "cuisine": "Southern",
            "matching_docs": 1
        },
        {
            "cuisine": "Tex-Mex",
            "matching_docs": 1
        },
        {
            "cuisine": "Turkish",
            "matching_docs": 1
        }
    ],
    "docs_queried": 640
}
```
