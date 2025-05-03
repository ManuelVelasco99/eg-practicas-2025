## Práctica N2 CSS

### 1.1 ¿Qué es CSS y para qué se usa?

CSS (Cascading Style Sheets, u Hojas de Estilo en Cascada) es un lenguaje utilizado para describir la presentación y el diseño de los documentos HTML. Se usa para definir estilos como colores, fuentes, márgenes, posiciones, tamaños, animaciones y más, separando el contenido (HTML) de su apariencia.


### 1.2 CSS utiliza reglas para las declaraciones de estilo, ¿cómo funcionan?

Las reglas CSS siguen una estructura básica:

```css
selector {
  propiedad: valor;
}
```

- El **selector** indica a qué elementos HTML se aplicará el estilo.  
- Las **propiedades** son las características visuales que se desean cambiar.  
- Los **valores** especifican cómo se debe aplicar esa propiedad.

**Ejemplo:**

```css
p {
  color: red;
}
```

Este estilo aplicará el color rojo a todos los párrafos `<p>`.


### 1.3 ¿Cuáles son las tres formas de dar estilo a un documento?

1. **CSS en línea (inline):**  
   Se escribe directamente en la etiqueta HTML, usando el atributo `style`.  
   ```html
   <p style="color: blue;">Texto azul</p>
   ```

2. **CSS interno (internal):**  
   Se escribe dentro de una etiqueta `<style>` en la cabecera del documento HTML.  
   ```html
   <style>
     p { color: green; }
   </style>
   ```

3. **CSS externo (external):**  
   Se escribe en un archivo `.css` separado y se vincula al HTML con `<link>`.  
   ```html
   <link rel="stylesheet" href="estilos.css">
   ```



### 1.4 ¿Cuáles son los distintos tipos de selectores más utilizados? Ejemplifique cada uno.

- **Selector de tipo:**  
  ```css
  h1 { font-size: 24px; }
  ```

- **Selector de clase (`.`):**  
  ```css
  .destacado { color: orange; }
  ```

- **Selector de ID (`#`):**  
  ```css
  #titulo { text-align: center; }
  ```

- **Selector universal (`*`):**  
  ```css
  * { margin: 0; padding: 0; }
  ```

- **Selector de atributo:**  
  ```css
  input[type="text"] { background-color: yellow; }
  ```

- **Selector descendente:**  
  ```css
  div p { font-style: italic; }
  ```


### 1.5 ¿Qué es una pseudo-clase? ¿Cuáles son las más utilizadas aplicadas a vínculos?

Una **pseudo-clase** es una palabra clave añadida a los selectores que define un estado especial del elemento.

**Pseudo-clases comunes en vínculos:**
- `:link` — Vínculo no visitado.
- `:visited` — Vínculo ya visitado.
- `:hover` — Cuando el usuario pasa el mouse sobre el vínculo.
- `:active` — Cuando el vínculo está siendo clickeado.
- `:focus` — Cuando el elemento está enfocado.

**Ejemplo:**

```css
a:hover {
  color: red;
}
```


### 1.6 ¿Qué es la herencia?

La **herencia** en CSS es el mecanismo por el cual algunos estilos aplicados a un elemento padre se transmiten a sus elementos hijos. No todas las propiedades se heredan, pero sí muchas relacionadas con texto (como color, fuente, espaciado).

**Ejemplo:**

```css
div {
  color: blue;
}
```

Todos los textos dentro del `<div>` heredarán el color azul, a menos que se indique lo contrario.


### 1.7 ¿En qué consiste el proceso denominado cascada?

La **cascada** es el conjunto de reglas que CSS utiliza para decidir qué estilo aplicar cuando hay múltiples reglas para un mismo elemento. Este proceso considera:

- El **origen del estilo** (navegador, usuario, autor).
- La **especificidad** del selector.
- El **orden de aparición** en el documento (último gana si hay conflicto).
- Si una regla está marcada como `!important`.

La cascada permite combinar reglas de distintos lugares de manera coherente.

---

### 2) Analizar el siguiente código señalando declaraciones y aplicaciones de reglas, y su efecto. Análisis de Reglas CSS y su Aplicación

A continuación se analiza el siguiente código CSS y HTML:

#### Código CSS

```css
p#normal {
  font-family: arial,helvetica;
  font-size: 11px;
  font-weight: bold;
}

*#destacado {
  border-style: solid;
  border-color: blue;
  border-width: 2px;
}

#distinto {
  background-color: #9EC7EB;
  color: red;
}
```

#### Código HTML

```html
<p id="normal">Este es un párrafo</p>
<p id="destacado">Este es otro párrafo</p>
<table id="destacado"><tr><td>Esta es una tabla</td></tr></table>
<p id="distinto">Este es el último párrafo</p>
```


#### Análisis de las Reglas

#### 1. `p#normal`

- **Selector:** `p#normal`  
  Aplica la regla solamente al elemento `<p>` que tenga `id="normal"`.
- **Propiedades aplicadas:**
  - `font-family: arial,helvetica;` → Utiliza la fuente Arial o, si no está disponible, Helvetica.
  - `font-size: 11px;` → Tamaño de fuente de 11 píxeles.
  - `font-weight: bold;` → Texto en negrita.
- **Aplicación:**  
  Afecta solo al primer párrafo:
  ```html
  <p id="normal">Este es un párrafo</p>
  ```


#### 2. `*#destacado`

- **Selector:** `*#destacado`  
  Selecciona cualquier elemento (`*`) con `id="destacado"`.  
  Nota: El uso de `*` es redundante en este contexto; `#destacado` sería suficiente.
- **Propiedades aplicadas:**
  - `border-style: solid;` → Borde de línea sólida.
  - `border-color: blue;` → Borde de color azul.
  - `border-width: 2px;` → Borde de 2 píxeles de ancho.
- **Aplicación:**  
  Afecta al párrafo y a la tabla con `id="destacado"`:
  ```html
  <p id="destacado">Este es otro párrafo</p>
  <table id="destacado"><tr><td>Esta es una tabla</td></tr></table>
  ```
  Ambos elementos tendrán un borde azul de 2px.


#### 3. `#distinto`

- **Selector:** `#distinto`  
  Selecciona cualquier elemento con `id="distinto"`.
- **Propiedades aplicadas:**
  - `background-color: #9EC7EB;` → Fondo celeste claro.
  - `color: red;` → Texto en color rojo.
- **Aplicación:**  
  Afecta al párrafo con `id="distinto"`:
  ```html
  <p id="distinto">Este es el último párrafo</p>
  ```


#### Conclusión

- Las reglas CSS están correctamente aplicadas según los selectores por ID.
- El uso de `*#destacado` es válido pero innecesariamente complejo.
- Cada estilo afecta a su elemento objetivo de forma específica y clara.

---- 

### 3) Analizar el siguiente código señalando declaraciones y aplicaciones de reglas, y su efecto.

#### Código CSS

```css
p.quitar {
  color: red;
}

*.desarrollo {
  font-size: 8px;
}

.importante {
  font-size: 20px;
}
```

#### Código HTML

```html
<p class="desarrollo">
En este primer párrafo trataremos lo siguiente:
<br />xxxxxxxxxxxxxxxxxxxxxxxxx
</p>

<p class="quitar">
Este párrafo debe ser quitado de la obra…
<br />xxxxxxxxxxxxxxxxxxxxxxxxx
</p>

<p>
En este otro párrafo trataremos otro tema:<br />
xxxxxxxxxxxxxxxxxxxxxxxxx
</p>

<p class="importante">
Y este es el párrafo más importante de la obra…
<br />xxxxxxxxxxxxxxxxxxxxxxxxx
</p>

<h1 class="quitar">Este encabezado también debe ser quitado de la obra</h1>

<p class="quitar importante">Se pueden aplicar varias clases a la vez</p>
```


#### Análisis de las Reglas CSS

#### 1. `p.quitar`

- **Selector:** Aplica solo a elementos `<p>` con clase `quitar`.
- **Propiedad aplicada:**  
  - `color: red;` → El texto se mostrará en rojo.
- **Aplicación:**  
  Afecta a:
  ```html
  <p class="quitar">...</p>
  <p class="quitar importante">...</p>
  ```

#### 2. `*.desarrollo`

- **Selector:** Aplica a cualquier elemento (`*`) con clase `desarrollo`.  
  El `*` es redundante, ya que `.desarrollo` es suficiente.
- **Propiedad aplicada:**  
  - `font-size: 8px;` → Tamaño de fuente pequeño.
- **Aplicación:**  
  Afecta a:
  ```html
  <p class="desarrollo">...</p>
  ```

#### 3. `.importante`

- **Selector:** Aplica a cualquier elemento con clase `importante`.
- **Propiedad aplicada:**  
  - `font-size: 20px;` → Tamaño de fuente grande.
- **Aplicación:**  
  Afecta a:
  ```html
  <p class="importante">...</p>
  <p class="quitar importante">...</p>
  ```


#### Análisis del Resultado Visual

1. **Primer párrafo** (`class="desarrollo"`)  
   → Tamaño de fuente: 8px

2. **Segundo párrafo** (`class="quitar"`)  
   → Color: rojo

3. **Tercer párrafo** (sin clase)  
   → No tiene estilos aplicados por las reglas dadas

4. **Cuarto párrafo** (`class="importante"`)  
   → Tamaño de fuente: 20px

5. **Encabezado `<h1 class="quitar">`**  
   → **No se aplica** `p.quitar` porque el selector es específico para `<p>`,  
   → No hay regla para `.quitar` general, por lo tanto no se aplica ninguna regla

6. **Último párrafo** (`class="quitar importante"`)  
   → Se combinan ambas clases:  
   → Color: rojo, Tamaño de fuente: 20px


---

### 4) Dadas las siguientes declaraciones:


```css
* { color: green; }

a:link { color: gray; }
a:visited { color: blue; }
a:hover { color: fuchsia; }
a:active { color: red; }

p {
  font-family: arial, helvetica;
  font-size: 10px;
  color: black;
}

.contenido {
  font-size: 14px;
  font-weight: bold;
}
````

### Analizar los siguientes códigos y comparar sus efectos. Explicar:

#### Primer Fragmento HTML


```html
<body>
  <p class="contenido" style="font-weight: normal;">
    Este es un texto ...............
  </p>
  <table>
    <tr>
      <td>Y esta es una tabla.......</td>
    </tr>
    <tr>
      <td>
        <a href="http://www.google.com.ar">con un enlace</a>
      </td>
    </tr>
  </table>
</body>
```

#### Análisis

- `<p class="contenido" style="font-weight: normal;">`  
  → `class="contenido"` le daría tamaño 14px y peso `bold`.  
  → Pero el `style="font-weight: normal;"` sobrescribe el `font-weight`, aplicando **normal**.  
  → Tamaño: 14px, Fuente: Arial o Helvetica, Peso: normal, Color: **black** (por regla de `p`).

- `td` no tiene estilos específicos, pero la regla `* { color: green; }` aplica → Color de texto **verde**.

- El `<a>` sin visitar:  
  → `a:link { color: gray; }`  
  → Texto del enlace será **gris**.


#### Segundo Fragmento HTML

```html
<body class="contenido">
  <p> Este es un texto................</p>
  <table>
    <tr>
      <td>Y esta es una tabla.......</td>
    </tr>
    <tr>
      <td>
        <a href="http://www.google.com.ar">con un enlace</a>
      </td>
    </tr>
  </table>
</body>
```

#### Análisis

- `<body class="contenido">` aplica las reglas `.contenido` a `<body>`,  
  pero no hereda el estilo a los elementos hijos que ya tienen reglas más específicas como `p`.

- `<p>`  
  → Se aplica la regla de `p`:  
    Fuente: Arial, Tamaño: 10px, Color: **black**.  
  → **No se aplica** `.contenido` porque esta clase está en el `<body>`, no en el `<p>`.

- `td` → sin estilos específicos, se aplica `*` → Color: **verde**.

- `<a>`  
  → Como en el anterior, se aplica `a:link` si no fue visitado → Color: **gris**.


#### Comparación de Efectos

| Elemento              | Primer HTML                         | Segundo HTML                         |
|-----------------------|--------------------------------------|--------------------------------------|
| `<p class="contenido">` | Tamaño 14px, peso normal (por estilo en línea), color negro | Tamaño 10px, peso normal, color negro |
| Texto en `<td>`       | Verde (por `*`)                     | Verde (por `*`)                      |
| Enlace `<a>`          | Gris si no visitado, azul si visitado, cambia con hover y active | Igual comportamiento                |


#### Conclusión

- Las reglas en línea (`style`) tienen **mayor prioridad** que las clases.
- Una clase aplicada al `<body>` **no siempre** se transmite a todos los elementos hijos si hay reglas más específicas.
- La regla universal `*` aplica a todos los elementos que no tengan una regla más específica.
- Las pseudo-clases en los enlaces (`:link`, `:visited`, `:hover`, `:active`) modifican dinámicamente el color del texto según la interacción del usuario.

----

### 5) Declarar una regla CSS que produzca los efectos solicitados en cada caso.


### 5.1 Los textos enfatizados dentro de cualquier título deben ser rojos.

```css
h1 em, h2 em, h3 em, h4 em, h5 em, h6 em {
  color: red;
}
```


### 5.2 Cualquier elemento que tenga asignado el atributo "href" y que esté dentro de cualquier párrafo que a su vez esté dentro de un bloque debe ser color negro.

```css
div p [href] {
  color: black;
}
```


### 5.3 El texto de las listas no ordenadas que estén dentro del bloque identificado como “ultimo” debe ser amarillo pero si es un enlace a otra página debe ser azul.

```css
#ultimo ul {
  color: yellow;
}

#ultimo ul a[href] {
  color: blue;
}
```


### 5.4 Los elementos identificados como “importante” dentro de cualquier bloque deben ser verdes, pero si están dentro de un título deben ser rojos.

```css
div #importante {
  color: green;
}

h1#importante, h2#importante, h3#importante,
h4#importante, h5#importante, h6#importante {
  color: red;
}
```

### 5.5 Todos los elementos h1 que especifiquen el atributo title, cualquiera que sea su valor, deben ser azules.

```css
h1[title] {
  color: blue;
}
```

### 5.6 El color de los enlaces en las listas ordenadas debe ser azul para los enlaces aún no visitados, y violeta para los ya visitados y, además, no deben aparecer subrayados.

```css
ol a:link {
  color: blue;
  text-decoration: none;
}

ol a:visited {
  color: violet;
  text-decoration: none;
}
```

---

### 6) Dado los códigos de los documentos principal.html y estilo2.css, realizar las modificaciones necesarias en eldocumento HTML para reemplazar la hoja de estilo interna por la externa estilo2.css (sin modificarla) y obtener la misma salida en el navegador.

#### principal.html

````html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3c.org/TR/1999/REChtml401-19991224/loose.dtd">
<HTML lang=es xmlns="http://www.w3.org/1999/xhtml">
<HEAD><TITLE>Página Principal</TITLE>
<META http-equiv=Content-Type content="text/html; charset=iso-8859-1"></META>
<style>
body{
font-family: "Times New Roman", Times, serif;
color: #000000;
margin: 0px;
padding: 0px;
background-color: #FFFFCC;
}
a:link, a:visited, a:hover {
color: #660099;
text-decoration: none;
}
h1, h2, h3, h4, h5, h6 {
font-family: Verdana, Arial, Helvetica, sans-serif;
margin: 0px;
padding: 0px;
}
h1{
font-size: 140%;
color: #006666;
}
h2{
font-size: 120%;
color: #990000;
}
h3{
font-size: 100%;
color: #000099;
}
ul{
list-style-type: square;
color:#000000;
}
#titulo{
background-color: #CCFFCC;
margin: 5px;
padding: 0px 0px 10px 10px;
}
#menu{
background-color: #FFCC99;
}
.navBar{
margin: 0 79% 0 0;
padding: 20px;
font-size: 90%;
}
.navBar a:hover {
background-color: #dddddd;
}
#contenido{
float:right;
width: 75%;
margin: 0;
padding: 0 3% 0 0;
}
.resaltado{
color: #ff0000;
}
#pie{
clear:both;
text-align: center;
border: 1px solid #006666;
font-size: 75%;
color: #006666;
padding: 10px 10px 10px 10px;
}
</style>
</HEAD>
<BODY>
<DIV id=titulo><H1>ASIGNATURA ELECTIVA</H1></DIV>
<DIV id=contenido>
<H2>Contenido</H2>
<p>En esta asignatura ...........................<BR></p>
<P>El objetivo fundamental ..................</P>
<P>etc., etc., ...........................................</P>
<P>etc., etc., ...........................................</P>
<P>Adem&aacute;s, ...........................................</P>
<P>etc., etc., ...........................................</P>
<P class="resaltado">Pero, lo más importante es ..............................</P>
<P class="resaltado">etc., etc., ...........................................</P>
<P>Y, entonces, podemos continuar con ..................</P>
<P>etc., etc., ...........................................</P>
<P>&nbsp;</P>
</DIV>
<DIV id=menu class=navBar>
<H3>Enlaces</H3>
<UL>
<LI><A href="http://www.e-style.com.ar/moodle" target=_blank>Curso Actual</A>
<LI><A href="http://www.e-style.com.ar/logica" target=_blank>Curso anterior</A> </LI>
<LI><A href="http://www.e-style.com.ar/ntedu/consultas.htm" target=_blank>Contacto</A></LI>
</UL>
</DIV>
<DIV id=pie>Ingeniería en Sistemas de Información - Universidad Tecnológica Nacional Rosario</DIV>
<p>&nbsp;</p>
</BODY>
</HTML>
````

#### estilo2.css

````css
body {
    font-family: "Times New Roman", Times, serif;
    color: #000000;
    margin: 0;
    padding: 0;
    background-color: #FFFFCC;
}
  
a:link,
a:visited {
    color: #660099;
    text-decoration: none;
}
  
a:hover {
    background-color: #dddddd;
}
  
h1,
h2,
h3 {
    font-family: Verdana, Arial, Helvetica, sans-serif;
    margin: 0;
    padding: 0;
}
  
h1 {
    font-size: 140%;
    color: #006666;
}
  
h2 {
    font-size: 120%;
    color: #990000;
}
  
h3 {
    font-size: 100%;
    color: #000099;
}
  
ul.vineta {
    list-style-type: square;
    color: #000000;
}
  
#encabezado {
    background-color: #CCFFCC;
    margin: 5px;
    padding: 0 0 10px 10px;
}
  
#menu {
    background-color: #FFCC99;
    margin: 0 79% 0 0;
    padding: 20px;
    font-size: 90%;
}
  
#contenido {
    float: right;
    width: 75%;
    margin: 0;
    padding: 0 3% 0 0;
}
  
.resaltado {
    color: #ff0000;
}
  
#pie {
    clear: both;
    text-align: center;
    padding: 10px;
}
  
.estilopie {
    border: 1px solid #006666;
    font-size: 75%;
    color: #006666;
}
````

#### Click en el siguiente vínculo para ver el documento HTML modificado:

[principal_modificado.html](principal_modificado.html)

----

### 7) Completar el juego para practicar sobre selectores http://flukeout.github.io/

 ![captura_reto_css](<css_complete.png>)
