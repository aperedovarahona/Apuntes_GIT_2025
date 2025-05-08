# Apuntes_GIT_2025 

## 🧠 Contenido ##

+ 📌 Introducción a Git

+ 📁 Configuración Inicial

+ 📂 Comandos Básicos

+ 🧭 Ramas (Branches)

+ 🔁 Merge y Rebase

+ 🌐 GitHub y Repos Remotos

+ 🛠️ Buenas Prácticas


## 📌 Introducción a Git ##

![Git_Logo](img/git_logo.png)

Git es un sistema de control de versiones distribuido, creado por Linus Torvalds en 2005. Permite registrar y controlar cambios en archivos de forma eficiente y colaborativa.

### ¿Que es un control de versiones? ###
 
+ Es un sistemas que registra cada cambio que se realiza dentro del codigo fuente de un proyecto.

+ Permite tener un historial de todos lo cambio producidos, ademas de saber quien y cuando se hizo dicho cambio.

### ¿Por qué es importante un control de versiones ###

+ Rendimiento: solamente guarde lo necesario.

+ Seguridad: conserva toda accion.

+ Flexibilidad: no necesita contar con un desarrollo lineal.

## 📁 Configuración Inicial ##

Esta sección es fundamental porque configura la identidad del usuario en Git, lo cual es necesario para que cada commit que se haga quede correctamente registrado como propiedad de uno.

```bash
git config --global user.name "Alejandro (en mi caso)"
```
Esto le dice a Git que tu nombre como autor de los commits será Alejandro (en mi caso). Aparecerá en el historial de cambios junto a cada commit que hagas.

```bash
git config --global user.email "tu_correo@example.com"
```
Esto configura el correo electrónico que se asociará a tus commits. Git lo usa como un identificador único, y también es importante si se usa en plataformas como GitHub, que enlazan tu correo con tu cuenta.

## 📂 Comandos Básicos ##

```git init```
: Inicializa un repositorio

```git add .```
: Añade archivos al área de staging

```git commit -m "mensaje"```
: Guarda los cambios en el historial

```git status```
: Verifica el estado de los archivos

```git log```
: Muestra el historial de commits

![Comandos_Git](img/comandos_git.jpg)

## 🧭 Ramas (Branches) ##

Crear una rama: ```git branch nombre_rama```

Cambiar de rama: ```git checkout nombre_rama``` o ```git switch nombre_rama```

Crear y cambiar: ```git checkout -b nueva_rama```

Eliminar una rama: ```git branch -d nombre_rama```

![Commit_apuntando_a_una_Rama](img/commit.png)

