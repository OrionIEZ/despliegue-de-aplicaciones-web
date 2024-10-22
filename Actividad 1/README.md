# Respuestas a las Preguntas

## 4. ¿A qué puerto se reciben normalmente las peticiones del protocolo HTTP? ¿A qué capa del modelo TCP/IP se encuentra el protocolo HTTP? ¿Y los protocolos TCP, UDP, e IP?

**Puertos estándar para HTTP:**

- **HTTP (no seguro):** Las peticiones del protocolo HTTP se reciben normalmente en el **puerto 80**.
- **HTTPS (HTTP seguro):** Las peticiones HTTPS se reciben en el **puerto 443**.

**Capas del modelo TCP/IP:**

El modelo TCP/IP se compone de cuatro capas:

1. **Capa de Aplicación:**
   - **HTTP** se encuentra en la **capa de Aplicación**.
   - Protocolos en esta capa: HTTP, HTTPS, FTP, SMTP, DNS, etc.

2. **Capa de Transporte:**
   - **TCP (Transmission Control Protocol):** Protocolo orientado a la conexión que proporciona transmisión fiable de datos.
   - **UDP (User Datagram Protocol):** Protocolo no orientado a la conexión que permite transmisión de datos sin confirmación.

3. **Capa de Internet (Red):**
   - **IP (Internet Protocol):** Responsable del direccionamiento y enrutamiento de paquetes entre dispositivos.
   - Protocolos en esta capa: IP, ICMP, ARP.

4. **Capa de Acceso a la Red (Enlace):**
   - Maneja la transmisión física de datos a través de la red.
   - Protocolos: Ethernet, Wi-Fi, etc.


## 5. ¿Cuál es el significado de la siguiente respuesta de un servidor?

HTTP/1.1 302 Found Location: http://www.example.com/test/index2.php

**Explicación:**

- **Código de estado HTTP 302 Found:**
  - El código **302** es una respuesta de redirección que indica que el recurso solicitado se ha movido temporalmente a una nueva ubicación.
  - El cliente debe realizar una nueva solicitud a la URL especificada para obtener el recurso.

- **Header `Location`:**
  - La cabecera `Location` proporciona la nueva URL a la que el cliente debe redirigirse.
  - En este caso: `http://www.example.com/test/index2.php`.


El servidor está indicando que el recurso solicitado ha sido temporalmente movido a otra dirección y sugiere al cliente que haga una nueva solicitud a la URL proporcionada. Esto es común cuando una página ha sido temporalmente reubicada o durante procesos de autenticación y flujo de navegación.


## 6. Utilizando el filtro de captura para la interfaz de red de Wireshark, analiza la petición al host: www.google.com. Mostrando la cabecera IP, la dirección IP de tu ordenador y la del servidor. Comprueba que, poniendo esa IP en el navegador, accedas a Google.

**Pasos para el análisis:**

1. **Abrir Wireshark y seleccionar la interfaz de red:**
   - Inicia Wireshark y selecciona la interfaz de red que estás utilizando (por ejemplo, Wi-Fi o Ethernet).

2. **Aplicar un filtro de captura:**
   - Puedes aplicar un filtro para capturar solo el tráfico HTTP:
     ```
     tcp port 80
     ```
   - O capturar todo el tráfico y luego filtrar.

3. **Iniciar la captura de paquetes:**
   - Haz clic en el botón de inicio para comenzar a capturar paquetes.

4. **Realizar la petición a www.google.com:**
   - En tu navegador web, visita `http://www.google.com`.

5. **Detener la captura:**
   - Una vez cargada la página, detén la captura en Wireshark.

6. **Aplicar un filtro de visualización:**
   - Para filtrar los paquetes relacionados con Google:
     ```
     http.host contains "google.com"
     ```
   - O por dirección IP si la conoces:
     ```
     ip.addr == [dirección IP de Google]
     ```
 