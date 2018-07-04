# GitPro - Notatki z książki

## Rozdział 1 - Pierwsze kroki

Migawki, nie różnice. Większość repozytoriów zapisuje zmiany w postaci różnicowych delt (Git tak nie działa):

![Zapisywanie zmian: delty](https://git-scm.com/book/en/v2/images/deltas.png)

Git zapisuje migawki:

![Zapisywanie zmian: migawki](https://git-scm.com/book/en/v2/images/snapshots.png)

Trzy stany (miejsca) w jakich znajdują się pliki

![Trzy stany](https://git-scm.com/book/en/v2/images/areas.png)

## Rozdział 2 - Podstawy Gita

```
$ git status
git status -s   /   git status --short
```

Stany śledzenia plików w Git:
![stany śledzenia plików](https://git-scm.com/book/en/v2/images/lifecycle.png)

Ignorowanie plików: .gitignore

Repozytorium plików .gitignore dla różnych typów projektów: [https://github.com/github/gitignore]()

```
# ignoruje pliki .a (w folderze głównym i w podfolderach)
*.a

# ale śledzi plik lib.a (wyjątek)
!lib.a

# ignoruje plik TODO tylko w gółnym folderze (nie w podfolderach)
/TODO

# ignore all files in the build/ directory
build/

# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt

# ignore all .txt files in the doc/ directory
doc/**/*.txt
```
Sprawdzenie zawartości poczekalni / zaplecza (staging area)
```
git diff --staged
```

Zatwierdzanie zmian, czyli przenoszenie z poczekalni to repozytorium lokalnego

```
git commit
```

Zatwierdzenie zmian bezpośrednio z katalogu roboczego (z pominięciem poczekalni). Zatwierdzane są wszystkie zmienione i zmodyfikowane pliki, które są śledzone, czyli takie, które pokaże ```git diff``

```
git commit -am 'added new benchmarks'
```

Usuwanie śledzonego pliku. Nie wystarczy standardowo usunąć pliku, który wcześniej został dodany do repozytorium. Tak usunięty plik, zostanie wykazany jako "Zmienione ale nie zaktualizowane". Konieczne jest usuwanie poleceniem:

```
git rm PROJECTS.md
```

Usuwanie śledzenia pliku (usunięcie pliku ze staging area, plik dalej nie będzie już śledzony)

```
git rm --cached MY_LOCAL_TASKS
git rm log/\*.log
```

Zmiana nazwy pliku

```
git mv README.md README
```

```
mv README.md README
git rm README.md
git add README
```

Przeglądanie rewizji repozytorium

```
git log
git log -5
git log -p
git log --stat
git log --pretty=oneline
git log --oneline
git log --pretty=format:"%h %s" --graph
git log --since=2.weeks
```

Drobne poprawki repozytorium

```
git commit --amend
```

Unstage, czyli usuwanie pliku z poczekalni / zaplecza (staging area). Więcej informacji w rozdziale [7.7 Git Tools - Reset Demystified](https://git-scm.com/book/pl/v2/Git-Tools-Reset-Demystified)

```
git reset HEAD CONTRIBUTING.md
git reset HEAD --  CONTRIBUTING.md
```

Usunięcie z poczekalni oraz przywrócenie ostatnio zatwierdzonej wersji pliku:

```
git checkout -- CONTRIBUTING.md
```

Zdalne repozytoria

```
git remote -v
git remote
git remote show origin
git remote add pb https://github.com/paulboone/ticgit
git remote rename pb paulboone
git fetch paulboone
git remote rm paulboone
git push
git push origin master
```

Tagowanie

```
git tag
git tag -l 'v1.*'
git tag v1.4-lw
git tag -a v1.4 -m 'my version 1.4'
git tag -a v1.2 9fceb02
git push origin v1.5
git push origin --tags
git checkout -b version2 v2.0.0
```

## Rozdział 3 - Gałęzie Gita

TBD

## Źródło

[GitPro książka](https://git-scm.com/book/pl/v2)
Tłumaczenie społecznościowe książki: Pro Git Second Edition (2014) - Scott Chacon, Ben Straub
