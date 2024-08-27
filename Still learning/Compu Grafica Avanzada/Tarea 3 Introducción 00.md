## Diego Barragán Rivera
## Computación Gráfica Avanzada
Primero nos aseguramos que la sintetiza el proyecto correcto, que en este caso en 00-Introduccion, Se hace lo mismo al ejecutarlo.
![[Pasted image 20240824111542.png|Figura 1: Barra de tareas CMake]]
Para cerciorarnos de lo anterior, se ejecuta el proyecto y se observa como no arroja errores y todos los objetos y texturas se renderizan correctamente.
![[Pasted image 20240824111725.png|Figura 2: Ejecucion de 00-Introduccion]]
La primera parte del código nos muestra la importación de las bibliotecas primarias de OpenGL y C. 
![[Pasted image 20240824111832.png|Figura 3: Importación de bibliotecas]]
Además de las bibliotecas, importamos archivos header para utilizar recursos generados específicamente para el proyecto o conjunto de proyectos de la materia. Específicamente se importan shaders, figuras 3D, funciones de cámara, texturas y modelos.
![[Pasted image 20240824111850.png|Figura 4: Importación de headers]]
Como en todo código tenemos una función main donde mandamos a inicializar el proyecto por medio de init. Una vez con los recursos en memoria, se llama a applicationLoop para mantener el proyecto ejecución y esperar inputs del usuario para procesar las interacciones entre los objetos.
![[Pasted image 20240824112106.png|Figura 5: Función Main]]
La función init toma los parámetros para definir las dimensiones de la ventana emergente donde se renderiza el proyecto. Si alguno de los procesos de GLFW falla, se muestra un mensaje al usuario indicando el fallo.
![[Pasted image 20240824112346.png|Figura 6: Parte de init donde se administran las funciones de GLFW]]
Los callbacks de cursor y teclado son cruciales para esta actividad, ya que utilizamos sus inputs como medio de navegación dentro del entorno. Tambien se tiene a WindowSizeCallback() en caso de que el usuario desee cambiar el tamaño de la ventana.
![[Pasted image 20240824112439.png|Figura 7: Llamada a callbacks]]
En las siguiente lineas se llaman las funciones de GLEW y además se configura el Viewport a partir de las variables de ancho y alto de la ventana. Se activa la prueba de profundidad y el corte de caras. Las últimas 3 líneas indican la inicializaciónde shaders para los modelos, el skybox y la iluminación.
![[Pasted image 20240824113416.png|Figura 8: Configuración de Viewport e inicialización de shaders]]
Para entender el proceso de inserción de un objeto en la escena, se inserta una esfera por medio de el objeto esfer1, que es de tipo Sphere. Al igual que a los otros objetos le aplicamos el shaderMultiLightining para que se le aplique la iluminación por igual a todos los objetos.
![[Pasted image 20240824114501.png|Figura 9: Inicialización de objetos]]
La función applicationLoop es, como su nombre lo indica, un bucle que permite la ejecución continua del código en espera de inputs del usuario. En la imagen mostrada primero se declaran las transformaciones del objeto eclipse junto con sus variable que utilizamos para su animación en la práctica 1. Tambien reservamos un espacio en el sistema de archivos para guardar los keyframes con los que vamos a animar al modelo de Darth Vader. El while mostrado continua mientras psi sea true y este mismo continua siéndolo por medio del proceso de los inputs como se muestra en la última línea de las imágenes.
![[Pasted image 20240824115408.png|Figura 10: AutomationLoop ]]
![[Pasted image 20240824115437.png|Figura 11: Cálculo de framerate]]
ProcessInput() se encarga de avisar si hay actividad dentro del programa o si se cerró la ventana del proyecto. De este modo el programa sabe cuando liberar la memoria de los recursos utilizados. También se declaran las teclas utilizadas como input y sus funciones.
![[Pasted image 20240824115822.png|Figura 12: processInput]]
Otra parte fundamental del código es la configuración de la matriz proyección y vista. A estos se les asignan los shader de los objetos, iluminación y del Skybox.
![[Pasted image 20240824115938.png|Figura 13: Configuración de projection y view]]
Lo siguiente en el proceso de agregar un objeto es asignar texturas, escalas y transformaciones. La primera se renderiza con una textura de carretera y en modo Fill, donde se ve como una esfera con volumen, mientras que la segunda esfera utiliza la textura de una pared y se rederiza a como un conjunto de aristas por el anableWireMode().

![[Pasted image 20240824120305.png|Figura 14: Renderizado de esferas]]

![[Pasted image 20240824125600.png|Figura 15: Resultado del renderizado de esferas]]

 Aquí se muestra como se carga una imagen de textura, la configura y la transfiere a la GPU para su uso en renderizado con OpenGL. Se asegura de que la textura esté correctamente configurada y optimizada para diferentes situaciones de renderizado.

![[Pasted image 20240824125835.png|Figura 16: Carga de imagen como textura]]

![[Pasted image 20240824131939.png|Figura 17: declaración de objeto esfera1]]

![[Pasted image 20240824131956.png|Figura 18: Inicialización de objeto de landing pad]]

![[Pasted image 20240824132012.png|Figura 19: Liberación de recursos tomados por los modelos]]
Además de la esfera, se inserta un objeto llamado Landingpad. Al igual que todos los demás se le aplican transformaciones y texturas. Tambien el le aplica el shader de Multilighting. En este caso nos concentramos es scaleUV para renderizar copias del mismo objeto a un lado de sí mismo.
![[Pasted image 20240824132102.png|Figura 20: Transformaciones de Landingpad y asignación de texturas de Landingpad]]
Los cambios en ScaleUV nospermite rederizar repeticiones del mismo objeto.
![[Pasted image 20240824132329.png|Figura 21: Cambios en Shader]]

![[Pasted image 20240824132738.png|Figura 22: Resultado de asignar a scaleUV como 2,2]]

![[Pasted image 20240824132802.png]]
![[Pasted image 20240824132655.png|Figura 22: Resultado de asignar a scaleUV como 1,2]]

![[Pasted image 20240824133145.png|Figura 23: Uso de GL REPEAT]]
![[Pasted image 20240824133114.png|Figura 24: Resultado gl repeat]]
- **`GL_REPEAT`** es adecuado cuando necesitas que la textura se repita continuamente.
- **`GL_CLAMP`** es útil cuando deseas que la textura se extienda hasta los bordes sin repetirla
![[Pasted image 20240824133231.png|Figura 25: Uso de GL CLAMP]]
![[Pasted image 20240824133256.png|Figura 26: Resultado de GL CLAMP]]
