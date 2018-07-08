# Modyfikacja historii repozytorium.

Tematy:
* Drobne korekty ostatniej rewizji
* Zmiana bazy
* Interaktywna zmiana bazy (z możliwością zgniatania rewizji)

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

Polecenie rebase pozwala przenosić kilka rewizji z jednej gałęzi do innej bez konieczności scalania.

**Sytuacja:** pracujemy na rozgałęzieniu (dla przykładu nazwanym: eksperyment) i chcemy wstawić zmiany z gałęzi eksperyment do master'a tak jakby były wykonywane ma gałęzi głównej.  
![Stan przed rebase](https://git-scm.com/figures/18333fig0327-tn.png)   

Wykonujemy następujące polecenia:  

```
git checkout experiment
git rebase master
```  

**Stan po rebase:**  
![Stan po rebase](https://git-scm.com/figures/18333fig0329-tn.png) 

## Interaktywna zmiana bazy (git rebase -i)

Interaktywny zmiana bazy (rebase) dodatkowo wzbogaca polecenie zmiany bazy o możliwość skorygowania każdej rewizji, scalenia jej z wcześniejszą lub nawet jej pominięcia w czasie przenoszenia zmian z jednej gałęzi do drugiej. Czyli poza standardowym odtwarzaniem zmian na innej gałęzi interaktywna zmiana bazy pozwala zmieniać historię rewizji.

Interaktywna zmiana bazy pozwala wykonać następujące operacje na każdej z rewizji:

- p pick - użyj rewizji
- r reword - użyj ze zmianą opisu rewizji (komunikatu)
- e edit - użyj rewizji, ale zatrzymaj się na korekty (amend)
- s squash - użyj rewizji ale wciel ją w poprzednią rewizję
- f fixup - jak squash, ale pomiń komunikat loga
- x exec - uruchom polecenie shell'a
- d drop - odrzuć rewizję

## Rebase na zdalnym origin/master oraz hard reset na master

TBD ...

# TODO
1. Do zrobienia:
    - opisanie: ```git push origin master --force```
    - opisanie: rebase i squash
    - przetestowanie i opisanie: ```git reset --hard```
    - opisanie merge
2. Linki do przejrzenia i analizy:
    - [Doc: Zmiana bazy](https://git-scm.com/book/pl/v1/Gałęzie-Gita-Zmiana-bazy)

