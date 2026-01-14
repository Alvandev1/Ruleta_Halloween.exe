# 🎃 Túnel del Terror - Ruleta de Halloween

> **Supuesto Práctico:** Desarrollo y Distribución de una Aplicación de Escritorio.

## 📋 Descripción
Proyecto del módulo 11 de Desarrollo de Interfaces. Consiste en una aplicación gráfica (JavaFX) que simula una ruleta de premios para Halloween, preparada profesionalmente para su distribución en entornos Windows.

El objetivo principal de este repositorio es demostrar el **ciclo completo de despliegue (deployment)**, generando un instalador que permite ejecutar la aplicación en ordenadores que **no tienen Java instalado**.

## 🚀 Características de la Distribución

Para cumplir con los requisitos de portabilidad y facilidad de uso, se ha implementado la siguiente arquitectura:

1.  **Independencia del Sistema (Bundled JRE):**
    * La aplicación incluye su propia carpeta `jre` (Java Runtime Environment) en el directorio de instalación.
    * **Ventaja:** El usuario final no necesita instalar Java ni configurar variables de entorno.

2.  **Ejecutable Nativo (`miapp.exe`):**
    * Generado con **Launch4j**.
    * Encapsula el archivo `tunel2.jar`.
    * Se ejecuta en modo gráfico (sin consola negra de fondo).
    * Utiliza un icono personalizado (`1-fb3c61b3.ico`) para mejorar la identidad visual.

3.  **Instalador Profesional (`mysetup.exe`):**
    * Creado con **Inno Setup**.
    * Empaqueta automáticamente el ejecutable, el JAR y la carpeta `jre`.
    * Gestiona la creación de accesos directos y permite una desinstalación limpia desde el Panel de Control.

## 📂 Estructura de Archivos de Distribución

El proyecto genera los siguientes artefactos clave para el despliegue:

| Archivo / Carpeta | Descripción |
| :--- | :--- |
| **`miapp.exe`** | Ejecutable nativo de Windows configurado con Launch4j. Es el punto de entrada para el usuario. |
| **`tunel2.jar`** | La lógica de la aplicación (Fat JAR generado con Maven Shade). |
| **`jre/`** | **(Obligatorio)** Carpeta que contiene el entorno de ejecución de Java embebido. Vital para la portabilidad. |
| **`mysetup.exe`** | El instalador final que se entrega al cliente. Contiene todo lo anterior comprimido. |
| **`ruletahalloween.iss`** | Script de configuración de Inno Setup utilizado para compilar el instalador. |
| **`launch4j.xml`** | Archivo de configuración para la generación del .exe. |

## 🛠️ Tecnologías y Herramientas

* **Lenguaje:** Java 25
* **Interfaz:** JavaFX
* **Construcción:** Apache Maven (Maven Shade Plugin)
* **Wrapper:** Launch4j 3.50
* **Instalador:** Inno Setup Compiler 6

## 💿 Instalación y Prueba

1.  Descargue el archivo **`mysetup.exe`** desde la sección de **Releases** de este repositorio.
2.  Ejecute el instalador y siga las instrucciones del asistente.
3.  Al finalizar, encontrará un acceso directo en el escritorio con el icono de la aplicación.
4.  ¡Ejecute el juego! (No requiere tener Java preinstalado en el equipo).

---
**Autor:** Alfonso Ivan Barrios Buaiz
**Módulo:** Desarrollo de Interfaces
