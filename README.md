### 🧠 Asistente Virtual con Patrones de Diseño – Java + Swing
## 📌 Descripción General

---

Este proyecto implementa un sistema de asistentes virtuales personalizables en Java, usando el entorno NetBeans y aplicando cuatro patrones de diseño:
👉 Prototype, Adapter, Iterator y Singleton.

Se incluye una interfaz gráfica con Swing que permite:

Clonar asistentes virtuales.

Simular conversaciones paso a paso.

Integrarse con un sistema de clientes antiguo.

Generar respuestas con un motor de IA centralizado.

## 🧩 Patrones de Diseño Usados
#1. 🧬 Prototype – Clonación de Asistentes
Permite crear nuevos asistentes virtuales copiando uno base y personalizándolo (nombre, tono, etc.).

Clase clave: BotSoporteEstandar

Interfaz: AsistenteVirtual

Ubicación: prototype/

Ejemplo:

```java
AsistenteVirtual base = new BotSoporteEstandar();
AsistenteVirtual clon = base.clonar();
clon.personalizar("VirtualBotX", "Informal");
```
## 2. 🔌 Adapter – Adaptador para CRM Antiguo
Permite integrar un sistema antiguo que entrega datos en formato XML.

Clase adaptada: CRMXmlAntiguo

Interfaz moderna: ICRM

Adaptador: AdaptadorCRM

Ubicación: adapter/

Ejemplo:

```java
ICRM crm = new AdaptadorCRM();
String nombre = crm.obtenerNombreCliente("123");
```
## 3. 🧭 Iterator – Flujo de Diálogo del Asistente
Permite recorrer paso a paso los mensajes del asistente, útil para pruebas y depuración.

Clase de nodo: NodoDialogo

Iterable: FlujoDialogo

Ubicación: iterator/

Ejemplo:

```java
FlujoDialogo flujo = new FlujoDialogo(nodoInicio);
for (NodoDialogo paso : flujo) {
    System.out.println(paso.pregunta);
}
```
## 4. 🧠 Singleton – Motor de IA
Asegura que solo exista una única instancia del motor de respuestas IA.

Clase: MotorIA

Ubicación: singleton/

Ejemplo:

```java
MotorIA ia = MotorIA.getInstancia();
String respuesta = ia.generarRespuesta("Hola IA");
```
## 🖼 Interfaz Gráfica (Swing)
La aplicación contiene 2 ventanas:

VentanaPrincipal.java
Botón Crear Asistente: clona y personaliza un bot.

Botón Ver Flujo de Diálogo: muestra pasos del asistente.

Botón Probar CRM Adapter: integra sistema antiguo.

Botón Llamar Motor IA: usa Singleton para respuesta.

VentanaFlujoDialogo.java
Muestra el flujo de conversación de un asistente virtual utilizando el patrón Iterator.

---

## 🚀 Cómo Ejecutar el Proyecto
Abre NetBeans.

Crea un nuevo proyecto Java con Ant o Maven (Java Application).

Copia las carpetas prototype/, adapter/, iterator/, singleton/ y gui/.

Crea el archivo Main.java en el paquete principal.

Ejecuta Main.java.

---

## 📦 Dependencias
Solo se utilizan bibliotecas estándar de Java:

javax.swing.* (interfaz gráfica)

org.w3c.dom.* y javax.xml.parsers.* (para el Adapter con XML)

---

## 📚 Ejemplo de Caso de Uso
Una empresa quiere crear su asistente "VirtualBotX", similar al asistente base, pero con tono informal. Quiere integrarlo con su antiguo sistema de clientes y ver cómo respondería paso a paso. El sistema permite:

Clonar el asistente (Prototype).

Mostrar el flujo (Iterator).

Extraer datos de su sistema (Adapter).

Generar respuestas IA (Singleton).

---

## 📌 Conclusión
Este proyecto es una demostración funcional e interactiva de patrones de diseño clásicos aplicados a un caso real y moderno: asistentes virtuales personalizados.
Ideal para enseñar patrones de forma visual, o para evolucionar a una versión web o con IA real.
