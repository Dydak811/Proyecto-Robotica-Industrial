# {Proyecto: Nombre del Proyecto Simulado}

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
{Para este proyecto se desarrollara una interfaz grafica en la plataforma de MatLab la cual tendra la función de enseñar al usuario como manipular el robot UR5 de Universal Robots por medio de una interfaz como si este fuera el Teach Pendant físico de la misma marca. Para esto utilizaremos la función de Design App para poder generar la GUI 
controlar al mismo robot, de igual forma vendrá con funciones de cinematica directa e inversa para poder generar un movimiento mas dinamico y limpio. Finalmente esta interfaz se podra conectar al software RoboDK para poder mostrar el control del movimiento del UR5.}

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

{En la actualidad, la automatización y la robótica industrial son clave para optimizar procesos en diversos sectores, destacando los robots colaborativos como el UR5 por su precisión, seguridad y facilidad de integración. Sin embargo, su programación aún representa un desafío, ya que suele requerir conocimientos técnicos avanzados y experiencia en lenguajes específicos, lo cual limita su accesibilidad para usuarios sin formación especializada. Aunque los teach pendants tradicionales permiten controlar estos robots, su uso puede resultar poco intuitivo y complejo, especialmente para principiantes o entornos educativos. 


Con el objetivo de hacer más accesible la interacción con el robot UR5, este proyecto propone el desarrollo de una interfaz gráfica interactiva utilizando MATLAB, apoyándose en su herramienta App Designer. Esta interfaz actúa como un teach pendant virtual, permitiendo al usuario controlar y programar el robot de forma visual, sencilla e intuitiva, sin necesidad de conocimientos avanzados en programación. Además, se establece una conexión con el entorno de simulación RoboDK, lo que posibilita la visualización en tiempo real de los movimientos del robot y la validación de trayectorias sin utilizar hardware físico.

A lo largo de este documento, se describe el proceso de desarrollo de esta herramienta, desde la definición del problema hasta las pruebas realizadas, pasando por el diseño de la interfaz, la integración con RoboDK y las funcionalidades implementadas. Finalmente, se discuten los beneficios, limitaciones y posibles mejoras futuras, destacando el valor de esta solución como herramienta educativa, de prototipado o de apoyo en la enseñanza de robótica industrial.}

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

Pasos detallados para instalar y configurar el entorno de simulación:

1. Instalar el simulador principal (Webots, Gazebo o RoboDK).
2. Instalar ROS Noetic (si se usa ROS):
   ```bash
   sudo apt update
   sudo apt install ros-noetic-desktop-full
   ```
3. Instalar dependencias y librerías necesarias específicas para cada simulador.

---

## 🛠️ Configuración del Proyecto

Instrucciones para clonar el repositorio, compilar, lanzar el mundo simulado y ejecutar los nodos o scripts:

```bash
git clone https://github.com/usuario/proyecto-simulacion.git
cd proyecto-simulacion
catkin_make
source devel/setup.bash
roslaunch proyecto_simulacion main.launch
```

---

## 💻 Programación

Estructura General

El código está construido con App Designer y contiene:

Propiedades privadas: Variables internas como RDK, robot, temporizadores y estados de articulaciones.

Funciones de conexión: Se conectan a RoboDK y permiten seleccionar el robot deseado.

Callbacks para sliders y botones: Permiten mover las articulaciones o la herramienta.

Funciones de actualización: Mantienen los displays sincronizados con los movimientos del robot.

Manejo de errores y reconexiones automáticas en caso de interrupción en la comunicación con RoboDK.

Componentes Principales del Programa

1. Conexión a RoboDK

ConnectButtonPushed: Establece la comunicación inicial con RoboDK. Abre la aplicación si está cerrada. Muestra un uialert como confirmación.

SelectRobotButtonPushed: Permite al usuario seleccionar manualmente el robot desde RoboDK.

2. Movimiento Articular

Cada articulación tiene:

Un slider (ValueChangingFcn): Cambia el ángulo en tiempo real.

Un display numérico (EditField): Muestra y permite editar manualmente el valor del ángulo.

Dos botones + y -: Permiten mover en saltos de 5 grados.

updateJointValue(jointIndex, newValue): Funciones centralizada que:

Actualiza el vector de articulaciones.

Mueve el robot.

Actualiza los valores del display y sliders.

Llama a updateToolPoseDisplays() para mantener actualizada la pose cartesiana.

3. Movimiento Cartesiano

Cuatro botones:

Izquierda, Derecha, Arriba, Abajo (+ adelante y atrás opcional)

MoveToolXYZ(dx, dy, dz):

Calcula una nueva matriz de transformación de la herramienta respecto a la base.

Resuelve la cinemática inversa para encontrar nuevos ángulos articulares.

Mueve el robot y actualiza sliders + displays.

4. Campos Editables de Pose

Campos para X, Y, Z, RX, RY, RZ:

Se actualizan con la posición real de la herramienta.

Al modificar manualmente cualquiera de ellos, se recalcula la cinemática inversa y se mueve el robot a esa posición deseada.

5. Home

HomeButton: Mueve el robot a una posición predefinida.

También actualiza los sliders y campos numéricos.

6. Sincronización Visual

Cada movimiento (articular o cartesiano) actualiza:

Sliders

Displays numéricos

Campos de pose cartesiana

updateToolPoseDisplays: Utiliza la función PoseTool() de RoboDK y tr2rpy() para mostrar los valores XYZ y orientaciones RX RY RZ en grados.

Manejo de errores y reconexiones

reconnectIfNeeded:

Si el robot pierde conexión (por ejemplo, RoboDK se cierra o hay un fallo de red), el sistema:

Intenta reconectar hasta un máximo de 3 veces.

Reestablece el objeto robot mediante búsqueda por nombre.

Muestra alertas solo si no se puede recuperar la conexión.

---

## ✅ Conclusión

{Resumen de lo que se logró construir, aprendizajes obtenidos y posibles mejoras o versiones futuras del proyecto.}

---

## 🔜 Mejoras Futuras

- {Hacer el programa más robusto, por ejemplo que pueda responder a instrucciones de manera más veloz sin trabarse en el proceso,
- Que pueda seguir movimientos de los sliders con más fidelidad,
- Programar una función que permita obtener las matrices de transformación homogénea de una acción en particular,
- Que se puedan guardar los puntos de una trayectoria para generar un programa de python,
- Hacer la conexión directamente con el robot en físico para que no solo pueda operar el teach-pendant en el RoboDK sino también en el software del robot real,
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

- {Miguel Angel Salazar, Juan Carlos Barba Salce, Hiram Alonso Ramón, Pastrana}
- {Afiliación o institución: UDLAP}
