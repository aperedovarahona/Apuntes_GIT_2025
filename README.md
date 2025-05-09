# Apuntes_GIT_2025

## 🧠 Contenido

+ 📌 Introducción a Git

+ 📁 Configuración Inicial

+ 📂 Comandos Básicos

+ 🧭 Ramas (Branches)

+ 🔁 Merge y Rebase

+ 🌐 GitHub y Repos Remotos

+ 🛠️ Buenas Prácticas

## 📌 Introducción a Git

![Git_Logo](img/git_logo.png)

Git es un sistema de control de versiones distribuido, creado por Linus Torvalds en 2005. Permite registrar y controlar cambios en archivos de forma eficiente y colaborativa.

### ¿Que es un control de versiones?

+ Es un sistemas que registra cada cambio que se realiza dentro del codigo fuente de un proyecto.

+ Permite tener un historial de todos lo cambio producidos, ademas de saber quien y cuando se hizo dicho cambio.

### ¿Por qué es importante un control de versiones

+ Rendimiento: solamente guarde lo necesario.

+ Seguridad: conserva toda accion.

+ Flexibilidad: no necesita contar con un desarrollo lineal.

## 📁 Configuración Inicial

Esta sección es fundamental porque configura la identidad del usuario en Git, lo cual es necesario para que cada commit que se haga quede correctamente registrado como propiedad de uno.

```bash
git config --global user.name "Alejandro (en mi caso)"
```

Esto le dice a Git que tu nombre como autor de los commits será Alejandro (en mi caso). Aparecerá en el historial de cambios junto a cada commit que hagas.

```bash
git config --global user.email "tu_correo@example.com"
```

Esto configura el correo electrónico que se asociará a tus commits. Git lo usa como un identificador único, y también es importante si se usa en plataformas como GitHub, que enlazan tu correo con tu cuenta.

## 📂 Comandos Básicos

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

## 🧭 Ramas (Branches)

### ¿Qué es un rama?

+ Una rama (branch) en Git es un puntero móvil a uno de los commits del historial. Cuando se crea una rama, el puntero se coloca en el commit actual, posteriormente se puede continuar trabajando y creando nuevos commits.

+ Las ramas son útiles para desarrollar funcionalidades o arreglar bugs sin afectar el código principal (rama "master" o "main").

+ Al crear una rama, puedes realizar cambios en un entorno aislado y, si los resultados son satisfactorios, fusionar (merge) la rama en la rama principal.

![Ramas_en_Git](img/ramas.png)

### Comandos basicos para Ramas en Git

Crear una rama: ```git branch nombre_rama```

Cambiar de rama: ```git checkout nombre_rama``` o ```git switch nombre_rama```

Crear y cambiar: ```git checkout -b nueva_rama```

Eliminar una rama: ```git branch -d nombre_rama```

![Commit_apuntando_a_una_Rama](img/commit.png)

## 🔁 Merge y Rebase

### 🔀 ```git merge nombre_rama```

Este comando toma los cambios de otra rama (rama) y los fusiona con la rama actual.

```bash
git checkout main
git merge rama-de-caracteristica
```

Git crea un commit de merge si hay cambios en ambas ramas.

Es ideal para mantener el historial explícito y ramificado.

### 🧱 ```git rebase nombre_rama```

Este comando reaplica los commits de la rama actual sobre la base de otra rama. El historial queda más lineal.

```bash
git checkout rama-de-caracteristica
git rebase main
```

No crea un commit de merge.

Es ideal para mantener un historial limpio y ordenado.

+ Precaución: No es recomendable hacer rebase de ramas que ya fueron compartidas con otras peersonas (porque reescribe el historial).

![Merge_de_Ramas](img/merge.png)

### ⚠️ Conflictos

Cuando Git no puede fusionar automáticamente los cambios (por ejemplo, si dos ramas modifican la misma línea de un archivo), se produce un conflicto.

#### ❓ ¿Cómo identificar un conflicto?

Después de un merge o rebase, Git te dirá algo como:

```bash
CONFLICT (content): Merge conflict in archivo.txt
Automatic merge failed; fix conflicts and then commit the result.
```

Y si haces git status, verás:

```bash
Copiar
Editar
both modified: archivo.txt
```

### 🛠️ ¿Cómo resolver conflictos?

#### 1. Abrir el archivo con conflicto

Git marcará las zonas en conflicto así:

```diff
Versión en tu rama actual (por ejemplo, `main`)
Versión en la rama que estás integrando (por ejemplo, `rama-de-caracteristica`)
```

#### 2. Editar el archivo

Debes decidir qué versión conservar, o combinar ambas. Luego borra los marcadores ```<<<<<<<```, ```=======```, ```>>>>>>>```.

Ejemplo resuelto:

```Versión combinada o elegida por ti
```

#### 3. Marcar el conflicto como resuelto

```bash
git add archivo.txt
```

Esto le indica a Git que ya resolviste el conflicto en ese archivo.

#### 4. Finalizar el proceso

Si estabas haciendo merge:

```bash
git commit
```

Si estabas haciendo rebase:

```bash
git rebase --continue
```

### 💡 Consejos para evitar conflictos

Comunícate con tu equipo antes de hacer cambios grandes.

Sincroniza tu rama frecuentemente con git pull.

Usa ramas pequeñas y con un propósito claro.

Antes de hacer merge, asegúrate de tener la última versión de la rama destino:

```bash
git checkout main
git pull origin main
```
