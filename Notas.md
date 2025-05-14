# 📌 Comandos Básicos y Fundamentales

## git config
Configura tu identidad y preferencias de Git.

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```
Usa `--global` para que aplique a todos tus repos.  
También puedes configurar el editor, colores, alias, etc.

---

## git init
Crea un nuevo repositorio Git en el directorio actual.

```bash
git init
```
Úsalo para empezar a usar Git en un proyecto local.

---

## git clone
Clona un repositorio remoto a tu máquina local.

```bash
git clone https://github.com/usuario/repositorio.git
```
Crea una copia completa del repositorio y su historial.

---

## git add
Agrega archivos al área de preparación (staging area).

```bash
git add archivo.txt
git add .   # agrega todos los archivos modificados
```
Prepara los archivos para ser guardados con `git commit`.

---

## git commit
Guarda los cambios del área de preparación al historial del proyecto.

```bash
git commit -m "Mensaje del commit"
```
Es como tomar una "foto" del estado del proyecto.

---

## git status
Muestra el estado del repositorio: qué está modificado, sin seguir, listo para commit, etc.

```bash
git status
```

---

## git log
Muestra el historial de commits.

```bash
git log
```

# 🌿 Ramas y Flujos

## git branch
Muestra las ramas existentes o crea una nueva.

```bash
git branch          # muestra ramas
git branch nueva-rama  # crea rama
```

---

## git checkout
Cambia de rama o revierte archivos.

```bash
git checkout main          # cambia a rama main
git checkout -b nueva      # crea y cambia a nueva rama
```

---

## git switch (moderno)
Mejor alternativa a checkout para cambiar de rama.

```bash
git switch main
git switch -c nueva
```

---

## git merge
Combina una rama con la actual.

```bash
git merge feature-1
```
Se usa para integrar cambios de otras ramas.

---

## git rebase
Reaplica commits de una rama sobre otra (reorganiza la historia).

```bash
git rebase main
```
Útil para limpiar el historial antes de integrar ramas.

---

## git cherry-pick
Aplica un commit específico de otra rama en la actual.

```bash
git cherry-pick abc1234
```
Ideal para traer un cambio puntual sin hacer merge.

---

## git reset
Deshace commits o saca archivos del staging.

```bash
git reset --soft HEAD~1    # deshace el último commit, mantiene cambios
git reset archivo.txt       # quita archivo del staging
```

---

## git stash
Guarda cambios sin hacer commit para trabajar en otra cosa.

```bash
git stash
git stash apply
```
Muy útil para guardar trabajo temporal sin hacer commit.

---

## git worktree
Permite trabajar con varias ramas al mismo tiempo en directorios distintos.

```bash
git worktree add ../otro-main main
```
Ideal para evitar cambiar de rama constantemente.

# 🌐 Remotos y Sincronización

## git remote
Muestra o gestiona conexiones a repositorios remotos.

```bash
git remote -v
git remote add origin https://github.com/user/repo.git
```

---

## git fetch
Descarga cambios del repositorio remoto sin mezclarlos.

```bash
git fetch origin
```

---

## git pull
Descarga y fusiona los cambios del remoto con tu rama actual.

```bash
git pull origin main
```

---

## git push
Sube tus commits al repositorio remoto.

```bash
git push origin main
```

# 🔖 Tags y Versionado

## git tag
Marca commits con nombres para indicar versiones.

```bash
git tag v1.0
git tag -a v1.0 -m "Versión estable"
git push origin --tags
```

# ⚙️ Flujos y Herramientas Especializadas

## git flow
Sistema de ramificación basado en convención: develop, feature/*, release/*, etc.

```bash
git flow init
git flow feature start nombre
git flow release finish 1.0
```
Automático pero rígido; puedes dejar de usarlo cuando desees.

---

## git lfs
Git Large File Storage: permite manejar archivos grandes.

```bash
git lfs install
git lfs track "*.psd"
```

---

## git diff
Muestra diferencias entre archivos o commits.

```bash
git diff
git diff main develop
```

---

## git patch
Aplica o crea parches de código (.patch files).

```bash
git format-patch HEAD~1
git apply archivo.patch
```

---

## git squash (no es un comando directo)
Combinar varios commits en uno usando rebase interactivo:

```bash
git rebase -i HEAD~3
# luego cambia "pick" por "squash" en los commits
```

---

## ❌ No Existe

### git download
No existe como comando oficial. Generalmente se refiere a clonar o hacer fetch / pull.

---

# 🧠 Otros Comandos Útiles

- `git clean -fd`: borra archivos no rastreados.
- `git reflog`: historial de movimientos del HEAD, útil para recuperar cambios.

---

# ✅ Flujo de Trabajo Recomendado

```bash
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
```