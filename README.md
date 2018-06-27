# Testy repozytorium

W czasie tych testów chciałbym sprawdzić jak można modyfikować historię w repozytorium. Do przećwiczenia mam następujące kroki:

1. Użycie commit --amend
    - amend = poprawka
    - nie można modyfikować commit'a, który już trafił do zdalnego repozytorium
    - korekta może być zrobiona tylko na lokalnym repozytorium
    - w przeciwnym wypadku konieczne będzie ręczne scalenie zmian (merge), które i tak trzeba będzie zakończyć pełnym commit'em
    - commit amend tworzy nową rewizję (nowa suma kontrolna rewizji i scala obie rewizje w jedną)
    - może zostać użyty do zmiany opisu
