# Dog Breed Fetcher (Java), Second Iteration

This is a CSC207 (Software Design, University of Toronto) mini assignment. This repository is a second iteration of the same Dog Breed Fetcher assignment.

## What it does

The program looks up the sub-breeds of a dog breed using the [Dog CEO API](https://dog.ceo/dog-api/):

- `DogApiBreedFetcher` calls the breed list endpoint with OkHttp and parses the JSON response with org.json. Failed or unknown lookups raise `BreedNotFoundException`.
- `CachingBreedFetcher` wraps any `BreedFetcher`, stores successful results in a `HashMap`, and counts calls to the underlying fetcher. Failed lookups are not cached.
- `Main.getNumberOfSubBreeds` returns the number of sub-breeds for a breed, or 0 if there are none.

## Key concepts

- Calling a REST API with OkHttp and parsing JSON with org.json
- Caching with a wrapper class
- Checked exceptions (`BreedNotFoundException` was changed from unchecked to checked)
- Keeping an interface and its implementations in sync
- Writing JUnit 5 tests

## Status

Work in progress. The project does not compile yet: the `BreedFetcher` interface declares `fetchSubBreeds`, which no class implements yet, and some method signatures do not yet match the checked-exception change.

## Running the tests

From the project root (JDK 11 or newer, with Maven):

    mvn test

---

Course starter code provided by the CSC207 teaching team; implementation by Aaryan Patel.
