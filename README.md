# Airline Booking Challenge

## Context

An airline operates flights from between airports in Europe and the USA. Available routes are provided in `data.ts` and can be flown in either direction, for example:

| Route     | Distance |
| --------- | -------- |
| MAN ↔ FRA | 845km    |
| MAN ↔ JFK | 5320km   |

There are two fare classes available:

|          | Base Fare | Surcharge     |
| -------- | --------- | ------------- |
| Economy  | £50       | £10 per 100km |
| Business | £100      | £15 per 100km |

The base fare is paid once per booking based on the chosen fare class.

## Task

Write an application that takes an itinerary of 2 or more airports + a cabin class and outputs the cost of the booking.

For example:

```js
book(["FRA", "MAN"], "ECONOMY") -> 50 + (10 * 8) -> 130
book(["MAN", "JFK", "MAN"], "ECONOMY") -> 50 + (10 * 106) -> 1110
book(["JFK", "MAN", "FRA"], "BUSINESS") -> 100 + (15 * 61) -> 1015
```

Implement the `book()` method and write tests to ensure it can:

1. Calculate the cost of a simple one-way flight (eg FRA → MAN).
2. Calculate the cost of a return flight (eg MAN → FRA → MAN).
3. Calculate the cost of connecting flights (JFK → MAN → FRA).
4. Throw a "flight unavailable" error for routes which are not available (FRA → JFK)

## Extension

The airline offers a rewards program for frequent flyers. Points are awarded as follows:

|          | Reward points earned                                 |
| -------- | ---------------------------------------------------- |
| Economy  | 500 per flight                                       |
| Business | 1000 per flight < 1000km / 2000 per flight >= 1000km |

Extend the application with the ability to calculate the number of points earned for a booking.
