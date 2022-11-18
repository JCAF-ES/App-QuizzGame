# QuizzGame

## [1 - Descripcion de la Aplicación](#Descripcion)
## [2 - Pantallas y Relación Entre Ellas](#Pantallas)
## [3 - Principales Clases Utilizadas](#Clases)
## [4 - Dificultades](#Dificultades)
## [5 - Autor](#Autor)
## [6 - Conclusión](#Conclusión)

## 1 - :page_with_curl: Descripcion de la Aplicación <a name="Descripcion">
Es una aplicación para dispositivos móviles en la que se han incluido varios minijuegos con la finalidad de integrar varias funcionalidades vistas 
en clase, a continuación se describirán dichas funcionalidades: single touch, multi touch, acelerómetro, uso de gestures, double tap.

## 2 - :tv: Pantallas y Relación Entre Ellas <a name="Pantallas">
En esta sección se hablará sobre todas las pantallas que se han realizado y como se va de una a otra, así como la tecnología que utilizamos para 
desarrollarla.
### 2.1 LOGIN
  Primero se inicia una actividad con un loguin (Ilistración 1) en el cual puedes introducir los datos de nombre y contraseña para entrar en la 
  aplicación. Para entrar en la aplicación se tiene que dar al botón “SING IN” que se activará después de haber introducido al menos un carácter 
  en ambos EditText. También puedes dar al botón de registrarse, dónde te llevará a una nueva actividad en la que introducir tu nombre de usuario y 
  contraseña. Además, si te registras vuelves al login con la información de tu usuario y contraseña ya escritos en el editText mediante el uso de 
  OnActivityResult.
  
  ![image](https://user-images.githubusercontent.com/63256402/202596418-43d32a4e-aa9e-4a95-9994-60b892a09a19.png)
  
  ![image](https://user-images.githubusercontent.com/63256402/202596653-866ecec9-6ba7-4a66-93b6-c4e4455e966c.png)
  
  En la pantalla de Loguin hay un botón en la esquina superior que permite cambiar la fuente de los textos. Además, hay una opción para modificar la 
  base de datos, eliminando, modificando o incluyendo preguntas, para ello se ha implementado un buscador. También puedes encontrar un botón de “tienda” 
  en la que se pueden comprar pistas que ayudarán al usuario a resolver preguntas.
  
  ![image](https://user-images.githubusercontent.com/63256402/202596883-1c1d0acf-0b59-4682-87de-2b75ab8310d3.png)
  
  En la anterior imagen se puede ver cómo te puedes registrar. Se puede tener una foto identificativa que se guardará en una base de datos.
  
  ![image](https://user-images.githubusercontent.com/63256402/202597050-697e3445-f1e4-4927-90fa-19d344e2c22d.png)
  
  Una vez identificados podemos entrara en la pantalla de inicio en la que deberemos ir superando minijuegos de uno en uno hasta completarlos todos. 
  Ha cada minijuego le corresponde un GIF que se ilumina cuando puedes jugar al minijueego. Para animar el gif se utilizó la función estática with() 
  de la clase Glide().
  
### 2.2 MINIJUEGO 1
  Cuando nos logueamos empieza el quiz en el cual tendremos que superar distintos niveles para completar el juego. El primer minijuego es el quiz que 
  implementamos hasta la práctica tres (Ilustración 5) en el que se han incorporado nuevas funcionalidades como el botón “pista”, el cual se podrá usar 
  si tenemos pistas suficientes. Cuando pulsemos sobre el botón pista, el botón de la respuesta correcta se moverá, se ha usado la clase animator para 
  realizar esta funcionalidad.
  
  ![image](https://user-images.githubusercontent.com/63256402/202597186-9ccd980b-c774-46b1-9370-1499c4d4b5a4.png)
  
### 2.3 MINIJUEGO 2

  Una vez superado el juego de las preguntas, se tendrá que superar el segundo minijuego (Ilustración 6) en el que se tienen que mover unos botones y 
  deslizarlos sobre la respuesta correcta, para ello se ha utilizado dragListener para capturar el evento y se ha reescrito el evento ACTION_DROP en 
  el que se compara si la respuesta es correcta.
  
  ![image](https://user-images.githubusercontent.com/63256402/202597275-88a6850f-8422-46a9-8c1d-5a7368045cc1.png)
  
### 2.4 MINIJUEGO 3

  En el tercer minijuego (Ilustración 7) se tendrá que encontrar las diferencias entre ambas imágenes, para ello el usuario utilizará el efecto zoom usando 
  el multitouch o doubletouch para acercar o alejar la imagen. Una vez vistas las diferencias el jugador elegirá entre cuatro opciones su respuesta.
  
  ![image](https://user-images.githubusercontent.com/63256402/202597370-b57b8ce9-6022-49ef-8b37-648738c4a1a9.png)
  
### 2.5 MINIJUEGO 4

  En el cuarto minijuego (Ilustración 8) el usuario conducirá una nave espacial con la que reunirá todos los puntos posibles, si colisiona con una bola de 
  fuego el minijuego concluirá. Para la elaboración del minijuego se han reescrito las funciones dispatchKeyEvent y onTouchEvent, además de toda la lógica 
  implementada en otras funciones. También se ha reescrito la función onBackPressed para controlar el botón de pulsar atrás, si se pulsa dos veces seguidas 
  el juego acabará, pero si solo se pulsa una vez, se ejecutará un toast preguntando si se quiere salir.
  
  ![image](https://user-images.githubusercontent.com/63256402/202597466-97669406-73a6-4f5f-a984-9a62c4585528.png)
  
### 2.6 MINIJUEGO 5

  En el minijuego 5 eres un alienígena que debe sortear paredes utilizando el acelerómetro. Para ello se ha utilizado la interfaz sensorEventListener utilizando 
  la matriz de rotación para saber el giro del dispositivo, y aumentando la velocidad hacia la dirección que está girado el dispositivo. Además, se utiliza la 
  clase surfaceView para pintar el panel de juego. El personaje principal tiene 3 imágenes que se superponen para que parezca que anda. Y la velocidad de llegada 
  de obstáculos y el tamaño de los agujeros están predefinidos por el código. Por último, se ha tenido que implementar un hilo para ejecutar el juego en él.
  
  ![image](https://user-images.githubusercontent.com/63256402/202597591-e615c736-37f5-45e5-a528-1468c321a0d8.png)
  
### 2.7 REALIDAD AUMENTADA

  Se descargo el plugin de Google Sceneform para soportar el uso de la realidad aumentada. Se implementó un frame del tipo de Sceneform, y se creó un objeto 3D, cuya 
  estructura y material fueron descargados de una página de diseños libres. En los móviles compatibles se puede hacer una foto de la copa que has ganado por superar 
  todos los juegos.
  
  ![image](https://user-images.githubusercontent.com/63256402/202597670-5fbb1e7a-a09c-40d7-bbf5-1c600aa058e9.png)
  
### 2.8 CONEXIÓN ENTRE PANTALLAS
  
  ![image](https://user-images.githubusercontent.com/63256402/202597712-5e1878c7-7609-42fe-8eab-fcfc774aafbb.png)
  
### 2.8 CONEXIÓN ENTRE ACTIVIDADES
  
  ![image](https://user-images.githubusercontent.com/63256402/202597775-0e91b04d-742e-44f7-b530-4bf07c89ef88.png)

## 3 - :open_file_folder: Principales Clases Utilizadas <a name="Clases">

  Las clases elegidas para la realización de esta práctica fueron:
  - Timer: se ha usado para que los subprocesos, del minijuego Nave, programen tareas para su ejecución futura en un subproceso en segundo plano.
  - Handler: se usó para procesos que se ejecutarán en algún momento en el futuro.
  - MotionEvent: se utilizó para informar eventos de movimiento y usarlos reescribiendo sus funciones en los minijuegos.
  - Glide: se ha usado para cargar imágenes a un botón ImageView.
  - WindowManager: se usó para administrar ventanas y obtener sus dimensiones.
  - KeyEvent: se utilizó para capturar eventos de botón.
  - animator: esta clase la utilizamos para dar soporte básico a animaciones que implementamos en los minijuegos.
  
  Para el último juego se ha decidido modificar la pantalla mediante draw:
  
  - Los obstáculos: Son dos cuadrados que aparecen bajo un tiempo y con un espacio determinado.
  - El jugador: Son tres fotos de un personaje que se alternan para dar la sensación de movimiento.
  - La escena principal: Tiene un fondo blanco con una puntuación arriba a la izquierda y si pierdes sale “Game Over”.
  Además, ha sido necesario implementar un hilo en el que correr el juego (MainThread) que por ejemplo limitase los FPS para aumentar la compatibilidad.
  Por último, para soportar el uso del acelerómetro se han utilizado la interfaz: SensorEventListener
  
## 4 - :chart_with_upwards_trend: Dificultades <a name="Dificultades">

  Para la realización de esta aplicación se encontraron diversas dificultades, una ellas fue la reproducción de imágenes en una actividad, para solucionarlo 
  se creó un gif y se reprodujo mediante la clase Glide. Para la animación de botones se usó también la clase animator. O la inclusión de la realidad aumentada 
  en la aplicación que nos obligó a aumentar a Android 7.0 el sistema mínimo, impidiendo que ningún móvil de los participantes pudiese soportarlo, teniendo que 
  pedir a un tercero que nos ayudase ha hacer la prueba. Por último, la mayor dificultad ha sido mantener funcionales las partes anteriores mientras añadíamos 
  nuevas actualizaciones.
  
## 5 - :running: Autor <a name="Autor">
  - Juancarlos@jcfa.me
  - ##### Github: [FinalBossRel](https://github.com/FinalBossRel)
  
## 6 - :speech_balloon: Conclusión <a name="Conclusión">

  Durante el desarrollo se han ido implementando y creando nuevas características. En esta última actualización de la aplicación, se ha tratado de hacerla 
  parecer una aplicación totalmente terminada y plenamente usable. Aunque también se nos ocurren mejoras como nuevos juegos, más fondos de pantalla, botones 
  más estéticos y una mayor usabilidad, que nos hubiese gustado añadir. Con todo, esta aplicación tiene juegos en los que se manejan multitud de eventos, desde
  multitouch al acelerómetro. Además de manejar gráficos, animaciones y sonidos durante el juego. Y todo ello encajando a la perfección con lo ya realizado en 
  las anteriores prácticas.
  En conclusión, en la creación de esta aplicación han implementado muchas funcionalidades, quedando un proyecto complejo y sólido que cuenta con más de 
  cuarenta clases y unas siete mil líneas de código.
