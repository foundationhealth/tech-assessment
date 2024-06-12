# Flight Booking Challenge

You are being tasked with writing part of a Flight Booking application that can book a trip through 2 or more airports & when combined with a fare class, it calculates the cost of the booking.

You should start by implementing the `book()` method _and writing tests_ to verify it can do the following:

1. Calculate the cost of a simple one-way flight (eg MAN → FRA).

2. Throw a "flight unavailable" error for routes which are not available (eg FRA → JFK)

When you have done the above successfully you may attempt the following additional tasks if you have time:

3. Calculate the cost of a return flight (eg MAN → JFK → MAN).

4. Calculate the cost of connecting flights (eg JFK → MAN → FRA).

## Context

An airline operates flights between airports in Europe and the USA. Available routes are provided in `data.ts` and can be flown in _either direction_, for example:

| Route      | Distance |
| ---------- | -------- |
| MAN ↔ FRA | 845km    |
| MAN ↔ JFK | 5320km   |

There are two fare classes available:

|          | Base Fare | Distance Charge |
| -------- | --------- | --------------- |
| Economy  | $50       | $1 per 10km     |
| Business | $100      | $1.50 per 10km  |

The base fare is paid once per booking based on the chosen fare class.

A per-flight baggage fee of $25 is charged for each flight _after_ the first flight.

Example bookings:

| Routes          | Class    | Distance | Base Fare | Distance Charge | Baggage | Total |
| --------------- | -------- | -------- | --------- | --------------- | ------- | ----- |
| MAN → FRA       | Economy  | 845      | 50        | 84              | 0       | 134   |
| MAN → JFK → MAN | Economy  | 10640    | 50        | 1064            | 25      | 1139  |
| JFK → MAN → FRA | Business | 6165     | 100       | 924             | 25      | 1049  |
