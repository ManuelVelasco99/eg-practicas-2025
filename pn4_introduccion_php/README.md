## Práctica N4 Introducción a PHP

### Sección 1 PHP: variables, tipos, operadores, expresiones, estructuras de control

### 1.1) En el siguiente código identificar:

- Las variables y su tipo
- Los operadores
- Las funciones y sus parámetros
- Las estructuras de control
- Cuál es la salida por pantalla

```php
<?php
function doble($i) {
 return $i*2;
}
$a = TRUE;
$b = "xyz";
$c = 'xyz';
$d = 12;
echo gettype($a);
echo gettype($b);
echo gettype($c);
echo gettype($d);
if (is_int($d)) {
 $d += 4;
}
if (is_string($a)) {
 echo "Cadena: $a";
}
$d = $a ? ++$d : $d*3;
$f = doble($d++);
$g = $f += 10;
echo $a, $b, $c, $d, $f , $g;
?>
```

#### Variables:

```php
$a;//boolean
$b;//string
$c;//string
$d;//integer
$f;//integer
$g;//integer
```

#### Operadores:

```php
//Aritméticos:
*, +=, ++

//Asignación:
=

//Lógicos/Ternario
? :
```

#### Funciones y sus parámetros:

```php
//Funcion:
doble($i)
//Parámetros:
$i
//Descripción:
//Devuelve el doble del valor recibido

//Funcion:
gettype($x)
//Parámetros:
$x
//Descripción:
//Devuelve el tipo de variable

//Funcion:
is_int($d)
//Parámetros:
$d
//Descripción:
//Verifica si $d es entero

//Funcion:
is_string($a)
//Parámetros:
$a
//Descripción:
//Verifica si $a es cadena
```

#### Estructuras de control

```php
<?php
//...
if (is_int($d)) { // Condicional if
 $d += 4;         // Se cumple, porque $d es entero (12)
}
if (is_string($a)) { // Condicional if
 echo "Cadena: $a";  // No se cumple, $a es boolean
}
$d = $a ? ++$d : $d*3; // Ternario Como $a es TRUE, se ejecuta ++$d
//...
?>
```

#### Salida en pantalla final:

```
booleanstringstringinteger1xyzxyz184444
```

### 1.2) Indicar si los siguientes códigos son equivalentes:

#### 1.2.a)
```php
<?php
$i = 1;
while ($i <= 10) {
 print $i++;
}
?>
```
```php
<?php
$i = 1;
while ($i <= 10):
 print $i;
 $i++;
endwhile;
?>
```
```php
<?php
$i = 0;
do {
 print ++$i;
} while ($i<10);
?>
```

#### 1.2.b)
```php
<?php
for ($i = 1; $i <= 10; $i++) {
 print $i;
}
?>
```
```php
<?php
for ($i = 1; $i <= 10; print $i, $i++) ;
?>
```
```php
<?php
for ($i = 1; ;$i++) {
 if ($i > 10) {
 break;
 }
 print $i;
}
?>
```
```php
<?php
$i = 1;
for (;;) {
 if ($i > 10) {
 break;
 }
 print $i;
 $i++;
}
?>
```
#### 1.2.c)
```php
<?php
…
…
if ($i == 0) {
 print "i equals 0";
} elseif ($i == 1) {
 print "i equals 1";
} elseif ($i == 2) {
 print "i equals 2";
}
?>
```
```php
<?php
…
…
switch ($i) {
 case 0:
 print "i equals 0";
 break;
 case 1:
 print "i equals 1";
 break;
 case 2:
 print "i equals 2";
 break;
}
?>
```

#### 1.2.a)

Sí, los tres códigos son equivalentes en comportamiento y salida.

Todos imprimen:
```
12345678910
```

#### 1.2.b)

Sí, los cuatro códigos son equivalentes.

Todos producen como salida:

```
12345678910
```

#### 1.2.c)

Sí, los dos códigos son equivalentes.
Ambos implementan la misma lógica de selección múltiple para los valores 0, 1 y 2.

Difieren en sintaxis (``if/elseif`` vs ``switch/case``) pero tienen el mismo comportamiento.

### 1.3) Explicar para qué se utiliza el siguiente código:

#### 1.3.a)
```php
<html>
<head><title>Documento 1</title></head>
<body>
<?php
 echo "<table width = 90% border = '1' >";
 $row = 5;
 $col = 2;
 for ($r = 1; $r <= $row; $r++) {
 echo "<tr>";
 for ($c = 1; $c <= $col;$c++) {
 echo "<td>&nbsp;</td>\n";
 } echo "</tr>\n";
 }
 echo "</table>\n";
?>
</body></html>
```

#### 1.3.b)
```php
<html>
<head><title>Documento 2</title></head>
<body>
<?php
if (!isset($_POST['submit'])) {
?>
 <form action="<?php echo $_SERVER['PHP_SELF']; ?>" method="post">
 Edad: <input name="age" size="2">
 <input type="submit" name="submit" value="Ir">
 </form>
<?php
 }
else {
 $age = $_POST['age'];
 if ($age >= 21) {
 echo 'Mayor de edad';
 }
 else {
 echo 'Menor de edad';
 }
}
?>
</body></html>
```

#### 1.3.a)

Este código PHP genera una tabla HTML con 5 filas y 2 columnas. La tabla ocupa el 90% del ancho de la página y tiene un borde de 1 píxel. Se usan bucles for anidados para crear dinámicamente cada fila y celda. Cada celda contiene un espacio en blanco para que no aparezca vacía visualmente.

#### 1.3.b)

Este código PHP se utiliza para mostrar un formulario que solicita la edad del usuario. Al enviar el formulario este se oculta y luego evalúa si la persona tiene 21 años o más, y muestra un mensaje indicando si es "Mayor de edad" o "Menor de edad". Utiliza el método POST y procesa los datos en la misma página.

### 1.4) Si el archivo datos.php contiene el código que sigue:

```php
<?php
$color = 'blanco';
$flor = 'clavel';
?>
```

#### Indicar las salidas que produce el siguiente código. Justificar.

```php
<?php
echo "El $flor $color \n";
include 'datos.php';
echo " El $flor $color";
?>
```

Al inicio, las variables no estaban definidas, por eso la primera línea imprime “El ” (vacío). Luego, el include carga las variables desde datos.php. En la segunda línea ya tienen valores y se imprimen correctamente como “El clavel blanco”. Por lo tanto la salida obtenida es:

```
El 
 El clavel blanco
```

### 1.5) Analizar el siguiente ejemplo: Contador de visitas a una página web


#### contador.php
```php
<?
// Archivo para acumular el numero de visitas
$archivo = "contador.dat";
// Abrir el archivo para lectura
$abrir = fopen($archivo, "r");
// Leer el contenido del archivo
$cont = fread($abrir, filesize($archivo));
// Cerrar el archivo
fclose($abrir);
// Abrir nuevamente el archivo para escritura
$abrir = fopen($archivo, "w");
// Agregar 1 visita
$cont = $cont + 1;
// Guardar la modificación
$guardar = fwrite($abrir, $cont);
// Cerrar el archivo
fclose($abrir);
// Mostrar el total de visitas
echo "<font face='arial' size='3'>Cantidad de visitas:".$cont."</font>";
?>
```

#### vistas.php
```php
<!-- Página que va a contener al contador de visitas -->
<html>
<head></head>
<body>
<? include("contador.php")?>
</body>
</html>
```

#### En la misma carpeta, crear el archivo de texto contador.dat, con el valor inicial del contador y con permisos de lectura y escritura.

#### Análisis del código:

Este código implementa un contador de visitas y un archivo de texto plano llamado contador.dat. Cada vez que un usuario accede a la página visitas.php, se ejecuta el script contador.php, que abre el archivo contador.dat, lee el número actual de visitas, lo incrementa en uno, y luego guarda el nuevo valor en el mismo archivo. Finalmente, muestra en pantalla cuántas veces se ha visitado la página. Para que funcione, es necesario que el archivo contador.dat exista en la misma carpeta y tenga permisos de lectura y escritura.

#### Ejemplo del contenido de contador.dat
```
6
```

---
### Sección 2 PHP: arrays, funciones

### 2.1) Indicar si los siguientes códigos son equivalentes.

```php
<?php
$a = array( 'color' => 'rojo',
 'sabor' => 'dulce',
 'forma' => 'redonda',
 'nombre' => 'manzana',
 4
 );
?> 
```

```php
<?php
$a['color'] = 'rojo';
$a['sabor'] = 'dulce';
$a['forma'] = 'redonda';
$a['nombre'] = 'manzana';
$a[] = 4;
?> 
```

#### 2.1)

Sí, ambos fragmentos de código PHP son equivalentes porque crean un array asociativo con las mismas claves (color, sabor, forma, nombre) y valores, y además agregan un valor adicional (4) sin clave, que PHP asigna automáticamente al índice numérico 0. Aunque la sintaxis es diferente (uno usa array() y el otro asignaciones paso a paso), el resultado final del array es el mismo en estructura y contenido.

### 2.2) En cada caso, indicar las salidas correspondientes

#### 2.2.a)
```php
<?php
$matriz = array("x" => "bar", 12 => true);
echo $matriz["x"];
echo $matriz[12];
?>
```

#### Salida
```
bar1
```


#### 2.2.b)
```php
<?php
$matriz = array("unamatriz" => array(6 => 5, 13 => 9, "a" => 42));
echo $matriz["unamatriz"][6];
echo $matriz["unamatriz"][13];
echo $matriz["unamatriz"]["a"];
?>
```

#### Salida
```
5942
```

#### 2.2.c)
```php
<?php
$matriz = array(5 => 1, 12 => 2);
$matriz[] = 56;
$matriz["x"] = 42; unset($matriz[5]); unset($matriz);
?> 
```

#### Salida
```
(no hay salida)
```

### 2.3) En cada caso, indicar las salidas correspondientes

#### 2.3.a)
```php
<?php
$fun = getdate();
echo "Has entrado en esta pagina a las $fun[hours] horas, con $fun[minutes] minutos y $fun[seconds]
segundos, del $fun[mday]/$fun[mon]/$fun[year]";
?>
```

#### Salida
```php
//Suponiendo que al moomento de ejecutar el script es 14/6/2025 a las 12:00:00
Has entrado en esta pagina a las 12 horas, con 0 minutos y 0 segundos, del 14/6/2025
```

#### 2.3.b)
```php
<?php
function sumar($sumando1,$sumando2){
 $suma=$sumando1+$sumando2;
 echo $sumando1."+".$sumando2."=".$suma;
}
sumar(5,6);
?>
```

#### Salida

```
5+6=11   
```

### 2.4) Analizar la siguiente función, y escribir un script para probar su funcionamiento:

```php
function comprobar_nombre_usuario($nombre_usuario){
 //compruebo que el tamaño del string sea válido.
 if (strlen($nombre_usuario)<3 || strlen($nombre_usuario)>20){
 echo $nombre_usuario . " no es válido<br>";
 return false;
 }
 //compruebo que los caracteres sean los permitidos
 $permitidos = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789_";
 for ($i=0; $i<strlen($nombre_usuario); $i++){
 if (strpos($permitidos, substr($nombre_usuario,$i,1))===false){
 echo $nombre_usuario . " no es válido<br>";
 return false;
 }
 }
 echo $nombre_usuario . " es válido<br>";
 return true;
} 
```

#### Script para probar el funcionamiento

```php
<?php
function comprobar_nombre_usuario($nombre_usuario){
    if (strlen($nombre_usuario) < 3 || strlen($nombre_usuario) > 20){
        echo $nombre_usuario . " no es válido<br>";
        return false;
    }

    $permitidos = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789_";

    for ($i = 0; $i < strlen($nombre_usuario); $i++){
        if (strpos($permitidos, substr($nombre_usuario, $i, 1)) === false){
            echo $nombre_usuario . " no es válido<br>";
            return false;
        }
    }

    echo $nombre_usuario . " es válido<br>";
    return true;
}

// Pruebas de la función
comprobar_nombre_usuario("Usuario_123");   // Válido
comprobar_nombre_usuario("Us");           // No válido (muy corto)
comprobar_nombre_usuario("Usuario!");     // No válido (carácter ! no permitido)
comprobar_nombre_usuario("usuario-123");  // No válido (guion medio no permitido)
comprobar_nombre_usuario("Usuario_Valido"); // Válido
?>
```

#### Salida
```
Usuario_123 es válido
Us no es válido
Usuario! no es válido
usuario-123 no es válido
Usuario_Valido es válido
```