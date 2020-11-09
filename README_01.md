
# ¿Qué es GitHub?

GitHub es un sitio web y un servicio en la nube que ayuda a los desarrolladores a almacenar y administrar su código, al igual que llevar un registro y control de cualquier cambio sobre este código. Para entender exactamente qué es GitHub, primero usted necesita conocer los dos principios que lo conectan:

- Control de versión
- Git

## Versión de Control

Una Versión de Control ayuda a llevar un registro y administrar cualquier cambio en el código del proyecto. A medida que crece este proyecto, la versión de control se vuelve esencial. 

La versión de control permite trabajar de forma segura a través de una bifurcación y una fusión.

- Con la bifurcación, se duplica parte del código fuente (llamado repositorio). Luego, de forma segura se pueden hacer cambios a esa parte del código, sin afectar al resto del proyecto.

- Después, una vez que se logre que parte del código funcione de forma apropiada, se podría fusionar este código al código fuente principal para hacerlo oficial.

_Todos estos cambios luego son registrados y pueden ser revertidos si es necesario._


## ¿Qué Es Git?

Git es un sistema de control específico de versión de fuente abierta creada por Linus Torvalds en el 2005.

Específicamente, Git es un sistema de control de versión distribuida, lo que quiere decir que la base del código entero y su historial se encuentran disponibles en la computadora de todo desarrollador, lo cual permite un fácil acceso a las bifurcaciones y fusiones.





[`git`](https://git-scm.com/) es un programa que sirve para llevar el control de versiones de un proyecto informático. Puedes entenderlo como una mezcla de control de cambios de word con el versionamiento de documentos de GoogleDrive para saber qué cambios hiciste a un script, por qué y cuándo, de manera que es más fácil mantener el orden, "volver al pasado" y trabajar en paralelo con colegas.


[Github](https://github.com/) Es un repositorio de código que:

* Utiliza `git` para llevar un sistema de **control de versiones**,
* Tiene una interfase Web pública
* Permite escribir/revisar código en equipo
* Su símbolo es un gatopulpo. 

![](Octocat.png)


## Open Source


## ¿De dónde viene Git?






Es muy buena idea llevar un control de versiones de tus scrips en tu carpeta `bin`.

Sin embargo, cuando subas tu proyecto con todo y datos como un repositorio (e.g. a Dryad) recuerda **NO** compartir la carpeta `.git`.

Como introducción a `git` primero vamos a entender los principales conceptos y el [flujo de trabajo de Github leyendo esta documentación](https://guides.github.com/introduction/flow/). 

Y es muy buena idea leer [An Intro to Git and GitHub for Beginners (Tutorial) de Meghan Nelson](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners).


### Los términos más importantes

+ **Repositorio**: Se usa para organizar un proyecto. Puede contener imágenes, código, etc. Es recomendable incluir un README.

+ **Fork**: Se crea un fork cuando el repositorio es copiado de la cuenta de un miembro de Github a la de otro.

+ **Branch**: El repositorio tiene una rama o branch principal llamada `master`, que es la "original". Se pueden crear otras ramas dentro del mismo repositorio en las cuales se pueden hacer modificaciones sin afectar el código original. Es el equivalente tener un archivo original `Tesis` y ponerle `Tesis_comentariosAsesora1` y `Tesis_comentariosAsesor2` a los archivos con los comentarios de tus asesores, mismos que eventualmente volverás a integrar en un archivo final (pero `git` lo hace todo más hermoso y organizado).

+ **Commit**: Equivale a guardar los cambios **en git** que no es lo mismo que en el archivo. ¡Ojo! Los cambios se guardan en la branch donde trabajas. Puedes acompañar el commit de un mensaje corto para especificar qué cambios hiciste. Esto es mucho mejor que tener nombres de archivos larguísimos tratando de explicar qué versión son (e.g. `Tesis_final_comentariosAMY_DP_rev22oct2017_comentariosFran_revEnero2018_FINAL_BUENO_corrected_2.doc`).

+ **push:** para enviar los commits locales al repo online.

Piensa en `push` para enviar y `pull` para recibir.

+ **Pull request**: Si se quieren agregar las modificaciones en la branch `master`, se envía una solicitud al propietario original. Es decir tú no haces `push`, le pides al propietario que haga `pull`.

+ **Merge**: Una vez que el propietario del repositorio ha revisado y aceptado los cambios, fusiona las ramas. 




## 1.6. Control de versiones con git y Github


### Configurando nuestro git local con Github

Para poder vincular tu `git` con tu cuenta de Github necesitas cambiar **asociar tu dirección de correo electrónico principal de Github con tu git local**. Además puedes cambiar tu nombre de usuario, pero lo que realmente te vincula con Github es tu correo. 

Para cambiar tu correo necesitas seguir cualquiera de estos dos métodos:

1) Correr `$ git config --global --edit` 

Lo cual abrirá una pantalla de `vim`. Edita tu nombre de usuario y cuenta de correo. Para poder "escribir en vim" presiona `I` (de insertar) donde quieras comenzar a escribir. Recuerda, para guardar y salir, tecla Esc y luego `:wq`.

2) Correr:

`$ git config --global user.email "email@example.com"`

`$ git config --global user.name "Mi_nombre"`

Donde el texto entre comillas son tus datos.

Comrpueba tu dirección es la correcta con:

`$ git config user.email`

Debe mostrarse tu dirección correcta.


[Referencia de lo anterior](https://help.github.com/articles/setting-your-commit-email-address-in-git/)


### Ejemplo: vamos a crear un repo

#### `git init`
Te permite crear un repo desde tu disco local. En la terminal escribe:

```
$ mkdir repo_name # crear un directorio en tu disco local
$ cd repo_name
$ git init # transformar ese directorio en un repositorio git
$ git status # verificar que el repositorio ha sido creado
```

Para conectar ese nuevo repostorio a github:
+ Log in en tu cuenta de github
+ En 'Repositories' click en el boton verde 'NEW"
+ Dale el mismo nombre que tu repostorio local y click en el botom 'Create repository'
+ Vuelves al terminal para conectar tu repo local con el repo en github, usando:

```
$ git remote add origin https://github.com/<username>/<repo_name>.git
$ git push -u origin master
```

### Ejemplo: vamos a clonar un repo.

#### `git clone`
Te permite copiar un repositorio que ya existe. Cada versión de cada archivo de la historia del proyecto es descargado cuando lo ejecutas. La dirección del repo que quieres clonar puedes conseguirla en el botón verde que dice "Clone or Download" en la página principal del repo en Github.

**Ojo con dónde corres `git clone`, pues tu working directory será el lugar a donde "se baje" el repo que estás clonando.**

```
$ git clone https://github.com/AliciaMstt/Repo_chocolate.git
Cloning into 'Repo_chocolate'...
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (2/2), done.
Unpacking objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0

```

Para poder hacer los siguientes comandos debemos estar en el directorio del repo. Es decir lo que acabamos de bajar. Así que `cd Repo_chocolate`.

#### `git status`
Es para saber en qué branch estas trabajando y si tienes archivos que te falte "guardar" (commit). Por ejemplo, si lo haces cuando acabas de clonar un repositorio, debe verse algo así:

```
$ git status                           []
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```

#### `git add`
Te permite agregar un archivo que no existía en el repositorio o prepara las modificaciones a archivos existentes. Esto no lo "guarda" (commit), solo hace que "lo sigas". Si modificas un archivo es necesario que vuelvas a dar `add`.

```
$ touch ejemplo.txt
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	ejemplo.txt

nothing added to commit but untracked files present (use "git add" to track)
$ git add ejemplo.txt
```


#### `git commit`
Confirma y agrega los cambios a la branch en la que estas trabajando. Utiliza la flag `-m` para escribirun mensaje breve. Si no lo haces se abrirá un editor de texto donde puedes describir brevemente el cambio que hiciste. Si tu editor es Vim, puedes guardar y salir con `:wq`.

```
$ git commit -m "agregar archivo ejemplo"
[master 79fce15] agregar archivo ejemplo
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 ejemplo.txt
```

#### `git diff`
Para ver los cambios que se hicieron a un archivo.

```
$ echo "el mundo es bello" > ejemplo.txt
$ cat ejemplo.txt 
el mundo es bello
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   ejemplo.txt

no changes added to commit (use "git add" and/or "git commit -a")
$ git diff ejemplo.txt
diff --git a/ejemplo.txt b/ejemplo.txt
index 8d269c1..0dc4fee 100644
--- a/ejemplo.txt
+++ b/ejemplo.txt
@@ -1 +1 @@
-bla bla bla
+el mundo es bello
```



#### `git rm`
Si quieres borrar un archivo **que ya había formado parte de un commit** no sólo de tu compu sino del sistema de versiones de git, lo mejor es NO utilizar `rm`, sino `git rm`. Ejemplo:

```
$ touch ejemplo2.txt
$ git add ejemplo2.txt
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   ejemplo2.txt
$ git add ejemplo2.txt
$ git commit -m added ejemplo2
$ git rm ejemplo2.txt
$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	deleted:    ejemplo2.txt

```

#### `git push`

Una vez que quieres integrar tus cambios a una rama, este comando te permite fusionar ramas. Debes decirle el origen (rama donde hiciste los commits) y el destino (por ejemplo master u otra rama).

**Ojo** uds no podrán hacer `push` porque no son propietarios de este repo. Para ello deberían hacer primero un `pull request`. Más adelante haremos ejercicios de esto.


```
$ git push origin master
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 285 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/AliciaMstt/Repo_chocolate.git
   72129b3..79fce15  master -> master
```

Nota: puedes agregar la flag `-u` para establecer `origin master` (o lo que sea) como el default y solo tener que hacer `git push` en un futuro.


#### `git pull`
Actualiza la copia del repositorio local con respecto a la rama remota. Es decir


```
$ git pull                             []
Already up-to-date.
```

Pero ojo, antes de andar con `pull` por la vida [checa las bondades de `git fetch`:

#### `git fetch`

Si vas a trabajar con repos de otras personas problablemente no quieras hacer un `merge` en automático (que es lo que hace `pull` tras bambalinas) con tu repo local, sino que solo quieras jalar los cambios que hayan hecho otros. Por ejemplo los archivos que agregue a este repo sin que borre lo que tu hayas hecho en tu versión. [Para evitar posibles problemas asociados a esto se recomienda usar `fetch`]((https://help.github.com/articles/fetching-a-remote/)).

[Otra referencia de fetch vs pull](https://longair.net/blog/2009/04/16/git-fetch-and-merge/)

Voy a hacer unos cambios en el archivo `ejemplo.txt` desde el editor de texto de Github y comitearlo (sí, espanglish del chido) online. Ahora veamos los cambios:

```
$ git fetch
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From https://github.com/AliciaMstt/Repo_chocolate
   79fce15..ad845a6  master     -> origin/master
$ head ejemplo.txt

$ git status
On branch master
Your branch is behind 'origin/master' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)
nothing to commit, working tree clean

$git pull
Updating 79fce15..ad845a6
Fast-forward
 ejemplo.txt | 1 +
 1 file changed, 1 insertion(+)

$ head ejemplo.txt 
bla bla 

```


#### `git log`

Para ver el historial de commits que se han hecho en el repo. Por default te mostrará los commits en orden cronológico invertido, pero hay muchas opciones que puedes darle para buscar algo más específico. [Instrucciones aquí](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History).


**Ejercicio:** clona el repositorio de la clase y actualízalo que vez que sea necesario. **NOTAS IMPORTANTES PARA ESTE EJERCICIO:** 

1) Clonalo en un lugar distinto de dónde habías bajado la carpeta del repo las clases anteriores, o cámbiale el nombre a esa carpeta vieja, o símil.

2) Como mi repo tiene más de una rama, necesitarás agregar a tu `git clone` lo siguiente: `--branch master --single-branch`.

#### `git` para la vida diaria en resumen:

0) `git pull` para jalar los cambios de una rama en Github a nuestra rama local (compu).

1) `git status` dentro del directorio de tu repo para ver si hay cambios.

2) `git diff nombrearchivo` para ver las modificaciones que se hicieron a un archivo desde el último commit.

3) `git add nombrearchivo` (para un archivo) o `git add *` (para todos los archivos) para agregar los archivos **que queremos incluir en un commit**. Como el equivalente a "adjuntarlos" en un correo que te enviarías por correo. 

4) `git commit -m "mensaje corto explicando qué contiene el commit"`. Como el contenido de un correo donde te explicarías a tí mismx qué cambios hiciste que ameritan guardar la versión ("commit").

5) `git push` para enviar nuestros cambios locales a Github.



#### ¿Cómo volver al pasado?

Hay muchas formas. [Esta respuesta de Stacksoverflow es una buena guía](https://stackoverflow.com/questions/4114095/how-to-revert-a-git-repository-to-a-previous-commit).



### Recomendación: ignorar archivos que no queremos que git siga**

Algunso archivos no queremos que sean considerados por `git`, por ejemplo archivos que la compu hace en automático como los "fantasmitas de Mac" o archivos de datos muy pesados si queremos solo publicar el código. Podemos entonces decirle a git cuáles archivos ignorar. Pasos:

1) Crear un archiovo `.gitignore` en el wd de tu repositorio (donde vive tu `.git` que se creó con `git init` o con `git clone`).

`touch .gitignore` (nota el punto `.`)

2) En ese archivo poner el nombre (o las extensiones) de los archivos que quieres ignorar. [Aquí puedes ver una lista de casos comunes proporcionada por Github](https://gist.github.com/octocat/9257657).

Por ejemplo yo voy ignorar los fantasmitas Mac:


`$ vim .gitignore`

Y en el editor de vim pegué lo siguiente:

```
# OS generated files #
######################
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

```

3) Si haces un `git status` notarmás que aparece `.gitignore` como untracked. Entonces debes:

```
$ git add .gitignore
$ git commit -m "Added .gitignore file to repo"
$ git push 
```

También puedes crear un `.gitignore` global que aplique en todos los repos de tu compu. Instrucciones [aquí](https://help.github.com/articles/ignoring-files/)



### Documentación extra


* [Learn Git Branching](https://learngitbranching.js.org/) para volverse chidos manejando el ramerío.


* [A successful Git branching model de VincentDriessen](http://nvie.com/posts/a-successful-git-branching-model/). Excelente.

Lo primero que hay que hacer es este tutorial: [Hello-world Github Guide](https://guides.github.com/activities/hello-world/) para aprender a crear un repo en Github y utilizar su versión web.


### Ejercicios:

1. Configura tu git local a Github con las instrucciones que dimos arriba

2. Sigue el [tutorial de Hello World](https://guides.github.com/activities/hello-world/) para crear un repositorio con el nombre de tu proyecto. Este es el repositorio que ocuparás para poner los scripts de tu proyecto que revisaremos durante el curso.

3. Realiza este tutorial de git [https://learngitbranching.js.org/](https://learngitbranching.js.org/).

4. Ve al Repo_chocolate que utilizamos en un ejercicio de arriba. Utiliza git para volverr al commit donde el archivo example2.txt existía pero estaba vacío.

5. Lee la [documentación de `pull request` en Github](https://help.github.com/en/articles/about-pull-requests). Con base en esto, modifica el archivo `/Unidad1/listado_estudiantes.txt` del repositorio del curso para agregar tu nombre y nombre de usuario de github a la lista. Posteriormente has un `pull request` para que nosotros lo veamos y aceptemos en el repositorio.  
