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

Aktualizacja zapamiętanej lokalnie listy zdalnych gałęzi w śledzonych zdalnych repozytoriach (prune cache)

```
git fetch -p origin
git fetch --prune origin
```

Angielski opis z dokumentacji ```fetch --prune```

> Before fetching, remove any remote-tracking references that no longer exist on the remote. Tags are not subject to pruning if they are fetched only because of the default tag auto-following or due to a --tags option. However, if tags are fetched due to an explicit refspec (either on the command line or in the remote configuration, for example if the remote was cloned with the --mirror option), then they are also subject to pruning

Lista gałęzi lokalnych i zdalnych
```
git branch --all
git branch -a
git branch --remote
git branch -r
```

Kasowanie gałęzi zdalnej

```
git push origin :pg-branches-v1
git push origin --delete pg-branches-v1
```