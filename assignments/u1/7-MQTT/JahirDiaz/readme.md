# 📘 Resumen de *MQTT & MQTT 5 Essentials* (HiveMQ)

## 🚀 1. ¿Qué es MQTT?
**MQTT (Message Queuing Telemetry Transport)** es un **protocolo de mensajería ligero y eficiente**, diseñado para dispositivos con recursos limitados y redes poco confiables.  
- 📅 Creado en **1999** por Andy Stanford-Clark (IBM) y Arlen Nipper (Arcom).  
- 🌐 Popular en el **Internet de las Cosas (IoT)**: sensores, domótica, autos conectados, industria, apps móviles.  
- 📜 Estandarizado en **2014 (OASIS)** y ampliado en **2019 con MQTT 5**.  

✨ **Características principales**:  
- Ligero (mínimo overhead).  
- Fácil de implementar en dispositivos pequeños.  
- Data-agnostic (envía texto, JSON, binarios, imágenes).  
- Escalable a millones de conexiones.  

---

## 🔗 2. Arquitectura Publish/Subscribe
En lugar del modelo cliente-servidor, MQTT usa **publish/subscribe**.  

- **Publisher (publicador):** envía mensajes.  
- **Subscriber (suscriptor):** recibe mensajes de interés.  
- **Broker:** el intermediario que recibe y reenvía mensajes.  

🔑 **Ventajas del pub/sub**:  
- **Desacoplamiento espacial:** no necesitan conocerse.  
- **Desacoplamiento temporal:** no requieren estar conectados al mismo tiempo.  
- **Asincronía:** trabajan en paralelo sin bloquearse.  

---

## 💻 3. Clientes y Broker
- **Cliente MQTT:** cualquier dispositivo con una librería MQTT (Arduino, móvil, app, servidor). Puede publicar, suscribirse o ambos.  
- **Broker MQTT:** el corazón del sistema. Maneja miles de conexiones, filtra mensajes, guarda sesiones, autentica clientes y se conecta a sistemas externos.  

---

## 📨 4. Topics y Mensajes
Los mensajes viajan a través de **topics** (temas).  
- Ejemplo: `casa/salon/temperatura`.  
- **Wildcards (comodines):**  
  - `+` → un solo nivel (`casa/+/temperatura`).  
  - `#` → múltiples niveles (`casa/#`).  
- Los topics se crean dinámicamente, sin configuración previa.  

⚡ **Buenas prácticas**:  
- Evitar `/` inicial.  
- No usar espacios.  
- Mantenerlos cortos y claros.  

---

## 📊 5. Calidad de Servicio (QoS)
Define la **garantía de entrega** de los mensajes:  

| Nivel | Nombre          | Garantía                    | Uso típico |
|-------|-----------------|-----------------------------|------------|
| 0     | At most once    | "Fire and forget", sin ACK  | Datos no críticos, sensores frecuentes |
| 1     | At least once   | Confirmación (PUBACK), puede duplicarse | Uso más común |
| 2     | Exactly once    | Entrega única con handshake | Sistemas críticos |

---

## 🛠️ 6. Funciones útiles de MQTT
- **Sesiones persistentes:** guardan suscripciones y mensajes cuando el cliente está desconectado.  
- **Retained Messages:** el broker almacena el último mensaje de un topic.  
- **Last Will and Testament (LWT):** notifica desconexiones inesperadas.  
- **Keep Alive:** confirma que la conexión sigue activa (PINGREQ/PINGRESP).  
- **MQTT sobre WebSockets:** permite usarlo desde navegadores.  

---

## ⚡ 7. Novedades en MQTT 5
MQTT 5 amplía las capacidades para **sistemas IoT a gran escala**:  

- 🕒 **Session & Message Expiry:** caducidad de sesiones y mensajes.  
- ❌ **Reason Codes / Negative ACKs:** mejor feedback de errores.  
- 🏷️ **User Properties:** metadatos personalizados.  
- 👥 **Shared Subscriptions:** balanceo de carga entre clientes.  
- 📑 **Payload Format Indicator:** define formato del mensaje (JSON, texto, binario).  
- 🔄 **Request-Response Pattern:** comunicación estilo petición-respuesta.  
- 🔢 **Topic Aliases:** reemplaza topics largos por IDs cortos.  
- 🔐 **Enhanced Authentication:** soporte para OAuth, Kerberos, etc.  
- 📉 **Flow Control:** limita mensajes para no saturar clientes pequeños.  

---

## ✅ 8. ¿Por qué usar MQTT?
- Ideal para **IoT y M2M**.  
- Funciona bien en **redes inestables**.  
- Muy eficiente en **batería y ancho de banda**.  
- **Escalable** a millones de dispositivos.  
- Compatible con **apps móviles y sistemas en la nube**.  

---

## 🎯 Conclusión
MQTT es el **estándar de facto en IoT**:  
- Simplicidad y ligereza para dispositivos pequeños.  
- Robusto y escalable para arquitecturas en la nube.  
- Con **MQTT 5**: más seguridad, control y flexibilidad.  

> 🌟 En resumen: **MQTT = mensajería ligera y potente para el IoT del presente y futuro.**

---
