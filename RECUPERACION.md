# RECUPERACION.md
 
## Error simulado
 
Se borro accidentalmente el archivo errores.sh con el comando rm
y se hizo commit de ese borrado, por lo que el archivo desapareció
del historial de la rama main.
 
## Comandos usados para recuperar el archivo
 
1. git reflog
   Muestra el historial completo de movimientos del HEAD,
   incluidos los commits que ya no están en la rama actual.
   Localizamos el hash del commit donde errores.sh aun existía.
 
2. git checkout <hash> -- errores.sh
   Recupera el archivo concreto de un commit anterior
   sin cambiar la rama ni el resto de archivos.
 
3. git add errores.sh && git commit
   Guardamos el archivo recuperado en un nuevo commit.
 
## Que aprendí
 
Git nunca borra información de verdad mientras el commit este
en el historial. Aunque hagamos un commit de un borrado, el
archivo sigue existiendo en commits anteriores y se puede
recuperar con git checkout o git reset.
El reflog es especialmente útil porque guarda incluso operaciones
que no están en la rama, como commits descartados o resets.
