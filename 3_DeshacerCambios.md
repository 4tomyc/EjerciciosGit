# Ejercicios de deshacer cambios

Para hacer estos ejercicios es necesario haber hecho antes los ejercicios sobre historial de cambios

## Ejercicio 1

1. Eliminar la última línea del fichero **indice.txt** y guardarlo.
2. Comprobar el estado del repositorio.
3. Deshacer los cambios realizados en el fichero **indice.txt** para volver a la versión anterior del fichero.
4. Volver a comprobar el estado del repositorio.

~~~git
tomas@tomas-VirtualBox:~/Git/capitulos$ vim indice.txt
tomas@tomas-VirtualBox:~/Git/libro$ git status
En la rama master
Cambios no rastreados para el commit:
  (usa "git add <archivo>..." para actualizar lo que será confirmado)
  (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
	modificado:     indice.txt

sin cambios agregados al commit (usa "git add" y/o "git commit -a")
tomas@tomas-VirtualBox:~/Git/libro$ 
tomas@tomas-VirtualBox:~/Git/libro$ git restore indice.txt
tomas@tomas-VirtualBox:~/Git/libro$ git status
En la rama master
nada para hacer commit, el árbol de trabajo está limpio
~~~

## Ejercicio 2

1. Eliminar la última línea del fichero **indice.txt** y guardarlo.
2. Añadir los cambios a la zona de intercambio temporal.
3. Comprobar de nuevo el estado del repositorio.
4. Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.
5. Comprobar de nuevo el estado del repositorio.
6. Deshacer los cambios realizados en el fichero **indice.txt** para volver a la versión anterior del fichero.
7. Volver a comprobar el estado del repositorio.

~~~git
tomas@tomas-VirtualBox:~/Git/libro$ vim indice.txt
tomas@tomas-VirtualBox:~/Git/libro$ git add indice.txt
tomas@tomas-VirtualBox:~/Git/libro$ git status
En la rama master
Cambios a ser confirmados:
  (usa "git restore --staged <archivo>..." para sacar del área de stage)
	modificado:     indice.txt
tomas@tomas-VirtualBox:~/Git/libro$ git reset .
Cambios fuera del área de stage tras el reset:
M	indice.txt
tomas@tomas-VirtualBox:~/Git/libro$ git status
En la rama master
Cambios no rastreados para el commit:
  (usa "git add <archivo>..." para actualizar lo que será confirmado)
  (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
	modificado:     indice.txt

sin cambios agregados al commit (usa "git add" y/o "git commit -a")
tomas@tomas-VirtualBox:~/Git/libro$ git checkout -- indice.txt
tomas@tomas-VirtualBox:~/Git/libro$ git status
~~~

## Ejercicio 3

1. Eliminar la última línea del fichero **indice.txt** y guardarlo.
2. Eliminar el fichero **capitulos/capitulo3.txt**.
3. Añadir un fichero nuevo **capitulos/capitulo4.txt** vacío.
4. Añadir los cambios a la zona de intercambio temporal.
5. Comprobar de nuevo el estado del repositorio.
6. Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.
7. Comprobar de nuevo el estado del repositorio.
8. Deshacer los cambios realizados para volver a la versión del repositorio.
9. Volver a comprobar el estado del repositorio.

~~~git
vim indice.txt
tomas@tomas-VirtualBox:~/Git/libro$ rm capitulos/capitulo3.txt
tomas@tomas-VirtualBox:~/Git/libro$ touch capitulos/capitulo4.txt
tomas@tomas-VirtualBox:~/Git/libro$ git status
En la rama master
Cambios a ser confirmados:
  (usa "git restore --staged <archivo>..." para sacar del área de stage)
	borrado:        capitulos/capitulo3.txt
	nuevo archivo:  capitulos/capitulo4.txt

tomas@tomas-VirtualBox:~/Git/libro$ git reset .
Cambios fuera del área de stage tras el reset:
D	capitulos/capitulo3.txt
tomas@tomas-VirtualBox:~/Git/libro$ git status
tomas@tomas-VirtualBox:~/Git/libro$ git checkout -- .
tomas@tomas-VirtualBox:~/Git/libro$ git status
En la rama master
Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que se será confirmado)
	capitulos/capitulo4.txt

no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)
tomas@tomas-VirtualBox:~/Git/libro$ git clean -f
tomas@tomas-VirtualBox:~/Git/libro$ git status
~~~

## Ejercicio 4

1. Eliminar la última línea del fichero **indice.txt** y guardarlo. 
2. Eliminar el fichero **capitulos/capitulo3.txt**.
3. Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Borrado accidental.” 
4. Comprobar el historial del repositorio. 
5. Deshacer el último commit pero mantener los cambios anteriores en el directorio de trabajo y la zona de intercambio temporal. 
6. Comprobar el historial y el estado del repositorio. 
7. Volver a hacer el commit con el mismo mensaje de antes. 
8. Deshacer el último commit y los cambios anteriores del directorio de trabajo volviendo a la versión anterior del repositorio.
9. Comprobar de nuevo el historial y el estado del repositorio.

~~~git
tomas@tomas-VirtualBox:~/Git/libro$ vim indice.txt
tomas@tomas-VirtualBox:~/Git/libro$ rm capitulos/capitulo3.txt
tomas@tomas-VirtualBox:~/Git/libro$ git add .
tomas@tomas-VirtualBox:~/Git/libro$ git commit -m "Borrado accidental"
[master 3ec23e9] Borrado accidental
 1 file changed, 1 deletion(-)
 delete mode 100644 capitulos/capitulo3.txt
tomas@tomas-VirtualBox:~/Git/libro$ git status
En la rama master
nada para hacer commit, el árbol de trabajo está limpio
tomas@tomas-VirtualBox:~/Git/libro$ git reset --soft HEAD~1
tomas@tomas-VirtualBox:~/Git/libro$ git status
En la rama master
Cambios a ser confirmados:
  (usa "git restore --staged <archivo>..." para sacar del área de stage)
	borrado:        capitulos/capitulo3.txt
tomas@tomas-VirtualBox:~/Git/libro$ git commit -m "Borrado accidental"
[master f8d0c74] Borrado accidental
 1 file changed, 1 deletion(-)
 delete mode 100644 capitulos/capitulo3.txt
tomas@tomas-VirtualBox:~/Git/libro$ git reset --hard HEAD~1
tomas@tomas-VirtualBox:~/Git/libro$ git status
En la rama master
nada para hacer commit, el árbol de trabajo está limpio
~~~
