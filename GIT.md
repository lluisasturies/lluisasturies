# Comandos Git
Lista de comandos básicos para Git.

## Configuración Básica
### Configurar Nombre
Configurar Nombre que salen en los commits
```ssh
	$ git config --global user.name "Lluis de la Rubia"
```
### Configurar Email
Configurar Email
```ssh	
	$ git config --global user.email lluis.asturies93@gmail.com
```
### Colores en los comandos
Marco de colores para los comandos
```ssh
	git config --global color.ui true
```

## Iniciando repositorio
### Iniciar repositorio
Iniciamos GIT en la carpeta donde esta el proyecto
```ssh
	$ git init
```
### Commit 
Hacemos un commit
```ssh
	$ git commit -m "Texto que identifique por que se hizo el commit"
```
### Revertir Commit
El comando git revert deshará el commit que le hemos indicado, pero creará un nuevo commit deshaciendo la anterior
```ssh
	$ git revert <sha1-commit-id>
```
### Volver a otro commit
Cuando queramos volver a un commit anterior y borrar los que hayamos hecho posteriormente a este.
subimos al repositorio
```ssh
	$ git reset --hard <sha1-commit-id>
```
```ssh
	$ git push origin HEAD –force
```

## Ramas
### Crear nueva rama
Creamos una nueva rama y nos colocamos en ella
```ssh
	$ git checkout -b <nombre-de-la-rama>
```
### Borrar una rama
Borramos la rama
```ssh
	$ git branch -d <nombre-de-la-rama>
```

## Pull
### Traer rama actualizada
Este comando se utiliza para recibir actualizaciones del repositorio remoto. Este comando es una combinación del git fetch y del git merge lo cual significa que cundo usemos el git pull recogeremos actualizaciones del repositorio remoto (git fetch) e inmediatamente aplicamos estos últimos cambios en local (git merge).
```ssh
	$ git pull <nombre-remoto>
```

## Merge
Cuando ya hayas completado el desarrollo de tu proyecto en tu rama y todo funcione correctamente, el último paso es fusionar la rama con su rama padre (dev o master). 
### Fusionar con otra rama
**AVISO:**
Asegúrate de que tu rama dev tiene la última versión antes de fusionar otras ramas, si no, te enfrentarás a conflictos u otros problemas no deseados.

Por ejemplo, cuando quieres fusionar tu rama de características en la rama dev.
```ssh
	$ git checkout dev
```
Antes de fusionar, debes actualizar tu rama dev local.
```ssh
	$ git fetch
```
Por último, puedes fusionar tu rama de características en la rama dev.
```ssh
	$ git merge <nombre-de-la-rama>
```