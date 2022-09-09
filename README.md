# Exercise
​
Implement application for managing flights reservation. Application should also support listing all flights and querying for flights by specific parameters.
​
## Specification
​
Your application should expose three HTTP endpoints:
​
### API Definition:
​
```
/flights
```
​
#### API Response:
​
This API endpoint should return all available flights.
​
### API Definition:
​
```
/search
```
​
### API Input:
​
This API endpoint takes JSON object that represents search request as an input.
​
### API Output:
​
Returns the available flights based on parameters given in search request.
​
### Example:
​
```
{
  "off": "ZAGREB",
  "to": "LONDON",
  "date": "2022-09-20"
}
```
​
```
{
  "flights": [
    {
      "off": "ZAGREB",
      "to": "LONDON",
      "departure": "2022-09-20 10:00:00",
      "arrival": "2022-09-20 12:00:00",
      "available": 8
    },
    {
      "off": "ZAGREB",
      "to": "LONDON",
      "departure": "2022-09-20 14:00:00",
      "arrival": "2022-09-20 16:00:00",
      "available": 33
    }
  ]
}
```
​
### API Definition:
​
```
/reserve/{id}
```
​
### API Input:
​
This API endpoint should take flight id as path parameter and make reservation for given number of seats if one can be made. Reservation can be made if there is enough seats
available for given flight.
​
Request
​
```
{
  "numberOfSeats": 3
}
```
​
### API Output:
​
Returns the status of reservation.
​
### Example:
​
Response
​
```
{
  "status": "SUCCESSFULL"
}
```
​
## Optional
​
Implement support for two-way flight search.
​
### Example
​
```
/search
```
​
```
{
  "off": "ZAGREB",
  "to": "LONDON",
  "date": "2022-09-20",
  "returnDate": "2022-09-22",
  "twoWayFlight": true
}
```
​
```
{
  "flights": [
    [
      {
        "off": "ZAGREB",
        "to": "LONDON",
        "departure": "2022-09-20 10:00:00",
        "arrival": "2022-09-20 12:00:00",
        "available": 8
      },
      {
        "off": "LONDON",
        "to": "ZAGREB",
        "departure": "2022-09-22 14:00:00",
        "arrival": "2022-09-22 16:00:00",
        "available": 12
      }
    ],
    [
      {
        "off": "ZAGREB",
        "to": "LONDON",
        "departure": "2022-09-20 10:00:00",
        "arrival": "2022-09-20 12:00:00",
        "available": 13
      },
      {
        "off": "LONDON",
        "to": "DORTMUND",
        "departure": "2022-09-22 14:00:00",
        "arrival": "2022-09-20 17:00:00",
        "available": 17
      },
      {
        "off": "DORTMUND",
        "to": "ZAGREB",
        "departure": "2022-09-22 19:00:00",
        "arrival": "2022-09-20 20:00:00",
        "available": 27
      }
    ]
  ]
}
```
​
## Additional Information
​
You are free to use any programming language and any framework.
​
You can find "flights.txt" in this repository which contains generated information about existing flights. Use attached file for retrieving information about flights and making
calculations.
​
#### File format
​
```
{COLUMN_NAME} ({COLUMN_CHARACTER_LENGTH})
```
​
```
DEPARTURE_CITY(30)
ARRIVAL_CITY(30)
FLIGHT_DATE(10)
DEPARTURE_TIME(8)
ARRIVAL_TIME(8)
NUMBER_OF_AVAILABLE_SEATS(2)
```
​
### Commiting
​
You will provide your solution by creating a feature branch using your name (i.e. feature/{your name}]) and pushing it to this repository.
