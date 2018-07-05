# QUICK NOTES

## Overwrite local master revision history

```
git fetch
git checkout path/to/file
```

```
git reset HEAD --hard
git clean -f
git pull origin master
```

Overwite one file

```
git fetch
git checkout origin/master <filepath>
```

Overwrite all changes

```
git fetch
git reset --hard origin/master
```

New branch based on the origin

```
git checkout origin/master -b <new branch name>
```

## Git workflow diagram

![img](http://images.osteele.com/2008/git-transport.png)
