# api-doc
Flomta application API documentation

# basic query and authentication
Authentication is obtained via http-header X-API-TOKEN

The authentication token is obtained via the Flomta application admin interface. NB! the authentication token is to be used for back-end server-to-server queries only! 

example query:

```$ curl -s https://api.flomta.eu/building/{buildingId} -H "X-API-TOKEN: my-secret-api-token" ```

Would result a json result similar to :

```
{
  "success": true,
  "data": {
    "id": "{buildingId}",
    "name": "Demo house",
    "short_name": "demo-house"
  }
}
```
# Endpoints

## building/apartments

#### Query

`https://api.flomta.eu/building/apartments/{buildingId}`

#### Result

```
{
  "success": true,
  "data": [
    {
      "id": "WL345RAR",
      "name": "1",
      "size": null
    },
    {
      "id": "dLrbnYL7",
      "name": "2",
      "size": null
    },
    / etc... /
  ]
}
```


## apartment

#### Query

`https://api.flomta.eu/apartment/{apartmentId}`

#### Result

```
{
  "success": true,
  "data": {
    "id": "WL345RAR",
    "building_id": "r6NvOgLQ",
    "name": "1",
    "size": null
  }
}
```

## apartment/meters

#### Query

`https://api.flomta.eu/apartment/meters/{apartmentId}`

#### Result

```
{
  "success": true,
  "data": [
    {
      "id": "ZL2jGYLO",
      "serial": "12345677-1",
      "active": true,
      "isMain": false,
      "isFlipped": false,
      "apartment_id": "WL345RAR",
      "medium-key": "16",
      "medium-name": "Cold water",
      "initial_value": 43.843
    },
    {
      "id": "YLYmKQLm",
      "serial": "12345678-1",
      "active": true,
      "isMain": false,
      "isFlipped": false,
      "apartment_id": "WL345RAR",
      "medium-key": "16",
      "medium-name": "Cold water",
      "initial_value": 7.913
    },
    / etc... /
  ]
}
```
