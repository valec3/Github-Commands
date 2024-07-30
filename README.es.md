# Comandos de GitHub

## Configuración

| Comando                                             | Descripción                                                                             |
| --------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `git config --global user.name "John Doe"`          | Define el nombre del autor para todos los commits en el repositorio actual.             |
| `git config --global user.email example@gmail.com ` | Define el correo electrónico del autor para todos los commits en el repositorio actual. |
| `git config --global color.ui auto`                 | Habilita algo de colorización en la salida de Git.                                      |
| `git config --global core.editor code`              | Define el editor de texto utilizado por comandos como `git commit`.                     |
| `git config --global --list`                        | Lista todas las configuraciones.                                                        |

## Comandos Básicos

| Comando                           | Descripción                                                                    |
| --------------------------------- | ------------------------------------------------------------------------------ |
| `git init`                        | Inicializa un repositorio Git local.                                           |
| `git status`                      | Lista todos los archivos nuevos o modificados.                                 |
| `git diff`                        | Muestra las diferencias de los archivos que no han sido staged.                |
| `git add <file>`                  | Agrega un archivo al área de staging.                                          |
| `git diff --staged`               | Muestra las diferencias entre staging y la última versión del archivo.         |
| `git commit -m "mensaje"`         | Realiza un commit de los cambios.                                              |
| `git commit -a`                   | Realiza un commit de todos los archivos que han sido agregados con `git add`.  |
| `git clone <url>`                 | Clona un repositorio en un nuevo directorio.                                   |
| `git log`                         | Muestra los cambios realizados en el repositorio.                              |
| `git log --oneline`               | Muestra los cambios en una sola línea.                                         |
| `git log --graph --oneline --all` | Muestra los cambios en una sola línea con gráfico.                             |
| `git log --oneline --graph`       | Muestra los cambios en una sola línea con gráfico.                             |
| `git show <commit>`               | Muestra los cambios realizados en el commit especificado.                      |
| `git show`                        | Muestra los cambios realizados en el último commit.                            |
| `git show HEAD`                   | Muestra los cambios realizados en el último commit.                            |
| `git show HEAD~1`                 | Muestra los cambios realizados en el commit anterior al último.                |
| `git reset HEAD <file>`           | Remueve un archivo del área de staging.                                        |
| `git reset HEAD`                  | Remueve todos los archivos del área de staging.                                |
| `git checkout -- <file>`          | Descarta los cambios en el directorio de trabajo.                              |
| `git checkout <commit> -- <file>` | Descarta los cambios en el directorio de trabajo hasta el commit especificado. |
| `git reset --hard`                | Descarta todos los cambios en el directorio de trabajo.                        |

## Ramas

| Comando                             | Descripción                                                            |
| ----------------------------------- | ---------------------------------------------------------------------- |
| `git branch`                        | Lista todas las ramas en el repositorio.                               |
| `git branch <branch>`               | Crea una nueva rama.                                                   |
| `git checkout <branch>`             | Cambia a una rama.                                                     |
| `git checkout -b <branch>`          | Crea una nueva rama y cambia a ella.                                   |
| `git merge <branch>`                | Fusiona una rama en la rama activa.                                    |
| `git branch -d <branch>`            | Elimina una rama.                                                      |
| `git push`                          | Envía los cambios al repositorio remoto.                               |
| `git push origin --delete <branch>` | Elimina una rama en el repositorio remoto.                             |
| `git push origin <branch>`          | Envía la rama al repositorio remoto.                                   |
| `git pull`                          | Actualiza el repositorio local con los cambios del repositorio remoto. |
| `git pull origin <branch>`          | Actualiza el repositorio local con los cambios de la rama remota.      |
| `git fetch`                         | Descarga objetos y referencias de otro repositorio.                    |
| `git fetch origin`                  | Descarga objetos y referencias del repositorio remoto.                 |
| `git remote -v`                     | Lista todos los repositorios remotos.                                  |
| `git remote add <name> <url>`       | Agrega un nuevo repositorio remoto.                                    |
| `git remote remove <name>`          | Elimina un repositorio remoto.                                         |

## Etiquetas

| Comando         | Descripción                                  |
| --------------- | -------------------------------------------- |
| `git tag`       | Lista todas las etiquetas en el repositorio. |
| `git tag <tag>` | Crea una nueva etiqueta.                     |

## Stash

| Comando                   | Descripción                                       |
| ------------------------- | ------------------------------------------------- |
| `git stash`               | Guarda cambios en un directorio de trabajo sucio. |
| `git stash list`          | Lista todos los stashes.                          |
| `git stash apply`         | Aplica el último stash.                           |
| `git stash apply <stash>` | Aplica un stash específico.                       |
| `git stash drop`          | Elimina el último stash.                          |

## Rebase

| Comando                 | Descripción                                      |
| ----------------------- | ------------------------------------------------ |
| `git rebase <branch>`   | Rebasea la rama actual con la rama especificada. |
| `git rebase --continue` | Continúa el proceso de rebase.                   |
| `git rebase --abort`    | Aborta el proceso de rebase.                     |

## Gitignore

```bash
# Ignorar todos los archivos .a
*.a
# Pero rastrear lib.a, aunque estás ignorando archivos .a arriba
!lib.a
# Ignorar todos los archivos en el directorio build/
build/
# Ignorar doc/notes.txt, pero no doc/server/arch.txt
doc/*.txt
# Ignorar todos los archivos .pdf en el directorio doc/
doc/**/*.pdf

# etc...
```

## Recursos Adicionales

- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Git Handbook](https://guides.github.com/introduction/git-handbook/)
- [GeeksforGeeks - Git Commands](https://www.geeksforgeeks.org/useful-github-commands/)
