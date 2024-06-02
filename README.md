# Firebase Push Notifications on Android (FCM + Backend)

Esta es una aplicación de mensajería sencilla que utiliza Firebase Cloud Messaging (FCM) para enviar y recibir notificaciones push. La aplicación está construida en Android Studio utilizando Kotlin y Jetpack Compose, y se conecta a un servidor backend construido con Flask en Python.

## Características

- **Enviar Notificaciones Push**: Envía notificaciones push a dispositivos específicos utilizando FCM.
- **Suscripción a Temas**: Suscribe dispositivos a temas para enviar notificaciones broadcast.
- **Interfaz de Usuario Moderna**: Utiliza Jetpack Compose para una UI moderna y responsiva.
- **Temas Dinámicos**: Adapta el esquema de colores al modo claro/oscuro del sistema.

## Requisitos Previos

- Android Studio
- Cuenta de Firebase
- Python 3
- Pip (gestor de paquetes de Python)

## Instalación

### Configuración del Backend

1. **Clonar el repositorio**:
    ```bash
    git clone https://github.com/Dino-E/firebase-push-notifications.git
    cd firebase-push-notifications
    ```

2. **Instalar dependencias de Python**:
    ```bash
    pip install Flask firebase-admin
    ```

3. **Configurar Firebase**:
    - Descarga el archivo `serviceAccountKey.json` desde la consola de Firebase y colócalo en el directorio del servidor.

4. **Ejecutar el servidor**:
    ```bash
    python server.py
    ```

### Configuración de la Aplicación Android

1. **Abrir el proyecto en Android Studio**:
    - Abre el directorio del proyecto `firebase-push-notifications` en Android Studio.

2. **Configurar Firebase en la aplicación**:
    - Sigue [estas instrucciones](https://firebase.google.com/docs/android/setup) para añadir Firebase a tu proyecto Android.
    - Descarga el archivo `google-services.json` y colócalo en el directorio `app`.

3. **Modificar la URL del servidor en `ChatViewModel.kt`**:
    - Asegúrate de que la URL del servidor en `ChatViewModel.kt` apunte a la dirección IP y puerto correctos de tu servidor backend.

4. **Ejecutar la aplicación**:
    - Conecta un dispositivo Android o utiliza un emulador y ejecuta la aplicación desde Android Studio.

## Uso

1. **Iniciar la Aplicación**:
    - La primera vez que inicies la aplicación, se te pedirá que ingreses un token remoto para enviar notificaciones a dispositivos específicos.

2. **Enviar Mensajes**:
    - Ingresa un mensaje en la pantalla de chat y presiona el botón de enviar para enviar una notificación push al dispositivo especificado por el token.

3. **Notificaciones Broadcast**:
    - Los dispositivos suscritos al tema "chat" recibirán notificaciones broadcast.

## Estructura del Proyecto

- **app/src/main/java/com/plcoding/firenotifimessenger/**:
    - **ui/theme/Color.kt**: Define los colores de la aplicación.
    - **ui/theme/Theme.kt**: Configura los temas de la aplicación.
    - **ui/theme/Type.kt**: Define la tipografía de la aplicación.
    - **ChatScreen.kt**: Pantalla principal de chat.
    - **ChatState.kt**: Estado del chat.
    - **ChatViewModel.kt**: Lógica del chat y gestión del estado.
    - **EnterTokenDialog.kt**: Diálogo para ingresar el token remoto.
    - **FcmApi.kt**: Interfaz de comunicación con el servidor backend.
    - **MainActivity.kt**: Actividad principal de la aplicación Android.
    - **PushNotificationService.kt**: Maneja las notificaciones push.
    - **SendMessageDto.kt**: Objeto de transferencia de datos para enviar mensajes.

- **server.py**: Servidor backend construido con Flask.

## Licencia

Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo [LICENSE](LICENSE) para obtener más detalles.
