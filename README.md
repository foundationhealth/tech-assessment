# Airline Booking Challenge

## Context

An airline operates flights from between airports in Europe and the USA. Available routes are provided in `data.ts` and can be flown in either direction, for example:

| Route     | Distance |
| --------- | -------- |
| MAN ↔ FRA | 845km    |
| MAN ↔ JFK | 5320km   |

There are three fare classes available:

|          | Base Fare | Surcharge     | Reward points earned                                 |
| -------- | --------- | ------------- | ---------------------------------------------------- |
| Economy  | £50       | £10 per 100km | 500 per flight                                       |
| Business | £100      | £15 per 100km | 1000 per flight < 1000km / 2000 per flight >= 1000km |
| First    | £250      | £30 per 100km | 5000 per flight                                      |

The base fare is paid once per booking based on the chosen fare class.

First class is only available on long haul flights greater than 1000km. Where a first class booking includes a leg on which first class is unavailable, the business class surcharge is applied to that leg.

## Task

Write an application that takes an itinerary of 2 or more airports + a cabin class and outputs the cost of the booking and the total number of reward points earned.

Example request:

```json
{
  "route": ["LAX", "MAN", "FRA"],
  "fareClass": "FIRST"
}
```

Example response:

```json
{
  "price": "£2940.00",
  "points": 6000
}
```

Some use cases for the application to consider:

1. Simple one-way flights (FRA → MAN).
2. Return flights (SFO → LAX → SFO).
3. Connecting flights (MAN → FRA → SFO).
4. Routes which are not available (FRA → LAX)
