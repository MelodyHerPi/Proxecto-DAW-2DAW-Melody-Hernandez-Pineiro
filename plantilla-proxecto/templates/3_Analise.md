# Requerimientos del sistema

- [Requerimientos del sistema](#requerimientos-del-sistema)
  - [1- Descrición General](#1--descrición-general)
  - [2- Funcionalidades](#2--funcionalidades)
  - [3- Tipos de usuarios](#3--tipos-de-usuarios)
  - [4- Contorno operacional](#4--contorno-operacional)
  - [5- Normativa](#5--normativa)
  - [6- Mejoras futuras](#6--mejoras-futuras)


## 1- Descrición General

**All Dance Together - Encuentra grupos de kpop dance cover a tu alrededor.**
Este proyecto nace con la ilusión de crear un punto de encuentro entre la comunidad "kpoper" de Galicia en un mismo espacio digital.
La idea es sencilla pero útil, ya que no existe dicha plataforma: centralizar en una sola web toda la información de grupos y solistas locales, contando con fichas de presentación, foros, sistema de noticias, acceso a las redes sociales, alertas de eventos próximos a ti, ¡incluso podrás crear tus propias quedadas y concursos! 
El concepto clave del proyecto es la unión de la comunidad. 

## 2- Funcionalidades

| Acción | Descripción | Entrada | Proceso | Salida |
| :--- | :--- | :--- | :--- | :--- |
| **Registro de Usuario/Grupo** | Creación de cuenta en la plataforma. | Datos de perfil (nombre, zona, estilo). | Validación y almacenamiento en MariaDB. | Cuenta activa y acceso al panel. |
| **Gestión de Ficha/Perfil** | Alta y edición de la ficha de presentación. | Fotos, descripción, redes sociales. | Procesamiento de archivos y actualización DB. | Perfil público visible para la comunidad. |
| **Búsqueda de Integrantes** | Localizar bailarines por cercanía o rol. | Filtros (ciudad, estilo, nivel). | Consulta a la BD con lógica de proximidad. | Listado de perfiles coincidentes. |
| **Publicación de Eventos** | Dar de alta concursos o quedadas. | Datos del evento (fecha, lugar, tipo). | Verificación de datos por el organizador. | Evento publicado en la agenda global. |
| **Sistema de Notificaciones** | Alertas de eventos próximos al usuario. | Ubicación del usuario y preferencias. | Cruce de datos fecha/localización en tiempo real. | Notificación visual en el panel del usuario. |
| **Participación en Foros** | Interacción en hilos de discusión. | Mensajes, hilos y comentarios. | Registro de la entrada y asociación al usuario. | Hilo de conversación actualizado. |
| **Administración de Contenido** | Control de seguridad y moderación. | Reportes de usuarios o peticiones de baja. | Borrado de datos o baneo de cuentas. | Base de datos depurada y segura. |

## 3- Tipos de usuarios
El acceso a las funcionalidades del sistema se segmenta en cuatro roles principales, definidos por sus permisos y objetivos dentro de la plataforma:

- **Usuario Anónimo (Visitante):** Cualquier persona que accede a la web sin autenticarse. Su acceso es de solo lectura. Puede consultar el calendario de eventos públicos, ver fichas de grupos y leer hilos del foro, pero no puede interactuar ni publicar contenido.

- **Usuario Registrado (Bailarín/Grupo):** Usuario que ha validado su cuenta. Tiene acceso a su panel de gestión personal donde puede crear y editar su ficha de artista, participar activamente en el foro (escribir hilos y comentarios) y utilizar el buscador de integrantes para contactar con otros perfiles.

- **Usuario Organizador (Cliente):** Perfil con permisos extendidos para la gestión de eventos. Además de las funciones del usuario registrado, puede dar de alta concursos, quedadas o talleres en la agenda global. Tiene acceso a herramientas de gestión de inscripciones para sus propios eventos.

- **Administrador (Superusuario):** Perfil técnico con control total sobre el sistema. Sus funciones incluyen la moderación de contenidos (borrado de mensajes inapropiados), gestión de altas/bajas de usuarios, mantenimiento de la base de datos MariaDB y supervisión del despliegue en contenedores Docker.

## 4- Contorno operacional
Para que los usuarios puedan interactuar con la plataforma de manera fluida y segura, se han definido los siguientes requisitos mínimos y recomendados:

### Software de usuario
El acceso a la aplicación se realiza a través de un navegador web, por lo que el usuario solo necesita un sistema operativo que soporte navegadores modernos:
- **Navegador Web:** Google Chrome, Mozilla Firefox, Microsoft Edge o Safari (versiones actualizadas de los últimos 2 años). 
- **Compatibilidad:** El navegador debe tener habilitado JavaScript para la interactividad de la interfaz y soporte para HTML5/CSS3 para la correcta visualización del diseño *responsive*.
- **Sistema Operativo:** Independiente (Windows, macOS, Linux, Android o iOS).

### Hardware de usuario
La aplicación está optimizada para consumir recursos mínimos, permitiendo el acceso desde dispositivos con prestaciones básicas:
- **Dispositivos Móviles:** Smartphone o Tablet con conexión de datos (4G/5G o Wi-Fi) para consultas en eventos o ensayos.
- **Ordenadores:** PC o Portátil con resolución mínima recomendada de 1024x768 píxeles para tareas de gestión de perfil y foros.

### Conexión a Internet
- Se requiere una conexión activa a internet. Aunque la web es ligera, se recomienda una conexión estable para la subida de imágenes de alta resolución en las fichas de los grupos de baile.

## 5- Normativa

El proyecto All Dance Together se desarrolla cumpliendo estrictamente con el marco legal vigente en España y la Unión Europea, garantizando la privacidad de los usuarios y la seguridad de sus datos.

### Marco Legal Aplicable
La plataforma se ajusta a las siguientes normativas:

- **RGPD (Reglamento General de Protección de Datos - UE 2016/679):** Normativa europea que regula el tratamiento de datos personales, asegurando la transparencia y el consentimiento explícito.
- **LOPDGDD (Ley Orgánica 3/2018):** Normativa española que adapta el RGPD y garantiza los derechos digitales de los ciudadanos, como el derecho al olvido y la portabilidad.
- **LSSI-CE (Ley 34/2002):** Ley de Servicios de la Sociedad de Información y de Comercio Electrónico, que regula las comunicaciones comerciales y la venta de servicios online (necesaria para la gestión de publicidad y eventos).

### Implementación en la Plataforma
Para dar cumplimiento a estas leyes, la web incluirá tres secciones accesibles desde el pie de página (*footer*):

1.  **Aviso Legal:** Identificación del responsable del sitio (datos del autónomo), condiciones de uso y propiedad intelectual del contenido y del código desarrollado.
2.  **Política de Privacidad:** Detalle exhaustivo de qué datos se recogen (email, nombre, ubicación), con qué finalidad (gestión del perfil y contacto entre bailarines) y cómo el usuario puede ejercer sus derechos de acceso, rectificación y supresión.
3.  **Política de Cookies:** Información sobre el uso de cookies técnicas (necesarias para la sesión en PHP) y analíticas, permitiendo al usuario aceptarlas o rechazarlas mediante un banner inicial.

### Compromiso de Cumplimiento
Se afirma que el diseño de la base de datos MariaDB y la lógica de programación en PHP han sido concebidos bajo el principio de Privacidad desde el Diseño, solicitando únicamente los datos mínimos necesarios para la funcionalidad del servicio y asegurando su almacenamiento cifrado.

## 6- Mejoras futuras
### Evolución Técnica
- **Desarrollo de App Nativa (Android/iOS):** Implementar una aplicación móvil que aproveche las notificaciones push en tiempo real para avisar de ensayos o cambios de última hora en eventos.
- **API Rest:** Creación de una API para que otras plataformas de eventos o academias puedan consultar el calendario de dance covers de forma automatizada.
- **Sistema de Votación en Tiempo Real:** Integrar un módulo de votación mediante códigos QR para concursos presenciales, permitiendo al público elegir a su grupo favorito desde la web.

### Nuevas Funcionalidades
- **Módulo de "Alquiler de Salas":** Un directorio de locales y salas de ensayo en Galicia con sistema de reserva directa y calendario de disponibilidad.
- **Mercadillo de Segunda Mano:** Sección especializada para la compraventa de vestuario de K-pop (outfits), accesorios y álbumes entre usuarios de la comunidad.
- **Sistema de "Matching" de Coreógrafos:** Funcionalidad para conectar a grupos que buscan formación con coreógrafos profesionales de danza urbana.

### Expansión Geográfica
- **Salto Nacional:** Una vez validado el modelo en Galicia, la infraestructura permite replicar la base de datos y los servicios para otras comunidades autónomas, manteniendo la segmentación local que da valor a la plataforma.

[**<-Anterior**](../../README.md)
