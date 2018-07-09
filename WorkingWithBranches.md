# Praca z gałęziami

## Tworzenie gałęzi

Podstawowe polecenia tworzące gałąź w lokalnym repozytorium to ```git branch``` lub ```git checkout -b```

```
git branch patch59
git checkout patch59
```

Zamiast tych dwóch poleceń można wywołać:

```
git checkout -b patch59
```

Jeśli gałąź może już istnieć to trzeba ją wyczyścić i przestawić na bieżące miejsce (HEAD)

```
git checkout -B patchBP
# równoważne
git branch -f patchBP
git checkout patchBP

```

## Przełączanie gałęzi

TBD

## Porządkowanie gałęzi lokalnych (usuwanie zbędnych)

Lista gałęzi scalonych z gałęzią główną (master) 
```
git branch --merged master 
```
Lista gałęzi scalonych z HEAD, czyli z głową bieżącej gałęzi
```
git branch --merged 
```

Lista gałęzi **niescalonych** z HEAD (j.w.)
```
git branch --no-merged
```

## Porządkowanie gałęzi zdalnych

Lista gałęzi lokalnych i zdalnych
```
git branch --all
git branch -a
git branch --remote
git branch -r
```