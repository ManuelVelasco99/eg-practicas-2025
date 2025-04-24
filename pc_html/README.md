## Práctica Complementaria HTML5

###  1) Responder el siguiente cuestionario

### 1.1)  ¿Ventajas de HTML5?

HTML5 tiene muchas ventajas, como mejor soporte para multimedia, ya que permite
integrar audio, video y gráficos sin necesidad de plugins externos. Además, sus nuevas
etiquetas semánticas hacen que el código sea más accesible y fácil de entender. Es
también más eficiente en cuanto a rendimiento, funciona muy bien en dispositivos móviles, y
permite el almacenamiento local para aplicaciones web.

### 1.2) ¿Por qué utilizarlo?

HTML5 es el estándar actual para el desarrollo web porque mejora la accesibilidad y la
experiencia en dispositivos móviles. También elimina la necesidad de plugins, lo que hace
que las páginas web sean más rápidas y seguras. Su integración con otras tecnologías web
lo hace perfecto para crear aplicaciones interactivas.

### 1.3) Nombre ventajas

Algunas ventajas son: mejor soporte para multimedia, nuevas etiquetas semánticas
que ayudan a organizar el contenido, mayor compatibilidad con dispositivos móviles y un
mejor rendimiento general.

---
### Ejercitación 2

### 2.A) ¿Qué formatos soporta ?

HTML5 soporta formatos como MP3, Ogg, WAV y AAC para el elemento ````<audio>````.

### 2.B) Crear un elemento audio
````html
<audio controls>
<source
    src="https://cdn.pixabay.com/audio/2025/02/26/audio_6c95941b94.mp3"
    type="audio/mp3">
    Tu navegador no soporta el elemento de audio.
</audio>
````
---

### Ejercitación 3

### 3.A) ¿Qué formatos soporta ?
El elemento ``<video>`` de HTML5 es compatible con formatos como MP4, WebM y Ogg.

### 3.B) Crear un elemento video

````html
<video controls>
    <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
    <source src="https://www.w3schools.com/html/mov_bbb.ogg" type="video/ogg">
    Tu navegador no soporta el elemento de video.
</video>
````

---

### Ejercitación 4

### 4.A) Crear un formulario con un campo requerido

````html
<form>
    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre" required>
    <input type="submit" value="Enviar">
</form>
````

### 4.B) Crear un formulario con un campo de tipo email y validar que funcione

````html
<form>
    <label for="email">Correo electrónico:</label>
    <input type="email" id="email" name="email" required>
    <input type="submit" value="Enviar">
</form>
````

### 4.C) Crear un formulario con un campo de tipo fecha y validar que funcione

````html
<form>
    <label for="fecha">Fecha:</label>
    <input type="date" id="fecha" name="fecha" required>
    <input type="submit" value="Enviar">
</form>
````

### 4.D) Crear un formulario con un campo de tipo color y validar que funcione

````html
<form>
    <label for="color">Color:</label>
    <input type="color" id="color" name="color" required>
    <input type="submit" value="Enviar">
</form>
````

### 4.E) Crear un formulario con un campo de tipo number y validar que funcione. Además configurar valores mínimos y máximos permitidos.

````html
<form>
    <label for="edad">Edad:</label>
    <input type="number" id="edad" name="edad" min="18" max="100"
    required>
    <input type="submit" value="Enviar">
</form>
````