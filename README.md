= Testy repozytorium

W czasie tych testów chciałbym sprawdzić jak można modyfikować historię w repozytorium. Do przećwiczenia mam następujące kroki:

1. Użycie commit --amend
    - amend = poprawka
    - nie można modyfikować commit'a, który już trafił do zdalnego repozytorium
    - korekta może być zrobiona tylko na lokalnym repozytorium
    - w przeciwnym wypadku konieczne będzie ręczne scalenie zmian (merge), które i tak trzeba będzie zakończyć pełnym commit'em
    - commit amend tworzy nową rewizję (nowa suma kontrolna rewizji i scala obie rewizje w jedną)
    - może zostać użyty do zmiany opisu
    - **```git commit --amend --no-edit```** - korekta bez zmiany opisu rewizji (--no-edit)
2. Użycie git rebase
    - Zmiana kilku rewizji
    - Możliwości (dla każdej rewizji wchodzącej w skład operacji rebase: 
        - p pick - użyj rewizji
        - r reword - użyj ze zmianą opisu rewizji (komunikatu)
        - e edit - użyj rewizji, ale zatrzymaj się na korekty (ammend)
        - s squash - użyj rewizji ale wciel ją w poprzednią rewizję
        - f fixup - jak squash, ale pomiń komunikat loga
        - x exec - uruchom polecenie shell'a
        - d drop - odrzuć rewizję
3. Rebase - zmiana bazy dla rozgałęzienia
    - Standardowe zastosowanie rebase
    - Sytuacja: pracujęmy na rozgałęzieniu (dla przykładu nazwanym: eksperyment) i chcemy wstawić zmiany z gałęzi eksperyment do master'a tak jakby były wykonywane ma gałęzi głównej.
    ![Stan przed reabase](https://git-scm.com/figures/18333fig0327-tn.png) 
    - Wykonujemy następujace polecenia:
        ```sh
git checkout experiment
$ git rebase master
        ```
    ![Stan po reabase](https://git-scm.com/figures/18333fig0329-tn.png) 
3. Rebase na zdalnym origin/master oraz hast reset na master

= Narzędzia pomocnicze

Do przeglądania historii rewizji służy polecenie log

1. Użycie git log:
    * **```git log --pretty=oneline```** - przeglądanie historii spakowanej (jedna rewizja w jednej linii)
    * **```git log --pretty=format:"%h %s"```** - przeglądnie spakowane z formatowaniem,  [więcej informacji...](https://git-scm.com/book/pl/v1/Podstawy-Gita-Podgląd-historii-rewizji/)
    * **```git log --stat```** - szczegółowe statystyki z informacja o liczbie zmian w plikach
