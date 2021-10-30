tomas@tomas-VirtualBox:~/Git$ git log
tomas@tomas-VirtualBox:~/Git$ mkdir capitulos
tomas@tomas-VirtualBox:~/Git$ vim capitulo1.txt
Git es un sistema de control de versiones ideado por Linus Torvalds.
tomas@tomas-VirtualBox:~/Git$ git add capitulo1.txt
tomas@tomas-VirtualBox:~/Git$ git commit -m "Añadido capitulo 1"
[master (commit-raíz) 48ec3fb] Añadido capitulo 1
 1 file changed, 1 insertion(+)
 create mode 100644 Git/capitulo1.txt
 tomas@tomas-VirtualBox:~/Git$ git log
commit 48ec3fbe8a8610b7e319a6ad5915b7d77185fd64 (HEAD -> master)
Author: Tomas <tomascastello444@gmail.com>
Date:   Wed Oct 13 08:33:09 2021 +0200

    Añadido capitulo 1 
tomas@tomas-VirtualBox:~/Git/capitulos$ vim capitulo2.txt
tomas@tomas-VirtualBox:~/Git/capitulos$ git add capitulo2.txt
tomas@tomas-VirtualBox:~/Git/capitulos$ git commit -m "Añadido capitulo 2"
[master 1069b2e] Añadido capitulo 2
 1 file changed, 1 insertion(+)
 create mode 100644 Git/capitulos/capitulo2.txt
 tomas@tomas-VirtualBox:~/Git/capitulos$ git diff HEAD~2..HEAD
fatal: argumento ambiguo 'HEAD~2..HEAD': revisión desconocida o ruta fuera del árbol de trabajo.
Use '--' para separar las rutas de las revisiones, de esta manera:
'git <comando> [<revisión>...] -- [<archivo>...]'
tomas@tomas-VirtualBox:~/Git/capitulos$ vim capitulo3.txt
tomas@tomas-VirtualBox:~/Git/capitulos$ git add capitulo3.txt
tomas@tomas-VirtualBox:~/Git/capitulos$ git commit -m "Añadido capitulo 3"
[master d9d5e2f] Añadido capitulo 3
 1 file changed, 1 insertion(+)
 create mode 100644 Git/capitulos/capitulo3.txt
 tomas@tomas-VirtualBox:~/Git/capitulos$ git diff HEAD~1..HEAD
diff --git a/Git/capitulos/capitulo3.txt b/Git/capitulos/capitulo3.txt
new file mode 100644
index 0000000..589038e
--- /dev/null
+++ b/Git/capitulos/capitulo3.txt
@@ -0,0 +1 @@
+t permite la creación de ramas los que permite tener distintas versiones del mismo proyecto y trabajar de manera simultanea en ellas.
tomas@tomas-VirtualBox:~/Git/capitulos$ vim indice.txt
tomas@tomas-VirtualBox:~/Git/capitulos$ git add indice.txt
tomas@tomas-VirtualBox:~/Git/capitulos$ git commit -m "Añadido capitulo 5 al indice"
[master 4700891] Añadido capitulo 5 al indice
 1 file changed, 1 insertion(+)
 create mode 100644 Git/capitulos/indice.txt
 tomas@tomas-VirtualBox:~/Git/capitulos$ git annotate indice.txt
47008912        (     Tomas     2021-10-13 09:00:49 +0200       1)Capítulo 5:Conceptos avanzados
~~~