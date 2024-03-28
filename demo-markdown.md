# GUÍA PARA EL USO DE GIT

![Logotipo de Git](/git_logo.png)

## INTRODUCCIÓN

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

[Página oficial de Git](https://git-scm.com/)

Una vez instalado, debemos configurar dos parámetros obligatorios antes de empezar a utilizar Git, para ello podemos abrir la terminar bash que se ha instalado junto a Git y tecleamos las siguientes instrucciones:

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

Para el manejo de Git, solo son necesarias una decena de instrucciones. A lo largo de esta guía, veremos las más relevantes e importantes para poder empezar a trabajar con Git.

Instrucciones Git en este apartado:

- `git init`
- `git status`
- `git add`
- `git commit`
- `git log`

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

Este comando se utiliza para añadir archivos al área de ***stage***, que es la zona donde colocamos los archivos antes de realizar un commit.

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

### git log

Al ejecutar este comando, Git muestra una lista con todos los commits realizados en el repositorio, incluyendo el __hash__ único que identifica a cada uno de ellos.

Esta información es útil para rastrear la evolución del proyecto y asegurarnos de que todas los commits se han almaenado según lo esperado.

```bash
git log
```

## Creación y manejo de ramas

Uno de los conceptos fundamentales de Git son las ramas, que permiten a los equipos trabajar en diferentes flujos de desarrollo de manera independiente y colaborativa.

Instrucciones de Git en este apartado:

- `git branch`
- `git switch`
- `git checkout`
- `git merge`

### git branch

Para crear una nueva rama en Git, utilizamos el comando `git branch`, seguido del nombre de la nueva rama.


```bash
git branch login
```

Una vez hecho esto, tendremos creada una nueva rama con la información del commit en el que estábamos ubicados.

### git switch

Para movernos entre las distintas ramas, tenemos la instrucción `git switch`.

```bash
git switch login     
git switch main      
```

Con estas instrucciones nos hemos desplazado a la rama login y después a la main.

### git checkout

Aunque `git checkout` también puede usarse para moverse entre ramas, `git switch` está diseñado específicamente para esa función.

Además del cambio entre ramas, `git checkout` puede realizar otras funciones como cambiar entre distintos hash, tags y commits.

```bash
git checkout login
```

La documentación de Git indica que para cambiar entre ramas por el nombre, debemos de usar `git switch`

### git merge

Las ramas son copias independientes del código base, lo que nos permite trabajar en diferentes características o funcionalidades sin afectar al código principal. Sin embargo, en algún momento será necesario integrar el trabajo realizado en una rama en otra.

Git nos ofrece el comando `git merge` para fusionar los cambios realizados en una rama con otra. Este comando toma los cambios realizados en una rama y los aplica a otra, creando un nuevo commit que combina ambos historiales.

Para realizar un merge, debemos situarnos en la rama destino y utilizar la instrucción indicando la rama de la cual queremos traernos los cambios.

```bash
git merge login
```

Si al realizar la fusión existiera algún conflicto, Git nos avisaría y tendríamos que resolver el conflicto de forma manual. Existen instrucciones que podrían resolver el conflicto, pero son más avanzadas y no son el objetivo de esta guía.

## Instrucciones

En este apartado crearemos una tabla con todas las instrucciones que hemos visto en la guía, para poder utilizarla de forma rápida.

| Instrucción | Apartado                   | Definición                                    |
|-------------|----------------------------|-----------------------------------------------|
|git config   | Configuración              | Define valores de configuración               |
|git init     | Primeros pasos             | Creación de un repositorio                    |
|git status   | Primeros pasos             | Muestra estado del directorio de trabajo      |
|git add      | Primeros pasos             | Añade archivos al área de stage               |
|git commit   | Primeros pasos             | Captura instantánea de los cambios preparados |
|git log      | Primeros pasos             | Muestra listado de commmits realizados        |
|git branch   | Creación y manejo de ramas | Crea una nueva rama                           |
|git switch   | Creación y manejo de ramas | Desplazamiento básico entre ramas             |
|git checkout | Creación y manejo de ramas | Desplazamiento avanzado entre ramas           |
|git merge    | Creacion y manejo de ramas | Fusiona dos ramas                             |


Estos no son ni mucho menos todos los comandos disponibles en Git, son los que a mi parecer considero indispensables para poder comenzar a trabajar.