# Moje notatki do Git'a

Notatki mają mi pomóc w utrwaleniu kluczowych informacji na temat systemu Git.

# Materiały

* [Praca z gałęziami](./WorkingWithBranches.md)
* [Poruszanie się po historii](./MovingAroundHistory.md)
* [Modyfikacja historii repozytorium](./HistoryModification.md)

# Notatki

* [Notatki z GitPro](./GitProNotes.md)
* [Notatki podręczne / wycinki](./QuickNotes.md)
* [Artykuły i wpisy na blogach](./ArticlesAndBlogs.md)

# Narzędzia pomocnicze

Do przeglądania historii rewizji służy polecenie log

1. Użycie git log:
    * **```git log --pretty=oneline```** - przeglądanie historii spakowanej (jedna rewizja w jednej linii)
    * **```git log --pretty=format:"%h %s"```** - przeglądnie spakowane z formatowaniem,  [więcej informacji...](https://git-scm.com/book/pl/v1/Podstawy-Gita-Podgląd-historii-rewizji/)
    * **```git log --stat```** - szczegółowe statystyki z informacja o liczbie zmian w plikach
