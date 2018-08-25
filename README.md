## Git Cheatsheet

### Commits 

---

```bash
git commit --amend -m "Mensaje01"  ==> Añade un commit al commit con mensaje Mensaje01

git checkout -- fichero ==> Elimina los cambios realizados en ése fichero

git checkout hash -- fichero ==> Recupera el fichero a la versión del commit identificado por el hash

git revert hash ==> Revertir un commit identificado por el hash

git reset HEAD fichero ==> Saca del commit el fichero

git reset --mixed hash ==> Deja los cambios en el area de trabajo  

cat .git/refs/heads/master ==> para vel el commit al que se está apuntando actualmente
```

### Clean 	

---

```bash
git clean -n ==> nos muestra los archivos que hay en area de trabajo pero no en el staged, por lo que deberían removerse

git clean -f ==> elimina todos los archivos no subidos al stage o al repositori
```

### ls-tree

---

```bash
git ls-tree master ==> ver contenido actual de la carpeta del repositorio

git ls-tree master^ ==> ver contenido de la versión anterior de la carpeta del repositorio

git ls-tree master~3 ==> ver contenido de hace tres versiones de la carpeta del directorio
```

### Logs 

---

```bash
git log --oneline ==> 1 commit por linea

git log --since=3.days ==> logs desde hace tres días/semanas..

git log --stat --summary ==> estadísticas y totales

git log --graph ==> versión 'gráfica'

git log --oneline --graph --all --decorate ==> vista compacta
```

### Branchs 

---

```bash
git diff --color-words branch1..branch2 ==> ver diferencias entre dos ramas

git branch --merged ==> ver qué ramas están incluidas por completo en nuestra rama actual

git branch -m nombreviejo nombrenuevo ==> cambiar el nombre de la rama

git branch -d branch ==> eliminado de rama
	no se puede eliminar una rama con cambios no integrados

git branch -D branch ==> fuerza el eliminado aunque haya cambios no integrados

git merge --abort ==> deshacer un intento de merge con conflictos
```

### Stash 

---

```bash
git stash save 'nombre para el stash' ==> se hace stash asignando un nombre
	los cambios en stash pueden volcarse en otras ramas, no solo en la actual

git stash apply ==> igual que git stash pop, pero sin eliminarlo del area de stash

git stash drop id ==> elimina un stash concreto

git stash clear ==> elimina todos los cambios del area de stash

git branch branch-local branch-remoto ==> branch local apuntando al remoto

git push origin --delete branch-remoto ==> elimina branch remoto
```