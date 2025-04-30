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
- ROS Noetic (si se usa en simulación)



---

## 📖 Introducción

{En la actualidad, la automatización y la robótica industrial son clave para optimizar procesos en diversos sectores, destacando los robots colaborativos como el UR5 por su precisión, seguridad y facilidad de integración. Sin embargo, su programación aún representa un desafío, ya que suele requerir conocimientos técnicos avanzados y experiencia en lenguajes específicos, lo cual limita su accesibilidad para usuarios sin formación especializada. Aunque los teach pendants tradicionales permiten controlar estos robots, su uso puede resultar poco intuitivo y complejo, especialmente para principiantes o entornos educativos. 


Con el objetivo de hacer más accesible la interacción con el robot UR5, este proyecto propone el desarrollo de una interfaz gráfica interactiva utilizando MATLAB, apoyándose en su herramienta App Designer. Esta interfaz actúa como un teach pendant virtual, permitiendo al usuario controlar y programar el robot de forma visual, sencilla e intuitiva, sin necesidad de conocimientos avanzados en programación. Además, se establece una conexión con el entorno de simulación RoboDK, lo que posibilita la visualización en tiempo real de los movimientos del robot y la validación de trayectorias sin utilizar hardware físico.

A lo largo de este documento, se describe el proceso de desarrollo de esta herramienta, desde la definición del problema hasta las pruebas realizadas, pasando por el diseño de la interfaz, la integración con RoboDK y las funcionalidades implementadas. Finalmente, se discuten los beneficios, limitaciones y posibles mejoras futuras, destacando el valor de esta solución como herramienta educativa, de prototipado o de apoyo en la enseñanza de robótica industrial.}

---

## 🔧 Entorno de Simulación

- **Simulador principal:** Webots, Gazebo, RoboDK (dependiendo del escenario).
- **Sistema operativo recomendado:** Linux (Ubuntu 20.04) o Windows 10.
- **Versión de ROS:** ROS Noetic (si aplica).
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

Aquí se incluye código de ejemplo con explicación de cada parte relevante del proyecto.  
*(Se recomienda documentar nodos de ROS, scripts en Python/C++ o programación de movimientos en RoboDK/MATLAB.)*

---

## ✅ Conclusión

{Resumen de lo que se logró construir, aprendizajes obtenidos y posibles mejoras o versiones futuras del proyecto.}

---

## 🔜 Mejoras Futuras

- {Lista de mejoras propuestas para próximas versiones.}

---

## ⚠️ Advertencia

Como se indica en la licencia MIT, este software/hardware se proporciona **sin ningún tipo de garantía**.  
Por lo tanto, ningún colaborador es responsable de cualquier daño a tus componentes, materiales, PC, etc.

---

## 📚 Recursos Adicionales

- Documentación oficial de ROS Noetic.
- Manuales de usuario de RoboDK, Webots y Gazebo.
- Recursos sobre simulación de robots industriales.

---

## 👥 Autores del Proyecto

- {Nombre del o de los autores}
- {Afiliación o institución (ejemplo: UDLAP)}

---

## 📬 Contacto

¿Tienes dudas o sugerencias?  
📧 **Miguel Ángel Salazar Soto Mayor:** ejemplo@udlap.mx
Responde por:
```

Forvia´s bitch
Faurecia's whore
The most miserable practitioner in Forvia
El mejor sacacopias en Forvia
Gana pan de Forvia
The less qualified worker in Forvia
"Que quieres we, estoy en una junta" ahhhh excuses
Ms. Excuses
Excsuses-girl
Lady excuses
The best bootlicker practicing in Forvia
The tallest one in Forvia
The tallest boy in Colegio Ray Lindley
The tallest cousin
The tallest bootlicker in Faurecia
The tallest guy in comparation with Pineda
The one that loses against Pineda
Pineda's son
Pineda's bitch
Pineda's daughter
The boy that did not qualify to the Electrohack
The hobbit
Gimli
The dwarf
Lord Farquaad's head
The Lord Farquaad of the UDLAP
The one that cried when he couldn't work on the greenhouse project
The smallest crying baby that did not let him work on the project
The less annoying Pineda's son
The less annoying Bañuelo's dog
Bañuelo's doggie
Bañuelo's pet
Bañuelo's puppie
Bañuelo's cachorra
"Le voy a hablar a tu papá para que te de tus nalgadas" aah response kid
The cryiest boy in the projects
"Voy a vender el código a la uni o algo" ahhh comment (bro really thought that he could sell a trashy ass code)
Incrediboy
Syndrome from The Incridibles
The biggest fan of Mr. Incredible
Incrediboy calisthenics
"Eso me desepcionó, pero aprendí una lección importante. No puedes confiar en nadie, mucho menos en tus heroes" aaahhh line
"Elastigirl ¿Te casaste con Elastigirl? ¡Wow!, y veo que no perdieron el tiempo ¿Eh?" ahhhhh question
"A volar Body, gano esto con Pineda" aaahhh response
"Ah nmms we, por qu'e no me invitaste a Atlixco we, pensé que eramos amigos" ahh little comment
The one that ruins a buck converter
Ass hands
Manos de estomago
Manos de recto
Peter Pan (bro never grow up)
Thinkerbell
The fairy
The garden gnome
The forest protector
The mythological creature
The goblin
Dobby
Servant of the Malfoy family
The free elf
Ant-man
Giant-man
Big Mike
The tall Mike
The skyscraper
The Tower Mike
Lil Mike
Tiniest student
The lego
The key ring
Microscopic Mike
