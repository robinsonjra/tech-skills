# Git
[<img src="asset/git.svg" width="150"/>](asset/git.svg)

## ¿Qué es Git?
Git es un sistema de control de versiones distribuido (DVCS) que varios desarrolladores y otros colaboradores pueden usar para trabajar en un proyecto. Proporciona una manera de trabajar con una o varias ramas locales y luego insertarlas en un repositorio remoto.

> #### ¿Qué es el control de versiones?
> 
> Un sistema de control de versiones **(VCS)** es un programa o conjunto de programas que realiza un seguimiento de los cambios en una colección de archivos. Uno de los objetivos es recuperar fácilmente versiones anteriores de archivos individuales o de todo el proyecto. Otro objetivo es permitir que varios miembros de un equipo trabajen en un proyecto, incluso en los mismos archivos, al mismo tiempo sin que eso afecte al trabajo de los demás.

> #### ¿Qué es el control de versiones distribuido?
>
> Git es un sistema distribuido, lo que significa que el historial completo de un proyecto se almacena en el cliente y en el servidor. Se pueden editar archivos sin conexión de red, protegerlos localmente y sincronizarlos con el servidor cuando una conexión esté disponible. Si un servidor deja de funcionar, todavía tendrá una copia local del proyecto. Técnicamente, ni siquiera es necesario tener un servidor.

> #### ¿Qué es GitHub?
> GitHub es una plataforma en la nube que usa Git como tecnología principal. Simplifica el proceso de colaboración en proyectos y proporciona un sitio web, más herramientas de línea de comandos y un flujo integral que los desarrolladores y usuarios pueden usar para trabajar juntos.


## GIT Cheatsheet
> Comando para saber la versión instalada de Git. ```git --version```

### > Configuración
Para configurar Git, debe definir algunas variables globales: **user.name** y **user.email**. Ambas son necesarias para realizar confirmaciones.

| COMANDOS | DESCRIPCION |
| --- | --- |
| ```git config --global user.name "<user_name>"``` | Reemplace **<user_name>** por el nombre de usuario que quiere usar. |
| ```git config --global user.email "<user_email>"``` | Reemplace **<user_email>** por la dirección de correo electrónico que quiere usar. |
| ```git config --list``` | Ejecute el siguiente comando para comprobar que los cambios han funcionado. |
| ```git config --global color.ui auto``` | (Opcional), si desea establecer un color automático en la línea de comandos para facilitar la revisión, ejecute el siguiente comando, reemplace **auto** por el color que quiere usar (Ejm: Red, blue, etc). |


### > Git Init o Git Clone
Empiece por crear una carpeta vacía para el proyecto.

| COMANDOS | DESCRIPCION |
| --- | --- |
| ```git init -b main``` | Inicializa el nuevo repositorio y establece el nombre de la rama predeterminada en main. |
| ```git clone [url-repositorio]``` | Clona un repositorio completo desde una ubicación alojada mediante URL.|


### > GitIgnore
El archivo .gitignore se usa para indicarle explícitamente a Git que debe ignorar.
Crear un archivo con los paterns deseados como **.gitignore** ya sea con coincidencias directas de cadena o comodines.

> Para que todos los repositorios locales ignoren un paterns puede usar el siguiente comando (reemplace [file]):
> 
> ```git config --global core.excludesfile [file]```


### > Comandos básicos de Git
Git recuerda los cambios efectuados en los archivos como si tomara instantáneas del sistema de archivos.

| COMANDOS | DESCRIPCION |
| --- | --- |
| ```git status``` | Muestra los archivos modificados en el directorio de trabajo, listos para la siguiente confirmación.|
| ```git add [file]``` | Añade un archivo tal y como se ve ahora a tu próxima confirmación (stage).|
| ```git commit -m "[message]"``` | Confirma el contenido preparado como una nueva instantánea de confirmación.|
| ```git branch``` | Lista tus ramas. aparecerá un * junto a la rama actualmente activa.|
| ```git branch [branch-name]``` | Crea una nueva rama con el commit actual.|
| ```git checkout [branch-name]``` | Cambia a otra rama y la comprueba en tu directorio de trabajo.|
| ```git merge [branch-name]``` | Fusiona el historial de la rama especificada en la actual.|


### > Buenas prácticas para un mensaje en el Commit

| CASO | EJEMPLO |
| --- | --- |
| Primer Commit (Inicializando el repositorio) | Initial commit: establecer la estructura del proyecto |
| Agregar nueva funcionalidad | Feat: agregar endpoint para obtener detalles del usuario |
| Modificar una funcionalidad | Change: lógica de restablecimiento de contraseña para utilizar la verificación de correo electrónico |
| Mejorar el rendimiento | Perf: optimizar consulta SQL para mejorar el tiempo de respuesta |
| Refactorizar código | Refactor: reorganizar funciones de validación en un módulo separado |
| Corregir un error | Fix: corregir error en el cálculo del total en el carrito de compras |
| Eliminar código no utilizado | Remove: funciones no utilizadas |
| Documentación | Docs: actualizar guía de configuración para nuevos desarrolladores | 


### > Instantánea y Diferencial
Trabajar con instantáneas y el área de preparación de Git.

| COMANDOS | DESCRIPCION |
| --- | --- |
| ```git reset [file]``` | Desescalar un archivo manteniendo los cambios en el directorio de trabajo.|
| ```git diff``` | Diferencial de lo que ha cambiado pero no está preparado.|
| ```git diff --staged``` | Diferencial de lo que está preparado pero aún no confirmado.|


### > Confirmaciones Temporales
Almacenar temporalmente los archivos modificados y rastreados para cambiar de rama.

| COMANDOS | DESCRIPCION |
| --- | --- |
| ```git stash save "my_stash_name"``` | Guardar cambios modificados y puestos en escena.|
| ```git stash list``` | Lista el orden de los cambios en los archivos almacenados.|
| ```git stash show -p``` | Puede ver un resumen de un stash.|
| ```git stash pop stash@{n}``` | Elimina los cambios de tu stash y los vuelve a aplicar a tu copia de trabajo.|
| ```git stash apply stash@{n}``` | Alternativamente, puedes volver a aplicar los cambios a tu copia de trabajo y mantenerlos.|
| ```git stash drop stash@{n}``` | Descartar los cambios de la parte superior de la pila stash.|
| ```git stash clear``` | Puedes borrar todos tus stash.|


### > Inspeccionar y Comparar
Examinar logs, diffs e información sobre objetos.

| COMANDOS | DESCRIPCION |
| --- | --- |
| ```git log``` | Muestra todos los commits del historial de la rama actual.|
| ```git log branchB..branchA``` | Muestra los commits de la ramaA que no están en la ramaB.|
| ```git log --follow [file]``` | Muestra las confirmaciones que cambiaron el archivo, incluso a través de renombramientos.|
| ```git diff branchB...branchA``` | Muestra el diff de lo que hay en la ramaA que no está en la ramaB.|
| ```git show [SHA]``` | Muestra cualquier objeto en Git en formato legible por humanos.|


### > Repositorios en la Nube
Recuperación de actualizaciones de otro repositorio y actualización de los repos locales.

| COMANDOS | DESCRIPCION |
| --- | --- |
| ```git remote add [alias] [url]``` | Añade una URL git como alias.|
| ```git fetch [alias]``` | Obtiene todas las ramas de ese Git remoto.|
| ```git merge [alias]/[rama]``` | Fusiona una rama remota en tu rama actual para actualizarla.|
| ```git push [alias] [rama]``` | Transmite los commits de la rama local a la rama remota del repositorio.|
| ```git pull``` | Obtener y fusionar cualquier confirmación de la rama remota de seguimiento.|


### > Seguimientos de Cambios
Versionado de archivos eliminados y cambios de ruta.

| COMANDOS | DESCRIPCION |
| --- | --- |
| ```git rm [file]``` | Borra el archivo del proyecto y prepara la eliminación para el commit.|
| ```git mv [existing-path] [new-path]``` | Cambia la ruta de un archivo existente y prepara el movimiento.|
| ```git log --stat -M``` | Muestra todos los registros de confirmación con indicación de las rutas que se han movido.|


### > Reescribir el Historial
Reescritura de ramas, actualización de commits y borrado del historial.

| COMANDOS | DESCRIPCION |
| --- | --- |
| ```git rebase [branch]``` | Aplica cualquier confirmación de la rama actual por delante de la especificada.|
| ```git reset --hard [commit]``` | Limpia el área de preparación, reescribe el árbol de trabajo desde la confirmación especificada.|