# Interfaz de usuario en Matlab que conecta con RoboDK - Teach Pendant

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Maintained](https://img.shields.io/maintenance/yes/2025)
![RoboDK](https://img.shields.io/badge/RoboDK-compatible-blue)
![Webots](https://img.shields.io/badge/Webots-compatible-green)
![Gazebo](https://img.shields.io/badge/Gazebo-compatible-orange)
![ROS](https://img.shields.io/badge/ROS-Noetic-blue)
![Python](https://img.shields.io/badge/Python-3.x-blue)
![C++](https://img.shields.io/badge/C++-11%2B-blue)
![MATLAB](https://img.shields.io/badge/MATLAB-compatible-yellow)

---

## 📋 Tabla de Contenidos

- [Breve Descripción del Proyecto](#-breve-descripción-del-proyecto)
- [Requisitos Previos](#-requisitos-previos)
- [Introducción](#-introducción)
- [Entorno de Simulación](#-entorno-de-simulación)
- [Instalación de Software](#-instalación-de-software)
- [Configuración del Proyecto](#-configuración-del-proyecto)
- [Programación](#-programación)
- [Conclusión](#-conclusión)
- [Mejoras Futuras](#-mejoras-futuras)
- [Advertencia](#-advertencia)
- [Recursos Adicionales](#-recursos-adicionales)
- [Autores del Proyecto](#-autores-del-proyecto)
- [Contacto](#-contacto)

---

## 📖 Breve Descripción del Proyecto
Para este proyecto se desarrollará una interfaz gráfica en la plataforma de MATLAB la cual tendrá la función de enseñar al usuario cómo manipular el robot UR5 de Universal Robots por medio de una interfaz como si este fuera el Teach Pendant físico de la misma marca. Para esto utilizaremos la función de Design App para poder generar la GUI.
Controlar al mismo robot, de igual forma vendrá con funciones de cinemática directa e inversa para poder generar un movimiento más dinámico y limpio. Finalmente esta interfaz se podrá conectar al software RoboDK para poder mostrar el control del movimiento del UR5.

---

## 📋 Requisitos Previos

### Conocimientos necesarios:
- **Fundamentos de robótica industrial:**
  - Cinemática directa
  - Cinemática inversa
  - Método Denavit-Hartenberg
- **Fundamentos matemáticos**
- **Simulación de robots**
- **Control de robots mediante interfaz gráfica**
- **Programación en MATLAB (App Designer)**
- **Integración de sistemas con RoboDK**
- **Mantenimiento y lubricación industrial**

### Herramientas necesarias:
- PC con Linux o Windows
- Acceso a Internet

### Software requerido:
- MATLAB (App Designer)
- RoboDK


---

## 📖 Introducción

En la actualidad, la automatización y la robótica industrial son clave para optimizar procesos en diversos sectores, destacando los robots colaborativos como el UR5 por su precisión, seguridad y facilidad de integración. Sin embargo, su programación aún representa un desafío, ya que suele requerir conocimientos técnicos avanzados y experiencia en lenguajes específicos, lo cual limita su accesibilidad para usuarios sin formación especializada. Aunque los teach pendants tradicionales permiten controlar estos robots, su uso puede resultar poco intuitivo y complejo, especialmente para principiantes o entornos educativos. 


Con el objetivo de hacer más accesible la interacción con el robot UR5, este proyecto propone el desarrollo de una interfaz gráfica interactiva utilizando MATLAB, apoyándose en su herramienta App Designer. Esta interfaz actúa como un teach pendant virtual, permitiendo al usuario controlar y programar el robot de forma visual, sencilla e intuitiva, sin necesidad de conocimientos avanzados en programación. Además, se establece una conexión con el entorno de simulación RoboDK, lo que posibilita la visualización en tiempo real de los movimientos del robot y la validación de trayectorias sin utilizar hardware físico.

A lo largo de este documento, se describe el proceso de desarrollo de esta herramienta, desde la definición del problema hasta las pruebas realizadas, pasando por el diseño de la interfaz, la integración con RoboDK y las funcionalidades implementadas. Finalmente, se discuten los beneficios, limitaciones y posibles mejoras futuras, destacando el valor de esta solución como herramienta educativa, de prototipado o de apoyo en la enseñanza de robótica industrial.

---

## 🔧 Entorno de Simulación

- **Simulador principal:** RoboDK
- **Sistema operativo recomendado:** Windows 11.
- **Requisitos mínimos de hardware:**
  - 8 GB RAM
  - CPU Intel i5 o superior
  - GPU dedicada (recomendable NVIDIA)

---

## 💾 Instalación de Software
En este caso, es necesario instalar el software del entorno de simulación RoboDK, junto con el software de control y manipulación de Matlab. Sin embargo existe un punto a considerar sobre ambos softwares, y es que para poder operar libremente sin ninguna restricción, se requiere de una licencia que tiene un costo considerable. Pero por otro lado, es posible obtener versiones gratuitas o de prueba de ambos softwares que permiten manipularlos sin ninguna restricción por un periodo de 30 días. Dichas versiones se pueden descargar a través de los siguientes enlaces.

- RoboDK: https://robodk.com/download
- Matlab: https://la.mathworks.com/campaigns/products/trials.html

Tanto en Matlab como en RoboDK al usar una versión de prueba de 30 días, se pueden usar ambos softwares libremente; pero al concluir el periodo, ambos programas tendrán restricciones en su operación y uso. Por lo que se podrán seguir operando, pero sin muchas otras funciones. Por otro lado, algunas instituciones permiten obtener MATLAB de manera gratuita mediante el uso de un correo electrónico perteneciente a la institución, siempre y cuando, la institución sÍ cuente con la licencia, por lo que en usos académicos, si es posible obtener MATLAB de manera "gratuita".

---

## 🛠️ Configuración del Proyecto

Ahora, es importante destacar que para la conectividad entre Matlab y RoboDK, es necesario verificar que se hayan instalado los elementos que se describen a continuación. En el caso de RoboDK, es importante ubicar la API de Matlab que generalmente se descarga al momento de descargar RoboDK. 
Para que el programa pueda detectar correctamente la ubicación del archivo, el programa .mlapp debe de moverse a la carpeta de MATLAB ubicada en el directorio de RoboDK:
```bash
C:\RoboDK\Matlab\
```

Para el caso de Matlab, es necesario instalar por lo menos los Toolboxes de: Instrument Control Toolbox, Robotics System Toolbox y Simulink (este último es opcional), ya que estos permiten una mejor comunicación desde Matlab con RoboDK y facilitan el uso de transformaciones y movimientos dentro de RoboDK desde Matlab. 

![Matlab folder](https://github.com/user-attachments/assets/7e51db3f-196b-4ef5-91ae-8d7c39decaf8)


Por último, es importante añadir que dentro de RoboDK es necesario habilitar un módulo, para permitir el uso de la API. Dentro del software de RoboDK, existen una serie de pestañas en la parte superior de la interfaz. Se debe ubicar la pestaña de "Tools" y se desplegará un submenú, donde en la parte inferior habrá otra pestaña de "Options". Dentro de la ventana de "Options", se buscará un recuadro llamado "Other" y al dar click, se abrirá una serie de configuraciones. Dentro de ese apartado, existe un recuadro ubicado del lado izquierdo que lleva de título: "RoboDK API", acompañado de una leyenda que marca: "Allow External API". Se deberá hacer click dentro del recuadro, luego en el recuadro de OK y finalmente, se podrá cerrar las opciones de Tools. 
![RoboDK configuration](https://github.com/user-attachments/assets/b781e1e1-07a2-48d6-9ad7-888dc09a0889)

Se debe de recordar habilitar la interfaz de programación externa en RoboDK para evitar posibles fallas de compatibilidad. 
Finalmente, para conectar una aplicación con la otra con el click del botón interactivo de conexión en el teach pendant, es necesario buscar en el código del archivo .mlapp la sigiente línea de código (se encuentra dentro de la función del botón de conexión):
```bash
roboDKPath = 'C:\Program Files\RoboDK\bin\RoboDK.exe';
```
y reemplazar la ruta si la instalación del programa RoboDK se encuentra en otra ubicación. Este path se usa para ejecutar RoboDK desde MATLAB en caso de que no esté ya abierto.

AQUÍ VA LA FOTO!!!

A manera de consideración adicional, es recomendable incluir las toolboxes de sistemas robóticos e instrumentación de control y recordar que la conexión entre las aplicaciones depende de una comunicación estable y pausada de los comandos ejecutados en el teach pendant.
---

## 💻 Programación

Estructura General

El código se construyó utilizando la función "appDesigner" de MATLAB.
La estructura principal de este código es de interconectar la aplicación de MATLAB con RoboDK y posteriormente reconocer el robot que se haya seleccionado para estudiar o manipular en el programa (de momento está optimizado para trabajar con robots de 6 articulaciones rotacionales y principalmente con el UR5). Para desarrollar este programa se necesitaron declarar las siguientes propiedades y funciones, además de callbacks para interactuar con los botones que aparecen en el teach-pendant:

Propiedades privadas: Variables internas como RDK, robot, temporizadores y estados de articulaciones.

Funciones de conexión: Se conectan a RoboDK y permiten seleccionar el robot deseado.

Callbacks para sliders y botones: Permiten mover las articulaciones o la herramienta.

Funciones de actualización: Mantienen los displays sincronizados con los movimientos del robot.

Manejo de errores y reconexiones automáticas en caso de interrupción en la comunicación con RoboDK.

El programa, a grandes rasgos puede dividirse en 10 bloques principales que serán descritos a continuación, es necesario mencionar que para que todas estas funciones puedan trabajar correctamente sin interferir entre ellas, fue necesario añadir al programa funciones de inicialización, y métodos que se utilizan dentro de otras funciones para optimizar la extensión del código.

1. Conexión a RoboDK
La aplicación inicia intentando establecer conexión con RoboDK. Si RoboDK no se está ejecutando, lo lanza desde una ruta conocida y realiza hasta 10 intentos de conexión. Esta lógica garantiza que el usuario no tenga que preocuparse por abrir RoboDK manualmente ni verificar conexión desde fuera de la app.

```bash
function ConnectButtonPushed(app, event)
    app.RDK = Robolink;  % Crea una instancia de conexión
    if ~isempty(app.RDK.getParam('PATH_OPENSTATION'))
        disp("✅ Conectado a RoboDK exitosamente.");
    else
        uialert(app.UIFigure, 'No se pudo conectar a RoboDK.', 'Error de conexión');
    end
end
```

2. Selección del robot
Una vez establecida la conexión, el usuario puede seleccionar el robot activo en RoboDK mediante un diálogo. La selección se guarda en el objeto app.robot, que se reutiliza en todas las operaciones siguientes. Esto asegura que cualquier acción que involucre movimiento o lectura de posición siempre se aplique al robot correcto.

```bash
function SelectRobotButtonPushed(app, event)
    app.robot = app.RDK.ItemUserPick('Select a robot', app.RDK.ITEM_TYPE_ROBOT);
end
```

3. Sistema de sliders (Base, Hombro, Codo, M1, M2, M3)
Cada slider representa una articulación del robot y está vinculado a una función Move, por ejemplo, M1Move para el cuarto eje del UR5. Cuando se manipula un slider, este actualiza una variable PendingJointValue y un índice de articulación. Luego, un temporizador se activa para aplicar el cambio de forma controlada.

Esto evita que RoboDK se sature con movimientos al arrastrar el slider rápidamente. Solo si el valor cambia y persiste por más de medio segundo se aplica el movimiento. Esta técnica mejora el rendimiento y la estabilidad del sistema.

```bash
function BaseMove(app, event)
            if isempty(app.robot) || app.robot.Valid() == 0
                uialert(app.UIFigure, 'Select a robot first!', 'Error');
                return;
            end
            startSliderTimer(app, 1, event.Value);
        end
```


4. Temporizador compartido con autodesactivación
El temporizador se activa cuando se mueve un slider y ejecuta periódicamente una función que mueve el robot según el valor pendiente. Si detecta que el valor no cambia en 5 ciclos consecutivos (0.5 segundos), se apaga automáticamente.

```bash
function startSliderTimer(app, jointIndex, value)
    app.PendingJointIndex = jointIndex;
    app.PendingJointValue = value;
    app.SliderIdleCounter = 0;

    if isempty(app.SliderTimer) || ~isvalid(app.SliderTimer)
        app.SliderTimer = timer(...
            'ExecutionMode', 'fixedRate', ...
            'Period', 0.1, ...
            'TimerFcn', @(~,~) app.applyPendingJointValue());
        start(app.SliderTimer);
    end
end
```
y el temporizador se encarga de aplicar ese valor de manera Segura:

```bash
function applyPendingJointValue(app)
    joints = app.robot.Joints();
    joints(app.PendingJointIndex) = app.PendingJointValue;
    app.robot.MoveJ(joints, false);
    updateToolPoseDisplays(app);

    app.SliderIdleCounter = app.SliderIdleCounter + 1;
    if app.SliderIdleCounter >= 5
        stop(app.SliderTimer);
        delete(app.SliderTimer);
        app.SliderTimer = [];
    end
end
```

Esto es esencial para evitar que los sliders interfieran con otros métodos de control (como botones o campos numéricos) y asegura que el sistema no quede en un estado “bloqueado” esperando una entrada de slider antigua.

5. Campos numéricos para articulaciones
Cada articulación también puede ser controlada manualmente por campos de texto (EditField7 a EditField12). Al ingresar un valor, el campo sincroniza su correspondiente slider y actualiza el robot. Esta doble vía de control (slider y campo) mejora la precisión y flexibilidad del usuario.

```bash
function Display3(app, event)  % Para articulación 3
    newValue = app.EditField9.Value;
    app.CodoSlider.Value = newValue;
    updateJointValue(app, 3, newValue);
end
```

6. Botones de desplazamiento cartesiano
Botones como “Derecha”, “Arriba”, “Adentro”, etc., permiten mover el TCP (herramienta) del robot en coordenadas relativas (XYZ). Internamente, el sistema calcula una nueva matriz de transformación sumando el desplazamiento deseado a la posición actual, y luego resuelve la cinemática inversa para generar una nueva configuración de articulaciones.

Si la solución de IK no es posible, se muestra un mensaje de error. Esto mantiene la operación segura y coherente con los límites del robot.

```bash
function MoveToolXYZ(app, dx, dy, dz)
    currentPose = app.robot.Pose();
    newPose = currentPose;
    newPose(1,4) = currentPose(1,4) + dx;
    ...
    newJoints = app.robot.SolveIK(newPose);
    app.robot.MoveJ(newJoints, false);
    updateToolPoseDisplays(app);
end
```

7. Visualización y actualización de la pose
La función updateToolPoseDisplays se encarga de mostrar continuamente la posición (X, Y, Z) y la orientación (RX, RY, RZ) del TCP del robot. Toma la matriz de pose actual del robot, la descompone en coordenadas cartesianas y ángulos RPY, y actualiza los campos visuales.

Esto asegura que el usuario siempre vea la posición real del robot después de cualquier acción (slider, campo numérico o botón).

```bash
function updateToolPoseDisplays(app)
    pose = app.robot.Pose();
    rpy = tr2rpy(pose(1:3,1:3)) * 180/pi;
    app.XEditField.Value = pose(1,4);
    app.RXEditField.Value = rpy(1);
    ...
end
```

8. Campos RX, RY, RZ: control de orientación
Los campos de rotación permiten modificar directamente la orientación de la herramienta. Al cambiar RX, por ejemplo, se mantiene la posición XYZ fija y se actualiza únicamente el ángulo de rotación sobre el eje X. Luego se vuelve a resolver la cinemática inversa para encontrar una configuración de articulaciones que logre esa orientación.

Cada campo incluye validaciones para evitar rotaciones inválidas (e.g., NaN o poses no alcanzables). Si ocurre un error, el valor del campo se revierte para proteger el sistema.

```bash
function RXEditFieldValueChanged(app, event)
    rx_new = app.RXEditField.Value;
    ...
    R = rpy2r(rx_new*pi/180, ry*pi/180, rz*pi/180);
    newPose(1:3,1:3) = R;
    jnts = app.robot.SolveIK(newPose);
    app.robot.MoveJ(jnts, false);
end
```

9. Control de posición absoluta (X, Y, Z)
Los campos XEditField, YEditField, ZEditField permiten que el usuario defina manualmente la posición absoluta del TCP. La orientación se conserva (extraída del estado actual del robot), y se calcula una nueva matriz de pose.

A partir de esta matriz, se resuelve IK para encontrar una nueva postura válida. Si no existe una solución, se muestra un error y el campo vuelve al valor anterior. Esto asegura que el robot siempre se mantenga dentro de límites físicos y cinemáticamente posibles.

```bash
% Obtener la pose actual directamente del robot
            currentPose = app.robot.Pose();
    
            % Extraer la posición y rotación actuales
            posX = currentPose(1,4);
            posY = currentPose(2,4);
            posZ = currentPose(3,4);
    
            % Convertir matriz de rotación a ángulos RPY
            rotm = currentPose(1:3,1:3);
            rpy = tr2rpy(rotm) * 180/pi;
            rx = rpy(1);
            ry = rpy(2);
            rz = rpy(3);
    
            % Usar el valor nuevo ingresado por el usuario solamente para X
            x = app.XEditField.Value;
            y = posY; 
            z = posZ;  
    
            % Crear nueva matriz de pose
            R_full = rpy2r(rx*pi/180, ry*pi/180, rz*pi/180);
            if size(R_full,1) == 4
                R = R_full(1:3,1:3);
            else
                R = R_full;
            end

            newPose = eye(4);
            newPose(1:3,1:3) = R;
            newPose(1:3,4) = [x; y; z];
            % Resolver cinemática inversa
            jnts = app.robot.SolveIK(newPose);
```

10. Función Home
El botón "Home" lleva al robot a una posición predefinida segura: [0, -90, -90, 0, 90, 0]. Esta posición inicializa todos los sliders y campos numéricos a valores conocidos, actualiza la visualización de pose y evita partir de una configuración inválida. Es clave para recuperación tras un error o para estandarizar el punto de inicio de operaciones.

```bash
function HomePressed(app, event)
    homePosition = [0, -90, -90, 0, 90, 0];
    app.robot.MoveJ(homePosition, false);
    updateToolPoseDisplays(app);
end
```
A continuación, se muestra la interfaz diseñada mediante AppDesigner.
![Matlab Interface](https://github.com/user-attachments/assets/9dd3581f-96d9-4a1d-8319-2c1e93b69396)

---

## ✅ Conclusión

A través de los resultados obtenidos, se puede asegurar que se cuenta con una herramienta de control de brazos robóticos bastante útil, realista y fiable. Si bien, la interfaz aún no cuenta con una robustez para poderse operar dentro de un ámbito industrial de programación, la aplicación cuenta con el potencial para poderse adaptar hasta el momento, en un ámbito de aprendizaje y enseñanza, al igual que en un ámbito de entrenamiento a operadores, debido al diseño integrado en la interfaz, donde se crean herramientas de control bastante similares a las de los Teach Pendat reales, que se utilizan a menudo en la industria. Aún hace falta integrar más herramientas de programación, como el marcar trayectorias o guardar puntos o targets, ya que hasta el momento, la interfaz solo permite manipular el TCP de robots y sus articulaciones, mediante el uso de distintas herramientas como lo son los sliders, botones y caja de texto editables. 

Nuestra integración, es una muestra de la posibilidad de controlar robots como el UR5 en la vida real, mediante una interfaz en MATLAB con conexión a RoboDK, optimizando el control y la programación. Además, el entorno de Matlab no solo permite, desarrollar mejoras de programación del robot, sino que puede ser un medio para la implementación de asistentes como una IA o red neuronal, que permita evaluar las acciones que está tomando el usuario para que en caso de detectar un posible error o fallo, pueda activar un sistema de paro de emergencia, o de optimizar alguna trayectoría o movimiento integrado en la programación de un robot mejorando de este forma aspectos como la seguridad, eficiencia y precisión en procesos automatizados donde se utilicen brazos robóticos. Además, gracias a su versatilidad, esta interfaz es capaz de adaptarse para varios modelos de brazos robóticos, lo cual prácticamente convierte la interfaz en un Teach Pendant universal o compatible para todos los brazos robóticos, sin la necesidad de tener que integrar los Teach Pendant de los fabricantes, que pueden llegar a elevar los costos en la implementación de brazos robóticos.

---

## 🔜 Mejoras Futuras

- {Hacer el programa más robusto, por ejemplo que pueda responder a instrucciones de manera más veloz sin trabarse en el proceso.
- Que pueda seguir movimientos de los sliders con más fidelidad.
- Programar una función que permita obtener las matrices de transformación homogénea de una acción en particular.
- Que se puedan guardar los puntos de una trayectoria para generar un programa de python,
- Hacer la conexión directamente con el robot en físico para que no solo pueda operar el teach-pendant en el RoboDK sino también en el software del robot real.
- Finalmente, extender la posibilidad de usos a más robots adecuando la cantidad de articulaciones para el robot seleccionado que no sea solo un UR5.}

---

## ⚠️ Advertencia

La única advertencia a tener en cuenta para esta versión del programa es que no es de un uso robusto y que los comandos tardan cierto tiempo en ejecutarse
por lo que muchas acciones en periodos cortos pueden llevar a un "timeout".

---

## 📚 Recursos Adicionales

- Librería de MATLAB destinada a la conexión entre RoboDK y MATLAB.
- Manuales de usuario de RoboDK.
- Recursos sobre simulación de robots industriales.

---

## 👥 Autores del Proyecto

- Miguel Angel Salazar, Juan Carlos Barba Salce, Hiram Alonso Ramón, Diego de Jesús Pastrana Blanco
- Institución: UDLAP

---
## 📬 Contacto

¿Tienes dudas o sugerencias?

- 📧 Correo electrónico: miguel.salazarso@udlap.mx
- 📧 Correo electrónico: juan.barbase@udlap.mx

---
