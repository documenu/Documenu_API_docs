# Documenu 
 
## Endpoint
 The endpoint for the API is :


`https://api.documenu.xyz/api`

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
https://api.documenu.xyz/api/restaurant/4072702673999819?key=YOUR_API_KEY_GOES_HERE
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
https://api.documenu.xyz/api/restaurant/4072702673999819
```


***

#### GET Search Restaurants Geo `/restaurants/search/geo`


Search Function using location and search radius. Returns list of restaurants sorted by closest

**Parameters:**

| Name         | Description  | Type  | Required  | Example  | default  |
|:------------- |:-------------:|:-------------:|:-------------:|:-------------:| -----:|
| **`lat`** | Latitude of search area   | **number** | **`false` **|`40.68919  ` |
| **`lon`** | Longitude of search area   | **number** | **`false` **|`-73.992378` |
| **`distance`** | Search Area radius (in miles)   | **number** | **`false` **|`5` |
| **`size`** | Data Size of Results   | **number** | **`false` **|`30` | `25` or `10`|
| **`page`** | Page Through Results  | **number** | **`false` **|`2` | `1`|
| **`fullmenu`** | include full menus | **number** | **`false` **|`317120` | `false` |



> Example:
```
https://api.documenu.xyz/api/restaurants/search/geo?lat=40.688072&lon=-73.997385&distance=1&fullmenu
```


***

#### GET Restaurants By State `/restaurants/state/{state_code}`


Search Function Returns Restaurants By State Code

**Parameters:**

| Name         | Description  | Type  | Required  | Example  | Default |
|:------------- |:-------------:|:-------------:|:-------------:|:-------------:| -----:|
| **`state_code`** | State Code To Bring Up. | **String** | **`true` **|`NY` |
| **`size`** | Data Size of Results   | **number** | **`false` **|`30` | `50` or `10`|
| **`page`** | Page Through Results  | **number** | **`false` **|`2` | `1`|
| **`fullmenu`** | include full menus | **Boolean** | **`false` **|  | `false` |

> Example:
```
https://api.documenu.xyz/api/restaurants/state/NY?fullmenu
```


***
#### GET Restaurants By Zip Code `/restaurants/zip_code/{zip_code}`


Search Function Returns Restaurants By Zip Code

**Parameters:**

| Name          | Description  | Type  | Required  | Example  | Default |
|:------------- |:-------------:|:-------------:|:-------------:|:-------------:| -----:|
| **`zip_code`** | Zip Code To Bring Up. | **number** | **`true` **|`90210` |
| **`size`** | Data Size of Results  | **number** | **`false` **|`30` | `50` or `10`|
| **`page`** | Page Through Results  | **number** | **`false` **|`2` | `1`|
| **`fullmenu`** | include full menus | **Boolean** | **`false` **|  | `false` |

> Example:
```
https://api.documenu.xyz/api/restaurants/zip_code/11211?size=100&page=2
```


***


#### GET Restaurants In Geo Bounding Box `/restaurants/geobbox`


Search Function using Geobounding Box. Returns list of restaurants inside GeoBounding Box.

**Parameters:**

| Name          | Description  | Type  | Required  | Example  | default  |
| ------------- |:-------------:|:-------------:|:-------------:|:-------------:| -----:|
| **`top_left`** | Top Left coordinates of Bounding Box in `lat,lon`  | **string** | **`true` **|`40.7636412,-74.016265` |
| **`bottom_right`** |Bottom Right coordinates of Bounding Box in `lat,lon`  | **string** | **`true` **|`40.706929,-73.96682` |
| **`size`** | Data Size of Results  | **number** | **`false` **|`30` | `25` or `10`|
| **`page`** | Page Through Results  | **number** | **`false` **|`2` | `1`|
| **`fullmenu`** | include full menus | **number** | **`false` **|`317120` | `false` |



> Example:

```
https://api.documenu.xyz/api/restaurants/geobbox?top_left=40.7636412,-74.016265&bottom_right=40.706929,-73.96682
```


***

#### GET Restaurants Within Walking/Driving Time of Coor `/restaurants/distance`


Search Function using mode of transport and minutes to return list of restaurants in that radius.

**Parameters:**

| Name          | Description  | Type  | Required  | Example  | default  |
| ------------- |:-------------:|:-------------:|:-------------:|:-------------:| -----:|
| **`lat`** | Latitude of start point   | **number** | **`true` **|`40.68919 ` |
| **`lon`** | Longitude of start point   | **number** | **`true` **|`-73.992378` |
| **`minutes`** | Number of minutes   | **number** | **`true` **|`5` |
| **`mode`** | Mode of Transport (walking or driving)  | **string** | **`true` **|`5` |
| **`size`** | Data Size of Results  | **number** | **`false` **|`30` | `25` or `10`|
| **`page`** | Page Through Results  | **number** | **`false` **|`2` | `1`|
| **`fullmenu`** | include full menus | **number** | **`false` **|`317120` | `false` |



> Example:
```
https://api.documenu.xyz/api/restaurants/istance?lat=40.688072&lon=-73.997385&minutes=5&mode=driving&fullmenu
```

