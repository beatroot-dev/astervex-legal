# Política de privacidad de Astervex

Fecha de entrada en vigor: 23 de agosto de 2026

Astervex es desarrollado y publicado por Dmitrii Kryzhanovskii. Beatroot Development es el nombre de proyecto y marca utilizado para Astervex. Esta política explica qué datos almacena Astervex y cómo se usan esos datos.

Contacto: beat.root.dev@icloud.com

## Datos que almacena Astervex

Astervex almacena los siguientes datos para proporcionar el juego:

- Datos de cuenta: Astervex Profile ID, identificadores internos de cuenta, datos de verificación de contraseña con hash y sal aleatoria única, metadatos de sesión activa, nombre del dispositivo e identificadores de dispositivo y sesión usados para iniciar sesión y evitar conflictos de cuenta entre dispositivos.
- Datos de juego: perfil del jugador, apodo del piloto, personaje seleccionado, puntuación máxima, partidas jugadas, saldos, contenido desbloqueado, inventario, configuración de la nave, progreso del mapa y estado guardado relacionado con el juego.
- Datos de entrega de compras: identificadores de transacciones de StoreKit, identificadores de transacciones originales, identificadores de productos, cantidad de cristales, fecha de compra y fecha de entrega. Estos datos se usan para entregar compras dentro de la app y evitar entregas duplicadas.
- Datos de eliminación de cuenta: después de eliminar una cuenta, Astervex conserva un marcador mínimo con el Profile ID, los identificadores internos de la cuenta y del perfil, el identificador de la operación de eliminación y la fecha de eliminación. No contiene progreso del juego, datos de verificación de contraseña ni datos de sesión activa. El marcador se reemplaza si el usuario crea explícitamente una cuenta nueva con el mismo Profile ID.

Astervex no solicita nombre real, dirección de correo electrónico, número de teléfono, ubicación precisa, contactos, fotos, cámara, micrófono, datos de salud ni datos de tarjetas de pago.

## Cómo se recopilan y almacenan los datos

- Para una cuenta estándar, el usuario introduce el Profile ID y la contraseña al crearla o iniciar sesión. Si el usuario elige Jugar como invitado, Astervex crea o restaura una cuenta de invitado completa en la base de datos privada de CloudKit del usuario y genera una contraseña criptográficamente aleatoria durante la creación. Astervex no almacena la contraseña de ningún tipo de cuenta; solo conserva un verificador derivado mediante hash y una sal aleatoria única. La contraseña generada para el invitado no se muestra ni se guarda como texto sin cifrar.
- Los datos de juego se crean a partir de las acciones y del progreso del usuario en el juego.
- La app genera los identificadores de dispositivo y sesión. iOS proporciona el nombre del dispositivo, que se usa únicamente para mostrar la sesión activa al usuario y resolver conflictos de sesión.
- Los datos de entrega de compras se reciben de Apple StoreKit cuando el usuario inicia o restaura una compra dentro de la app.

Las cachés de cuenta y juego, la configuración, el estado de autenticación activa y el estado pendiente de recuperación de compras o eliminaciones se almacenan localmente en el almacenamiento privado de la app. El identificador de dispositivo generado por la app también se guarda en el llavero de iOS para mantener la coherencia de las sesiones entre ejecuciones y reinstalaciones. Los registros de cuenta, juego, entrega de compras y marcadores de eliminación se sincronizan con la base de datos privada de CloudKit del usuario cuando iCloud está disponible.

## Cómo utiliza Astervex los datos

Astervex utiliza los datos almacenados únicamente para la funcionalidad de la app:

- crear e iniciar sesión en una cuenta de juego de Astervex;
- sincronizar el progreso guardado del juego con iCloud mediante Apple CloudKit;
- mantener una sesión activa de cuenta coherente entre dispositivos;
- guardar el progreso del juego, saldos, inventario y contenido desbloqueado;
- entregar compras dentro de la app mediante StoreKit y evitar la entrega duplicada de cristales.

Astervex no utiliza estos datos para publicidad de terceros, publicidad del desarrollador, intercambio con data brokers ni seguimiento entre apps.

## Intercambio de datos y servicios de Apple

Astervex no vende datos de usuarios ni los comparte con servicios de publicidad, análisis o data brokers. Los datos solo se procesan mediante servicios de Apple necesarios para la funcionalidad de la app: CloudKit para el almacenamiento privado en iCloud y StoreKit/App Store para las compras dentro de la app. Apple procesa estos datos conforme a sus políticas de privacidad, condiciones del servicio y protecciones de seguridad. Astervex no autoriza a Apple ni a ningún otro proveedor de servicios a utilizar los datos de la app Astervex para fines incompatibles con esta política.

## iCloud y CloudKit

Astervex utiliza Apple CloudKit para almacenar registros de cuenta de juego, datos de juego, registros de entrega de compras y marcadores de eliminación de cuenta en la base de datos privada de iCloud del usuario. Esto permite que la misma cuenta de Astervex y el progreso funcionen en los dispositivos del usuario con sesión iniciada en iCloud e impide que un dispositivo sin conexión con datos antiguos restaure una cuenta eliminada.

Los datos almacenados o procesados por los servicios de Apple también están sujetos a las políticas de privacidad de Apple y a los términos de iCloud.

## Compras dentro de la app

Astervex utiliza Apple StoreKit para las compras dentro de la app. Apple procesa el pago y la infraestructura de transacciones de App Store. Astervex almacena registros limitados de entrega de compras, como identificadores de transacción e identificadores de producto, para que los cristales comprados se entreguen una sola vez y no se dupliquen.

Astervex no almacena números de tarjetas de pago ni otros datos de métodos de pago.

## Eliminación de cuenta

El usuario puede solicitar la eliminación desde la interfaz de gestión de cuentas dentro de Astervex. No es necesario enviar un correo electrónico ni visitar un sitio web externo.

Cuando la eliminación de cuenta se completa correctamente en la app mientras iCloud está disponible, Astervex elimina el registro de la cuenta de juego, el registro del perfil del jugador, los registros conocidos del ledger de entrega de compras de esa cuenta y los datos de cuenta/perfil almacenados localmente en caché en el dispositivo. Astervex conserva el marcador mínimo descrito anteriormente en la base de datos privada de CloudKit del usuario para impedir que una copia obsoleta de la cuenta en otro dispositivo vuelva a crear la cuenta eliminada.

Si iCloud o la red no están disponibles temporalmente, la eliminación no se considera completada y los datos locales de cuenta/perfil se conservan para que el usuario pueda volver a intentarlo. Si la interrupción ocurre después de iniciar la eliminación, Astervex conserva una operación local duradera de recuperación y reanuda la limpieza restante cuando el backend vuelve a estar disponible.

Eliminar una cuenta de Astervex no elimina el historial de compras de App Store, los registros de transacciones de StoreKit, las copias de seguridad de iCloud ni otros registros controlados por Apple.

## Conservación de datos y opciones del usuario

- Los registros de cuenta y juego se conservan mientras exista la cuenta de Astervex y se eliminan como se describe anteriormente cuando finaliza la eliminación de la cuenta.
- Los registros de entrega de compras se conservan mientras sean necesarios para entregar compras y evitar entregas duplicadas; los registros conocidos vinculados a la cuenta se eliminan cuando finaliza la eliminación de la cuenta.
- Las operaciones locales de recuperación se conservan únicamente mientras sean necesarias para completar o recuperar la entrega de una compra o la eliminación de una cuenta y se eliminan cuando se resuelve la operación.
- El marcador de eliminación de cuenta se conserva en la base de datos privada de CloudKit del usuario hasta que este crea explícitamente una cuenta nueva con el mismo Profile ID; en ese momento, el marcador se reemplaza.
- El identificador de dispositivo generado por la app no es específico de una cuenta y permanece en el llavero de iOS después de eliminar una cuenta individual de Astervex. Se usa únicamente para mantener la coherencia de las sesiones y no se utiliza para seguimiento. El usuario puede solicitar ayuda relacionada con este identificador mediante la dirección de contacto indicada anteriormente.

Astervex no recopila datos opcionales de publicidad o seguimiento, por lo que no existe consentimiento de publicidad o seguimiento que revocar. El usuario puede detener la recopilación futura de datos de cuenta y juego eliminando la cuenta y dejando de usar la app. Las preguntas o solicitudes de ayuda con la eliminación pueden enviarse a la dirección de contacto indicada anteriormente.

## Niños

Astervex no está diseñado para solicitar información personal de contacto a niños. Si crees que un niño ha proporcionado información personal mediante Astervex, contacta con beat.root.dev@icloud.com.

## Cambios

Esta política puede actualizarse cuando Astervex cambie sus prácticas de datos. La fecha de entrada en vigor indicada arriba se actualizará cuando cambie la política.
