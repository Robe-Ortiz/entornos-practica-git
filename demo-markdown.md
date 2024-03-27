# GUÍA PARA EL USO DE GIT

### INTRODUCCIÓN

Este repositorio ha sido creado para realizar un ejercicio de la asignatura Entornos de Desarrollo.

Dicho ejercicio consiste en demostrar lo que hemos aprendido sobre el lenguaje Markdown. Para ello, debemos crear un documento de temática libre y aplicar los conocimientos adquiridos.

Dado que la temática es libre, he decidido realizar un tutorial sobre las instrucciones básicas de Git.

Todo lo aprendido sobre Git está extraído del libro:

> "Git & GitHub desde cero" -Brais Moure

Enlace del libro: [Libro Git & GitHub desde cero](https://leanpub.com/git-github)

## ¿Qué es Git?

Git es una **herramienta de control de versiones** distribuido que permite a los desarrolladores trabajar en un proyecto sin necesidad de estar conectados a un servidor central.

Una herramienta de control de versiones se utiliza para mantener un registro de los cambios que se hacen en un proyecto. Permite a los desarrolladores trabajar en un proyecto de manera colaborativa, manteniendo un historial de cambios y documentando cada uno de ellos.

## Configuración

Es importante tener en cuenta que la instalación de Git varía según el sistema operativo utilizado. Se recomienda visitar la página oficial de Git para encontrar la mejor manera de instalarlo según nuestras especificaciones.

[Web oficial de Git](https://git-scm.com/)

Una vez instalado, debemos configurar dos parámetros obligatorios antes de empezar a utilizar Git:

```bash
git config --global user.name "nombre usuario"
git config --global user.email "correo electrónico usuario"
```

La primera instrucción define el nombre de usuario y la segunda el correo electrónico asociado a ese usuario. Esto es indispensable para poder utilizar Git.

Por último, en la configuración de Git, tenemos otro parámetro que, aunque no es obligatorio, es muy aconsejable cambiar, ya que actualmente es el estándar.

```bash
git config --global init.defaultBranch "main"
```
Con esto conseguiremos que cada vez que creemos un repositorio, la rama principal se llame "main" en lugar de "master".

## Primeros pasos

Las instrucciones básicas de Git en este apartado son:

- `git init`
- `git status`
- `git add`
- `git commit`

### git init

Para crear un repositorio, debemos navegar mediante la consola Bash al directorio en el que queremos crear el repositorio.

Una vez ubicados en el directorio, escribimos la siguiente instrucción:

```bash
git init
```
Hecho esto, tendremos nuestro repositorio creado.

### git status

Muestra el estado del directorio de trabajo. Permite ver los cambios que se han preparado, los que no y los archivos en los que Git no va a realizar el seguimiento.

```bash
git status
```

### git add

Este comando se utiliza para añadir archivos al área de ***stage***, que es la zona donde colocamos los archivos antes de realiar un commit.

```bash
git add
```
Detrás de `add` podemos poner el nombre del archivo que queremos añadir. En caso de querer añadirlos todos, podemos poner un punto.

```bash
git add ejemplo.txt
git add .
```

### git commit

Sirve para capturar una instantánea de los cambios preparados en ese momento del proyecto. Estas instantáneas pueden considerarse como versiones "seguras" de un proyecto.

Es importante saber que cuando realizamos un commit, solo lo haremos de los archivos que previamente hemos agregado al **stage** con la instrucción `git add`.


```bash
git commit
```

Este comando, al ejecutarlo, nos abrirá un editor de texto donde nos obligará a escribir un comentario que acompañará al commit.

Para evitar esto, tenemos la opción `-m` con la cual podremos añadir directamente en la línea de comando el comentario.

```bash
git commit -m "Añadido registro de usuarios"
```
Los comentarios en los commit son obligatorios. Debemos, de forma escueta y concisa, definir la razón de ser del commit, como hemos hecho en el ejemplo anterior.