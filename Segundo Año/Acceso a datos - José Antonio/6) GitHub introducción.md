

No todos los IDE tiene conexión directa con GitHub pero con eclipse si lo vamos a hacer a través del IDE.

Pasos para iniciar un nuevo repositorio(proyecto en GitHub):

- Seleccionar propietario.
- Ponerle nombre que sea el nombre de mi proyecto en IDE.
- Inicialmente esta bien tenerlo en privado.
- en Add.gitignore puedes definir que archivos que no te interese subir no se suban, también se puede hacer desde eclipse.
- Se puede escoger una licencia pero no es necesario actualmente.

Algunos comandos de GitHub: 

### …or create a new repository on the command line

echo "# timmy" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/rodal90/timmy.git
git push -u origin main

### …or push an existing repository from the command line

git remote add origin https://github.com/rodal90/timmy.git
git branch -M main
git push -u origin main


***Manejamos repositorio en local y también en la nube. 

***A través de la dirección que se encuentra en tu página principal se puede conectar nuestro repositorio local al de la nube. https://github.com/rodal90/timmy.git

**El siguiente paso se hace para crear el repositorio local: **

En el nombre del proyecto en Eclipse, con click derecho buscamos "Team" y luego share. Al llegar marcamos el primer checkbox, y luego "Create Repository" y finalizamos.

La forma en la que se desarrolla es en ramas, la rama Master es la principal y las otras ramas pueden trabajarse de forma individualizada, se recomienda crear una nueva rama para dejar lo que ya funciona sin tocar, e incluso también se puede retroceder en el proceso de la rama.

En teams, add to index agrega al repositorio local los archivos que hemos modificado, desde la ultima vez que se subió el repositorio o que son nuevos. 

Luego otra vez en Teams, le das en "commit", y ves todos los ficheros que han sido modificados desde la última vez que se subieron al repositorio.  Con el símbolo de menos menos rojo se puede sacar ficheros individuales. 

Del lado derecho, tenemos el commit message, que es con el cual podemos escribir un breve comentario para tener registro de cambios o tener separación entre una versión u otra.

**El siguiente paso se hace solo una vez para enlazar: **

Al darle commit and push te hará el commit en local pero no podrás hacerlo en la nube, luego le das  Push otra vez y te da la opción para vincular con la nube. Aquí es donde ponemos la dirección que copiamos de GitHub. En el espacio de URI:  https://github.com/rodal90/timmy.git

Para comprobar que eres tu el que esta intentando hacer la conexión te pide tu usuario y contraseña de Github. Esto no es suficiente_ Hay que crear un personal token en cada equipo con el cual queramos hacer la conexión entre IDE y GitHub.

![[Pasted image 20241003110806.png]]

**OAuth apps: Verificarse a través de terceros, como Google etc.


Para crear un token personal en GitHub:
Primero te vas a tu perfil del lado derecho y luego de entrar te vas hasta a abajo a 
"Developer Settings", luego vas a ver la opción de Personal access tokens. Seleccionamos el clásico
y luego creamos una clásica, en notas ponemos el lugar del cual estamos accediendo y seleccionamos la cantidad de tiempo que queremos que el token este vigente, luego seleccionamos los permisos.

Este es tu token del Core:

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

Este es tu token de Casa:


Cuando terminas usar en password to token con tu correo. Y luego darle push. 

Cuando hagas una modificación y luego guardes, asi te muestra que no has hecho los cambios en la nube: 

![[Pasted image 20241003112602.png]]
con el mayor >.

cuando hacemos otra modificación en otro archivo, guardamos otra vez y nos va aparecer en la ventana de unstaged changes todos los archivos que hemos modificado pero que todavía no hemos guardado en local.  le damos a los símbolos de más para pasarlos a la parte de abajo y luego commit and push para actualizarlo en local y en el repositorio en la nube.

*Cuando se hace un cambio en tu archivo, luego en GitHub se puede ver cual ha sido la modificación haciendo click en el comentario que hemos puesto con los detalles de modificación*

**COMO SE RECUPERA UN RESPOSITORIO QUE NO ES MIO: 

Primero aceptar invitación de colaboración en proyecto

Luego meterse al proyecto y copiar la dirección https. Se llama clonar.

Luego le damos en Eclipse a la vista de Git que esta en la esquina superior  derecha, y luego al botón:   ![[Pasted image 20241003120456.png]]

Al darle al botón nos da la opción de agregar la dirección https la agregamos y luego seleccionamos con que rama queremos trabajar, luego el directorio que normalmente se recomienda usar el directorio de nuestro espacio de trabajo en este caso el workspace nuestro.

![[Pasted image 20241003120959.png]]


Luego de terminar esto, click derecho en vista de Git al proyecto y  hay que importar el proyecto que descargamos de Git para poder empezar a trabajar.


como descargar actualizaciones que se han hecho en el proyecto conjunto. Se baja dándole click derecho al proyecto, Teams y luego en vez de push, hacer click en "pull" y te sale esto:

![[Pasted image 20241003121636.png]]


Como se puede ver te muestra que commit es y cuando.

Para ver si tenes la ultima versión del proyecto podes utilizar esta opción que compara tu repositorio local con el que esta en la nube: 

![[Pasted image 20241003121838.png]]


---
