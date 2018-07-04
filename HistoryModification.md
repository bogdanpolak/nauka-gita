# Modyfikacja historii repozytorium.

Tematy:
* Scalanie
* Drobne korekty
* Zmiana bazy
* Sklejanie (zgniatanie) commit'ów

## Informacja wprowadzająca

W czasie tych testów chciałbym sprawdzić jak można modyfikować historię w repozytorium. Do przećwiczenia mam następujące kroki:

## Drobne poprawki (amend)

- amend = poprawka
- korekta powinna być zrobiona tylko na lokalnym repozytorium
- w przeciwnym wypadku konieczne będzie ręczne scalenie zmian (merge), które i tak trzeba będzie zakończyć pełnym commit'em
- commit amend tworzy nową rewizję (nowa suma kontrolna rewizji i scala obie rewizje w jedną)
- polecenie amend może zostać użyte do zmiany opisu
- korekta bez zmiany opisu rewizji, opcja: --no-edit  
    **```git commit --amend --no-edit```** 

## Zmiana bazy (git rebase)

Polecenie rebase pozwala zmieniać historię kilku rewizji oraz przenosić zmiany między rozgałęzieniami.

Możliwe operacje w przypadku interaktywnego rebase (dla każdej rewizji): 
- p pick - użyj rewizji
- r reword - użyj ze zmianą opisu rewizji (komunikatu)
- e edit - użyj rewizji, ale zatrzymaj się na korekty (amend)
- s squash - użyj rewizji ale wciel ją w poprzednią rewizję
- f fixup - jak squash, ale pomiń komunikat loga
- x exec - uruchom polecenie shell'a
- d drop - odrzuć rewizję

## Zmiana bazy dla rozgałęzienia

Jest to standardowe zastosowanie rebase
- Sytuacja: pracujemy na rozgałęzieniu (dla przykładu nazwanym: eksperyment) i chcemy wstawić zmiany z gałęzi eksperyment do master'a tak jakby były wykonywane ma gałęzi głównej.  
![Stan przed rebase](https://git-scm.com/figures/18333fig0327-tn.png)   
Wykonujemy następujące polecenia:  
```
git checkout experiment
git rebase master
```  
- Stan po rebase:  
![Stan po rebase](https://git-scm.com/figures/18333fig0329-tn.png) 

## Rebase na zdalnym origin/master oraz hast reset na master

TBD ...

# TODO
1. Do zrobienia:
    - opisanie: ```git push origin master --force```
    - opisanie: rebase i squash
    - przetestowanie i opisanie: ```git reset --hard```
    - opisanie merge
2. Linki do przejrzenia i analizy:
    - [Doc: Zmiana bazy](https://git-scm.com/book/pl/v1/Gałęzie-Gita-Zmiana-bazy)
    - [Blog: Always Squash and Rebase your Git Commits](https://blog.carbonfive.com/2017/08/28/always-squash-and-rebase-your-git-commits/)
    - [Stack: git log shows (origin) without any branch](https://stackoverflow.com/questions/42445001/git-log-shows-origin-without-any-branch)

