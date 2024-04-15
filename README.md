# Airline Booking Challenge

## Context

An airline operates flights between airports in Europe and the USA. Available routes are provided in `data.ts` and can be flown in _either direction_, for example:

| Route      | Distance |
| ---------- | -------- |
| MAN ↔ FRA | 845km    |
| MAN ↔ JFK | 5320km   |

There are two fare classes available:

|          | Base Fare | Surcharge      |
| -------- | --------- | -------------- |
| Economy  | £50       | £1 per 10km    |
| Business | £100      | £1.50 per 10km |

The base fare is paid once per booking based on the chosen fare class.

A per-flight baggage fee of £25 is charged for each flight _after_ the first flight.

Example trips:

| Routes          | Class    | Distance | Base Fare | Surcharge | Baggage | Total |
| --------------- | -------- | -------- | --------- | --------- | ------- | ----- |
| MAN → FRA       | Economy  | 845      | 50        | 84        | 0       | 134   |
| MAN → JFK → MAN | Economy  | 10640    | 50        | 1064      | 25      | 1139  |
| JFK → MAN → FRA | Business | 6165     | 100       | 616       | 25      | 1049  |

## Task

Write an application that takes a trip through 2 or more airports + a cabin class and outputs the cost of the booking.

Implement the `book()` method and write tests to ensure it can:

1. Calculate the cost of a simple one-way flight (eg MAN → FRA).
2. Calculate the cost of a return flight (eg MAN → JFK → MAN).
3. Calculate the cost of connecting flights (eg JFK → MAN → FRA).
4. Throw a "flight unavailable" error for routes which are not available (eg FRA → JFK)

## Extension

The airline offers a rewards program for frequent flyers. Points are awarded as follows:

|          | Reward points earned                                 |
| -------- | ---------------------------------------------------- |
| Economy  | 500 per flight                                       |
| Business | 1000 per flight < 1000km / 2000 per flight >= 1000km |

Extend the application with the ability to calculate the number of points earned for a booking.
