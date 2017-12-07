# Práctica del curso de git, gitHub y Sourcetree

## Carlos Gómez Pino

### ¿Qué comando utilizaste en el paso 11? ¿Por qué?

Se ha hecho uso del comando `git reset --hard HEAD~1`. Con la instrucción *reset* movemos la rama de lugar, concretamente se mueve al commit padre, el cual se lo indicamos con *HEAD~1*. Por último, con *--hard* hacemos que se pierdan los cambios en el working copy.

### ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

Se puede hacer de varias formas, una de ellas es usar el comando `git reflog`, y mirar el identificador del último commit por el que pasamos y hacer `git reset --hard [identificador del commit]`. No obstante hay una manera más sencilla, y es usar `git reset --hard HEAD@{1}`, que moverá la rama justo al lugar en el que estuvo en la iteración anterior.

### El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?

No se produce ningún conflicto, pero tampoco ningún cambio puesto que la rama styled ya contenía todos los cambios de la rama master.

### El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

Se producen conflictos al mezclar htmlify y styled, debido a que en ambas ramas se han modificado las mismas líneas con respecto a la rama master.

### El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

La rama styled solo tiene añadidos con respecto a master. Por tanto se hace un merge fast-forward y no se produce ningún conflicto, ya que simplemente la rama master avanza hacía el commit de la rama styled, sin producirse ningún nuevo commit.

### ¿Qué comando o comandos utilizaste en el paso 25?

Para dibujar el diagrama se ha hecho uso del comando `git log --graph`

### El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

Sí podría serlo, de hecho de no haber indicado el parámetro *--no-ff* sería fast forward por defecto. Puede serlo debido a que en la rama title con respecto a la master sólo hay añadidos, es decir, el grafo es lineal sin ninguna ramificación hasta el commit donde se quiere hacer el merge.

### ¿Qué comando o comandos utilizaste en el paso 27?

Normalmente para deshacer un merge se podría hacer uso del comando `git reset HEAD@{1}` (sin *--hard* para no perder los cambios del working copy). No obstante en este caso, al haberse realizado un merge sin fast forward, se podría usar también el comando `git reset HEAD~1`.

### ¿Qué comando o comandos utilizaste en el paso 28?

Se ha hecho uso del comando `git checkout -- .` para descartar los cambios de todos los archivos del directorio. En este caso (dado que sólo es un archivo), se podría sustituir el punto por el nombre del archivo (git-nuestro.md).

### ¿Qué comando o comandos utilizaste en el paso 29?

Se ha hecho uso del comando `git branch -D title`. En este caso se usó el parámetro `-D` para que git no nos hiciera la pregunta de seguridad.

### ¿Qué comando o comandos utilizaste en el paso 30?

Dado que deshacer el merge ha sido la última operación en la que nos hemos movido de commit que hemos realizado, basta con hacer uso del comando `git reset --hard HEAD@{1}`.

### ¿Qué comando o comandos usaste en el paso 32?

Podemos acceder al listado completo de movimientos realizados si hacemos uso del comando `git reflog`. Una vez hecho esto, bastará con apuntar la dirección del commit en el que se creó la primera versión del poema (410a00f). Luego podremos movernos a dicho commit haciendo uso del comando `git reset 410a00f`. Si además queremos aplicar los cambios en el working copy, podemos añadir el parámetro *--hard*.

### ¿Qué comando o comandos usaste en el punto 33?

Para volver al estado final de nuevo podemos recurrir a la misma estrategia, hacer un `git reflog` y `git reset [identificador]`. No obstante, dado que el estado final fue el último por el que pasamos, resulta más sencillo hacer uso del comando `git reset HEAD@{1}`. Nuevamente si queremos aplicar estos cambios al working copy, podemos añadir el parámetro *--hard*.
