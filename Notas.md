📌 COMANDOS BÁSICOS Y FUNDAMENTALES
🔹 git config
Configura tu identidad y preferencias de Git.

Uso común:

bash
Copiar
Editar
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
Usa --global para que aplique a todos tus repos.

También puedes configurar el editor, colores, alias, etc.

🔹 git init
Crea un nuevo repositorio Git en el directorio actual.

bash
Copiar
Editar
git init
Úsalo para empezar a usar Git en un proyecto local.

🔹 git clone
Clona un repositorio remoto a tu máquina local.

bash
Copiar
Editar
git clone https://github.com/usuario/repositorio.git
Crea una copia completa del repositorio y su historial.

🔹 git add
Agrega archivos al área de preparación (staging area).

bash
Copiar
Editar
git add archivo.txt
git add .   # agrega todos los archivos modificados
Prepara los archivos para ser guardados con git commit.

🔹 git commit
Guarda los cambios del área de preparación al historial del proyecto.

bash
Copiar
Editar
git commit -m "Mensaje del commit"
Es como tomar una "foto" del estado del proyecto.

🔹 git status
Muestra el estado del repositorio: qué está modificado, sin seguir, listo para commit, etc.

bash
Copiar
Editar
git status
🔹 git log
Muestra el historial de commits.

bash
Copiar
Editar
git log
🌿 RAMAS Y FLUJOS
🔹 git branch
Muestra las ramas existentes o crea una nueva.

bash
Copiar
Editar
git branch          # muestra ramas
git branch nueva-rama  # crea rama
🔹 git checkout
Cambia de rama o revierte archivos.

bash
Copiar
Editar
git checkout main          # cambia a rama main
git checkout -b nueva      # crea y cambia a nueva rama
🔹 git switch (moderno)
Mejor alternativa a checkout para cambiar de rama.

bash
Copiar
Editar
git switch main
git switch -c nueva
🔹 git merge
Combina una rama con la actual.

bash
Copiar
Editar
git merge feature-1
Se usa para integrar cambios de otras ramas.

🔹 git rebase
Reaplica commits de una rama sobre otra (reorganiza la historia).

bash
Copiar
Editar
git rebase main
Útil para limpiar el historial antes de integrar ramas.

🔹 git cherry-pick
Aplica un commit específico de otra rama en la actual.

bash
Copiar
Editar
git cherry-pick abc1234
Ideal para traer un cambio puntual sin hacer merge.

🔹 git reset
Deshace commits o saca archivos del staging.

bash
Copiar
Editar
git reset --soft HEAD~1    # deshace el último commit, mantiene cambios
git reset archivo.txt       # quita archivo del staging
🔹 git stash
Guarda cambios sin hacer commit para trabajar en otra cosa.

bash
Copiar
Editar
git stash
git stash apply
Muy útil para guardar trabajo temporal sin hacer commit.

🔹 git worktree
Permite trabajar con varias ramas al mismo tiempo en directorios distintos.

bash
Copiar
Editar
git worktree add ../otro-main main
Ideal para evitar cambiar de rama constantemente.

🌐 REMOTOS Y SINCRONIZACIÓN
🔹 git remote
Muestra o gestiona conexiones a repositorios remotos.

bash
Copiar
Editar
git remote -v
git remote add origin https://github.com/user/repo.git
🔹 git fetch
Descarga cambios del repositorio remoto sin mezclarlos.

bash
Copiar
Editar
git fetch origin
🔹 git pull
Descarga y fusiona los cambios del remoto con tu rama actual.

bash
Copiar
Editar
git pull origin main
🔹 git push
Sube tus commits al repositorio remoto.

bash
Copiar
Editar
git push origin main
🔖 TAGS Y VERSIONADO
🔹 git tag
Marca commits con nombres para indicar versiones.

bash
Copiar
Editar
git tag v1.0
git tag -a v1.0 -m "Versión estable"
git push origin --tags
⚙️ FLUJOS Y HERRAMIENTAS ESPECIALIZADAS
🔹 git flow
Sistema de ramificación basado en convención: develop, feature/*, release/*, etc.

bash
Copiar
Editar
git flow init
git flow feature start nombre
git flow release finish 1.0
Automático pero rígido; puedes dejar de usarlo cuando desees.

🔹 git lfs
Git Large File Storage: permite manejar archivos grandes.

bash
Copiar
Editar
git lfs install
git lfs track "*.psd"
🔹 git diff
Muestra diferencias entre archivos o commits.

bash
Copiar
Editar
git diff
git diff main develop
🔹 git patch
Aplica o crea parches de código (.patch files).

bash
Copiar
Editar
git format-patch HEAD~1
git apply archivo.patch
🔹 git squash (no es un comando directo)
Combinar varios commits en uno usando rebase interactivo:

bash
Copiar
Editar
git rebase -i HEAD~3
# luego cambia "pick" por "squash" en los commits
❌ NO EXISTE
🔸 git download
No existe como comando oficial. Generalmente se refiere a clonar o hacer fetch / pull.

🧠 OTROS COMANDOS ÚTILES (adicionales)
git clean -fd: borra archivos no rastreados.

git reflog: historial de movimientos del HEAD, útil para recuperar cambios.

✅ FLUJO DE TRABAJO RECOMENDADO
bash
Copiar
Editar
# 1. Inicializas o clonas
git init / git clone

# 2. Trabajas con ramas
git checkout -b feature-x

# 3. Haces cambios
git add .
git commit -m "algo"

# 4. Combinas cambios
git checkout main
git merge feature-x

# 5. Subes cambios
git push origin main