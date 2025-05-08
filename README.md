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

