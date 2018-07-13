# Praca z etykietami (tags)

## Przesuwanie etykiet

1. Usunięcie etykiety ze zdalnego repozytorium (zdalnych repozytoriów)
2. Dodanie etykiety do aktualnej rewizji (wskazywane przez ```HEAD```). Użyte opcje: ```-a``` / ```--annotate``` = etykieta opisana (obiekt w repozytorium zawierający dodatkowe informacje), ```-f``` / ```--force``` = zamień istniejącą flagę
3. Wypchnij etykiety do zdalnego repozytorium

```
git push origin :refs/tags/<tagname>
git tag -fa <tagname>
git push origin master --tags
```