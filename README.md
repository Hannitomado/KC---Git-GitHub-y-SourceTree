# KC---Git-GitHub-y-SourceTree
Repositorio para subir las practicas del modulo "Git, GitHub y SourceTree" del Bootcamp de IA 3

Ejercicio 1

Pasos

1. Crear un repositorio en GitHub y clonarlo en mi equipo. ☑
2. Crear un archivo git-nuestro.md con el siguiente provisto. ☑
Usando el comando notepad git-nuestro.md creamos un archivo de bloc de notas donde escribimos el texto que se nos has provisto.

3. Añadir git-nuestro.md al staging area. ☑
Mandamos el archivo desde Working Copy a Staging Area usando el comando git add git-nuestro.md

4. Mover lo que hay en el staging area al repositorio. ☑
Movemos todo lo que hay en Staging Area a Repositorio con el commando git commit.

5. Crear una rama llamada “styled”. ☑
Creamos la rama con el comando git branch styled.
6. Listar las ramas que hay en el repositorio. ☑
Con el comando git branch comprobamos cuantas ramas hay. En este paso, existen dos ramas, “main” y “styled”. Un arterisco nos indica que en estos momentos nos encontramos en la rama “main”.

7. Moverse a la rama “styled”. ☑
A traves del comando git checkout styled, nos movemos a la rama “styled”.

8. Comprobar que se esta en la rama correcta.☑
Volvemos a usar git branch para comprobar que estamos en “styled”.

9. Modificar el archivo git-nuestro.md.☑
Abrimos el archivo usando notepad git-nuestro.md, y modificamos el texto. Esto hace que el archivo se mueva al Working Copy.

10. Añadir cambios al staging area y luego pasarlos al repositorio. ☑
Usamos primero git add git-nuestro.md, y luego git commit. De esta manera, hemos movido el archivo primero al Staging Area, y luego al repositorio.

11. Deshacer el ultimo commit (perdiendo los cambios realizados). ☑
Como el paso nos pide deshacer el ultimo commit perdiendo los cambios realizados, usamos git reset --hard Head~1. Lo que deshace el ultimo commit y elimina los cambios que habiamos hecho.

12. Rehacer el ultimo commit (el que acabamos de deshacer). ☑
Dado que hemos usado un hard reset, hemos eliminado todos los cambios que se habian hecho en el ultimo commit. Para poder rehacerlos y volver a el podemos hacer un reset a un punto del commit donde esos cambios habian sido aplicados. Primero usamos el comando git reflog, y comprobamos el log de los cambios que se han hecho en nuestro repositorio. Cogemos el codigo del commit en el que habiamos modificado nuestro archivo git-nuestro.md. Para ello hemos escrito una descripcion del commit clara, donde indicamos que en ese commit habiamos editado el texto. Usamos el comando git reset --hard 75f7fbf (que es el codigo que tiene asignado el commit destino) y volvemos a el. 

13. Hacer un merge con “main” (“styled” absorbe a “main”). ☑
Usando git merge main, hemos hecho que la rama “styled” en la que nos encontrabamos, absorbiese a “main”. Al hacerlo hemos recibido el siguiente mensaje “Already up to date”. Este mensaje nos indica que no habia ningun elemento o cambio en “main” que no estuviese en “styled”, y por lo tanto git no ha necesitado hacer nada. 

14. Volver a la rama main. ☑
Volvemos a “main” con el comando git checkout main.

15. Creamos una nueva rama llamada “htmlify”. ☑
Escribimos el comando git branch htmlify y creamos asi la rama “htmlify”.

16. Cambiar a la rama htmlify. ☑
Nos vamos a “htmlify” con git checkout htmlify.

17. Modificar el archivo git-nuestro.md de la forma propuesta. ☑
Volvemos a modificar git-nuestro.md introduciendo los nuevos cambios, repitiendo lo que hicimos en el paso 9.

18. Hacer un commit. ☑
De nuevo, repetimos el paso 10 y hacemos un commit de nuestros nuevos cambios.

19. Hacer un merge de “htmlify” en “styled” (“styled” absorbe a “htmlify”). ☑
Nos vamos a la rama “styled” con git checkout styled, y hacemos que esta rama absorba a “htmlify” con git merge htmlify, lo que resulta en un conflicto. El conflicto resulta de intentar combinar dos ramas que tienen el mismor archivo pero en diferentes versiones, o dos archivos diferentes con el mismo nombre. Para poder continuar, git nos pide que resolvamos el conflicto.

20. Si hay conflictos, deberemos resolverlos quedandonos con el contenido de la rama “styled”. ☑
Para resolver el conflicto, abrimos nuestro archivo con notepad git-nuestro.md, y eliminamos los marcadores de conflicto. Despues, añadimos este cambio, y hacemos commit.

21. Desde “main”, hacer un merge con “styled”. ☑
En este caso no se ha generado ningun conflicto. Lo que ha sucedido es que al tener una version anterior de nuestro commit, git simplemente ha hecho fast forward y ha movido “main” a “styled”, actualizando su version antigua de git-nuestro.md.

22. Crear una rama “title” y cambiarse a esa rama. ☑
Escribimos git branch title, creando asi la nueva rama, y con git checkout title nos movemos a ella.

23. Añadir un titulo al archivo git-nuestro.md y hacer un commit. ☑
Abrimos nuestro archivo y en markdown le damos el titulo “Salmo Gitero”. Despues hacemos el commit dandole una descripcion adecuada.

24. Volver a la rama “main”. ☑
Volvemos a “main” con nuestro conocido git checkout main.

25. Dibujar el diagrama. ☑
Creamos nuestro diagrama en git bash usando la linea de codigo git log --oneline --graph --all --decorate. 

$ git log --oneline --graph --all --decorate
* 0e3eca4 (title) Damos un titulo a nuestro Salmo Gitero
*   755aa8a (HEAD -> main, styled) Combinamos main con styled
|\
| * 1f8668c Hacemos el primer commit de nuestro Salmo Gitero
* |   8adc658 Resolvemos el conflicto entre ramas, nos quedamos la de styled.
|\ \
| * | ffc1e1b (htmlify) Modificamos por segunda vez nuesto Salmo Gitero
| * | 45414f5 Rehacemos el commit que habia fallado
| |/
* / 75f7fbf Editamos nuestro Salmo Gitero
|/
* 9dbfeeb Hacemos el primer commit de nuestro Salmo Gitero
* bd78e21 (origin/main, origin/HEAD) Initial commit

En nuestro caso, se ve un poco rara por que hemos tenido unas incidencias con el notepad de Windows. Al parecer ha habido un momento en el que no se estaba cerrando bien, y por lo tanto no me dejaba guardar y hacer commits, y luego por algun sistema automatico estaba actualizando el archivo que estabamos creando en otra rama, en la rama principal. Esto ha sucedido dos veces, asi que al final he acabado creando dos nuevos commits para poder tener el archivo como se nos indicaba.

26. Hacer un merge “no fast-forward” de “title” en “main” (“main” absorbe a “title”). ☑
Ahora vamos a hacer otro merge donde “main” absorba a “title”. Siguiendo las instrucciones del ejercicio, especificaremos a git que no queremos un merge fast-forward. Para ello usamos el codigo git merge --no-ff title.

27. Deshacer el merge (sin perder los cambios del Working Copy). ☑
Para deshacer el merge sin perder ningun cambio en Working Copy o Staging Area vamos a usar la linea de codigo git reset --soft HEAD~1. A diferencia del git reset --hard HEAD~1 que hemos usado antes, este comando no borra todo lo que hay hasta el paso indicado por el numero hash de HEAD~ <hash>.

28. Descartar los cambios. ☑
Ahora usamos git reset --hard para eliminar los cambios que se nos habian quedado fuera del comit al deshacer el merge.

29. Eliminar la rama “title”. ☑
Con la linea git branch -D title, eliminamos la rama “title”.

30. Rehacer el merge que hemos deshecho. ☑
Ahora para rehacer el merge entre “main” y “title” usamos git reflog para ver en que lugar nos quedo ese merge, y a traves de l comando git reset --hard, volvemos a ese punto.

31. Volver a main y eliminar el resto de ramas. ☑
Volvemos a “main” con git checkout main, y usando la misma linea que usamos con “title”, borramos el resto de ramas.

32. Volver al commit inicial cuando se creo el poema. ☑
Una vez mas, utilizaremos git reset --hard + <hash> del primer commit, para volver a el. Primero miramos que codigo es con git reflog, y utilizamos el comando para ir al comienzo.

33. Volver al estado final, cuando pusimos titulo al poema. ☑
Y ahora en direccion contraria, de nuevo consultamos git reflog para ver el codigo del commit que hicimos cuando pusimos titulo, y usamos git reset --hard <hash> para volver al final.

34. Crear los siguientes tags: ☑
Inicial: en el primer commit
Styled: modificacion del paso 10
Htmlify: modificacion del paso 17-18
Title: modificacion del paso 30
Para cada uno de los tags que vamos a crear, primero usaremos git reflog para obtener sus numeros hash, y luego escribimos el siguiente codigo:
git tag Inicial 9dbfeeb
git tag Styled 75f7fbf
git tag Htmlify ffc1e1b
git tag Title c581d2e
35. Ir al tag “Htmlify”. ☑
Vamos a nuestro tag llamado “Htmlify” usando el codigo git reset Htmlify.

36. Volver a la rama main. ☑
Volvemos a main con git checkout main.
37. Subir a GitHub todas las ramas y todos los tags. ☑
Como hemos borrado todas las ramas, vamos a necesitar recrearlas otra vez. Para ello como ya hemos hecho antes, vamos a mirar primero en git reflog cual es su numero hash, y luego usamos el codigo git branch branch_name <hash>.
Una vez que las tenemos recreadas, para subir a GitHub tanto las ramas como los tags,  usamos git push --all origin y git push --tags, respectivamente.

