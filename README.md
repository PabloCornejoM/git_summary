# git_summary
git commands I use


# Git Workflow Guide - Lo Básico

## 1. Crear una Nueva Branch

```bash
# Crear y cambiar a la nueva branch en un solo comando
git checkout -b nombre-nueva-branch

# O hacerlo en dos pasos:
git branch nombre-nueva-branch    # Crear la branch
git checkout nombre-nueva-branch  # Cambiar a esa branch
```

## 2. Cambiar Entre Branches

```bash
# Ver todas las branches disponibles
git branch

# Cambiar a una branch existente
git checkout nombre-branch

# Cambiar a master/main
git checkout master
git checkout main
```

## 3. Crear Branch en Nueva Carpeta (Worktree)

```bash
# Desde tu directorio principal del proyecto
git worktree add ../nombre-carpeta nombre-branch

# Ejemplo:
git worktree add ../myproject-feature feature-branch
```

### Limpiar worktrees cuando termines:
```bash
# Eliminar la carpeta worktree
git worktree remove ../nombre-carpeta

# Eliminar la branch local
git branch -d nombre-branch

# Eliminar la branch del remoto
git push origin --delete nombre-branch
```

## 4. Añadir Cambios (git add)

```bash
# Añadir todos los archivos modificados
git add .

# Añadir archivo específico
git add nombre-archivo.txt

# Añadir múltiples archivos
git add archivo1.txt archivo2.py

# Ver qué archivos están staged
git status
```

## 5. Commit de Cambios

```bash
# Commit con mensaje
git commit -m "Descripción de los cambios"

# Commit más descriptivo
git commit -m "Fix: Solucionado error en checkpoint manager"

# Ver historial de commits
git log --oneline
```

## 6. Workflow Completo Típico

```bash
# 1. Crear nueva branch para una feature
git checkout -b nueva-feature

# 2. Hacer cambios en el código...
# 3. Añadir cambios
git add .

# 4. Commit
git commit -m "Implementada nueva feature"

# 5. Subir branch al remoto
git push origin nueva-feature

# 6. Después del merge, limpiar
git checkout master
git pull origin master  # Actualizar master
git branch -d nueva-feature  # Eliminar branch local
```

## 7. Comandos Útiles de Estado

```bash
# Ver estado actual
git status

# Ver diferencias antes de hacer commit
git diff

# Ver en qué branch estás
git branch

# Ver branches remotas también
git branch -a
```

## 8. Casos Especiales

### Si tienes cambios sin commit y quieres cambiar de branch:
```bash
# Guardar cambios temporalmente
git stash

# Cambiar de branch
git checkout otra-branch

# Volver y recuperar cambios
git checkout mi-branch-original
git stash pop
```

### Si necesitas forzar eliminación de branch:
```bash
# Eliminar branch aunque tenga cambios no mergeados
git branch -D nombre-branch
```

---

**Nota**: Este es el flujo básico que hemos usado hasta ahora. Siempre revisa con `git status` antes de hacer commits para asegurarte de que estás añadiendo los archivos correctos.
