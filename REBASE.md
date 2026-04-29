# REBASE.md
 
## Que es git rebase -i
 
git rebase -i (interactivo) permite reescribir el historial de commits.
Es útil para limpiar mensajes poco descriptivos o fusionar commits
pequeños que no aportan valor por separado antes de subir los cambios.
 
## Proceso seguido
 
### Fase 1: crear commits con mensajes malos
Se crearon tres commits con mensajes vagos (Arreglos, Cambios,
Actualización de cosas) para simular una situación real de trabajo
rápido donde no se cuidan los mensajes.
 
### Fase 2: rebase interactivo
Se ejecuto git rebase -i HEAD~3 para modificar los últimos 3 commits.
En el editor se usaron dos acciones:
- reword: para cambiar el mensaje de un commit sin modificar su contenido.
- squash: para fusionar commits con el anterior, combinando sus cambios
  en un solo commit con un mensaje nuevo.
 
### Fase 3: push --force
Como el historial local cambio fue necesario usar git push --force
para sobrescribir el historial remoto. Esta acción es destructiva
en repos compartidos, pero valida en ramas personales.
 
## Porque es importante limpiar el historial
 
Un historial limpio facilita la revisión del código, la búsqueda de
errores con git bisect y la colaboración en equipo. Mensajes como
Arreglos no aportan información útil sobre qué cambio ni por qué.
 
git add REBASE.md
git commit -m "añade REBASE.md explicando el proceso de rebase interactivo"
git push
