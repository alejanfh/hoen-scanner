# Hoen Scanner :shell:
This repo contains everything you need to get started on the Skyscanner backend engineering task

A simple REST microservice built with Dropwizard as part of the Skyscanner Software Engineering Virtual Experience on Forage.

## What it does

The microservice exposes a single `/search` endpoint that accepts POST requests with a city name and returns a list of matching hotels and rental cars available in that city.

## How it works

- `Search` — represents the incoming search request, deserialised from JSON using Jackson
- `SearchResult` — represents a single result (hotel or rental car), serialised back to JSON
- `HoenScannerApplication` — loads `hotels.json` and `rental_cars.json` on startup and combines them into a single list
- `SearchResource` — handles POST requests to `/search`, filters the results by city and returns the matches

## Example request

POST `localhost:8080/search`

\`\`\`json
{"city": "petalborough"}
\`\`\`

## Tech stack

- Java 11
- Dropwizard
- Jackson
- Maven