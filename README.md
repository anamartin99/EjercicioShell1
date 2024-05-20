𝑽𝒂𝒓𝒊𝒂𝒃𝒍𝒆𝒔 ⤵

⸺ Ejercicio 1:

#!/bin/bash: Indica que el script debe ser ejecutado con Bash.

nombre="Ana Maria", edad="25", ciudad="Huelva": estos son tres variables que da nombre a algo (nombre, edad, ciudad) y se les asignan valores.

echo "Mi nombre es $nombre, tengo $edad años y vivo en $ciudad": esto imprime un mensaje que incluye los valores de las variables utilizando la sintaxis $variable con este signo "$".

⸺ Ejercicio 2:

echo "Ingresa tu actividad favorita:": esto muestra un mensaje solicitando al usuario que ingrese su actividad favorita.

read actividad: esto lee la entrada del usuario y lo almacena en la variable actividad.

echo "Ingresa tu comida favorita:": esto muestra un mensaje solicitando al usuario que ingrese su comida favorita.

read comida: esto lee la entrada del usuario y lo almacena en la variable comida.

echo "Mi actividad favorita es $actividad. Mi comida favorita es $comida": esto imprime un mensaje que incluye las entradas del usuario para que se pueda efectuar correctamente.

𝑷𝒂𝒓𝒂𝒎𝒆́𝒕𝒓𝒐𝒔 ⤵

⸺ Ejercicio 1:

Estas líneas verifican si el número de parámetros pasados al script es menor que 3.

if " $ # -lt 3 "; then: esto comprueba si la cantidad de argumentos ($#) es menor que 3 (-lt 3). 

echo "Incorrecto , Es necesario realizar 3 parámetros": esto es si la condición es verdadera, se imprime el mensaje de error "Incorrecto, Es necesario realizar 3 parámetros". 

exit 1: El script termina con un código de salida 1, indicando un error.

⸺ Ejercicio 2:

function parametros(): esto declara una función llamada parámetros.

fichero="carpeta personal": esto declara una variable local del fichero dentro de la función y le asigna el valor "carpeta personal".

echo "En el fichero 
# "parámetros": esto utiliza el comando echo para imprimir un mensaje. "$fichero" se expande a "carpeta personal" y "$#" se expande al número de argumentos que se pasan a la función parámetros.

parámetros 1 2 3 4 5: esto llama a la función parámetros con cinco argumentos (1 2 3 4 5).

$(...): esto captura la salida de la función parámetros y la asigna a la variable texto.

// echo "$texto" Este comando imprime el contenido de la variable texto en la terminal.

𝑪𝒐𝒏𝒅𝒊𝒄𝒊𝒐𝒏𝒂𝒍𝒆𝒔 ⤵

⸺ Ejercicio 1:

if [ "$(whoami)" != "root" ]; then: esto verifica si el usuario que ejecuta el script no es root.

$(whoami): ejecuta el comando whoami que retorna el nombre del usuario actual.

echo "No tiene acceso como root": esto imprime un mensaje de error si el usuario no es root.

fi: esto hace finalizar la estructura condicional if.

⸺ Ejercicio 2:

echo "Ingrese el primer número:" y read n1: esto solicita al usuario que ingrese el primer número y lo almacena en n1.

echo "Ingrese el segundo número:" y read n2: esto solicita al usuario que ingrese el segundo número y lo almacena en n2.

if "[ "$n1" -eq "$n2" ]"; then: esto verifica si n1 es igual a n2. 

elif [ "$n1" -gt "$n2" ]; then: esto verifica si n1 es mayor que n2. 

else: esto hace lo contrario, n2 es mayor que n1. 

fi: esto hace finalizar la estructura condicional if.

⸺ Ejercicio 3:

echo "Ingrese un número:" y read numero: esto solicita al usuario que ingrese un número y lo almacena en número.

if [ $((numero % 2)) -eq 0 ]; then: esto verifica si (número) es divisible por 2 usando la operación del módulo %.

else: si no es divisible por 2, ejecuta esta sección. 

fi: esto hace finalizar la estructura condicional if.

𝑺𝒖𝒔𝒕𝒊𝒕𝒖𝒄𝒊𝒐́𝒏 𝒅𝒆 𝒄𝒐𝒎𝒂𝒏𝒅𝒐𝒔 ⤵

⸺ Ejercicio 1:

echo "Ingrese su fecha de nacimiento (YYYY-MM-DD):": esto solicita al usuario que ingrese su fecha de nacimiento y la almacena en fecha_nacimiento.

fecha_actual=$(date +"%Y-%m-%d"): esto obtiene la fecha actual en el formato YYYY-MM-DD y la almacena en fecha_actual.

edad=$(echo $((($(date -d 
(date -d $fecha_nacimiento +%s)) / 31536000))): esto calcula la edad en años.

echo "Tienes $edad años.": esto imprime la edad del usuario.

𝑩𝒖𝒄𝒍𝒆𝒔 ⤵

⸺ Ejercicio 1:

La "shebang" indica que el script debe ejecutarse utilizando el intérprete de bash.

pid_script=$$: esto asigna el PID del proceso actual del script a la variable pid_script. El $$ es una variable especial en bash que contiene el PID del proceso actual.

intentos=0: esto inicializa la variable intentos a 0, se utilizará para contar cuántos intentos ha hecho el usuario.

echo "Adivina el PID del script:": esto muestra un mensaje pidiendo al usuario que adivine el PID.

read intento: esto lee la entrada del usuario y la guarda en la variable intento.

intentos=$((intentos + 1)): esto incrementa la cuenta de intentos en 1.

while [ "$intento" != "$pid_script" ]; do: esto inicia un bucle while que continuará ejecutándose mientras el valor de intento no sea igual al valor de pid_script.

if [ "$intento" -gt "$pid_script" ]; then: esto verifica si el intento del usuario es mayor que el PID del script.

echo "El PID ingresado es mayor": esto si el intento es mayor, se muestra este mensaje.

else: si el intento no es mayor (es menor o igual); echo "El PID ingresado es menor": esto muestra este mensaje si el intento es menor.

fi: esto hace terminar la estructura if.

echo "Intenta de nuevo:": esto pide al usuario que intente de nuevo. 

read intento: esto lee el nuevo intento del usuario.

intentos=$((intentos + 1)): esto incrementa la cuenta de intentos en 1.

done: esto termina el bucle while. Y si el usuario adivina correctamente, el bucle se rompe y el script continúa.

echo "¡Felicidades! Has adivinado el PID del script: $pid_script": esto felicita al usuario por haber adivinado correctamente e imprime el PID.

echo "Número de intentos: $intentos": esto muestra el número de intentos que hizo el usuario.

⸺ Ejercicio 2:

echo "Ingrese el nombre del archivo a agregar:" y read nombre_archivo: esto solicita al usuario que ingrese el nombre de un archivo a crear.

touch "$nombre_archivo": esto crea un archivo vacío con el nombre proporcionado.

echo "Archivo '$nombre_archivo' creado.": esto informa al usuario que el archivo ha sido creado.

sleep 3: esto dice que hay que esperar 3 segundos.

echo "Lista de archivos actual:" y ls: esto muestra la lista actual de archivos en el directorio.

echo "¿Desea borrar un archivo? (Sí/No):" y read respuesta: esto pregunta al usuario si desea borrar un archivo.

if [ "$respuesta" = "Sí" ]; then: esto verifica si la respuesta es "Sí".

echo "Ingrese el nombre del archivo a borrar:" y read archivo_borrar: esto solicita el nombre del archivo a borrar.

echo "Ingrese el formato del archivo a borrar:" y read formato_borrar: esto solicita el formato del archivo a borrar.

if [ -f "$archivo_borrar.$formato_borrar" ]; then: esto verifica si el archivo existe.

rm "$archivo_borrar.$formato_borrar": esto borra el archivo.

else: Si el archivo no existe, informa al usuario.

echo "Ok, no borraremos ningún archivo.": esto informa que no se borrará ningún archivo si la respuesta es diferente a "Sí".
