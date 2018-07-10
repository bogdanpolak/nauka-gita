# Poruszanie się po historii Gita

## Historia w Git

Git przechowuje niezależnie wszystkie rewizje (commits) oraz wskaźniki do danej rewizji.

Rewizje są zapamiętywane w następujący sposób:

![Drzewko plików dla jednej rewizji](https://git-scm.com/book/en/v2/images/commit-and-tree.png)

Historia rewizji zapisana zostaje w następujący sposób:

![Historia rewizji](https://git-scm.com/book/en/v2/images/commits-and-parents.png)

Każda rewizja pamięta swojego rodzica, czyli wersję wcześniejszą.

> Źródło: https://git-scm.com/book/pl/v2/Gałęzie-Gita-Czym-jest-gałąź

## Wskaźniki do rewizji

Git ma kilka rodzajów wskaźników do rewizji.

* ```HEAD``` - aktualnie używana rewizja
* **Znacznik (tag)** - nazwany wskaźnik ustawiany na wybraną rewizję, służy do zapamiętania historycznej wersji repozytorium
* **Gałąź (branch)** - pozwala na dodawanie nowych wersji, przesuwa się razem ze zmianami. Możliwe jest scalanie gałęzi
* **master** - domyślnie zakładana gałąź (główna), zachowuje się analogicznie jak każda inna gałąź

![Wskaźniki do historii](https://git-scm.com/book/en/v2/images/branch-and-history.png)

Git podobnie jak każdy system wersjonowania plików pozwala rozgałęziać historię. Realizowane jest to dzięki wykorzystaniu wskaźników:

![Rozgałęziona historia](https://git-scm.com/book/en/v2/images/advance-master.png)

## Detached HEAD

>**TODO:** Przetłumaczyć i opisać

> This is called a detached HEAD. Example commands that will cause your HEAD to become detached (ouch!) are[1]:
```
git checkout master^        # parent of master
git checkout HEAD~2         # grandparent of current HEAD
git checkout origin/master  # a non-local branch
git checkout tagname        # since you cant commit to a tag!
```
