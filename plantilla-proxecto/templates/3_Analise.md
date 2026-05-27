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
| Acción | Usuario/Autor | Descripción | Entrada | Proceso | Salida |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Registro de Usuario/Grupo** | Usuario / Grupo | Creación de cuenta dentro de la plataforma. | Nombre, email, contraseña y tipo de cuenta. | Validación y almacenamiento de datos en MariaDB. | Cuenta creada y acceso al sistema. |
| **Gestión de Ficha/Perfil** | Usuario / Grupo | Edición de la información pública del perfil. | Foto, descripción, redes sociales y datos de colaboración. | Actualización de la información almacenada. | Perfil visible para la comunidad. |
| **Publicación de Noticias/Eventos** | Usuario / Grupo | Creación de publicaciones visibles para otros usuarios. | Título, descripción, imágenes y fecha. | Validación y guardado del contenido en la base de datos. | Publicación mostrada en el tablón principal. |
| **Comentarios en Publicaciones** | Usuario / Grupo | Interacción mediante comentarios en publicaciones. | Texto del comentario. | Asociación del comentario con la publicación y el autor. | Conversación actualizada. |
| **Buscador de Eventos Próximos** | Usuario / Grupo | Consulta de eventos publicados mediante filtros o búsqueda. | Palabras clave o filtros. | Consulta de datos en MariaDB. | Listado de eventos coincidentes. |
| **Información de Colaboración** | Usuario / Grupo | Configuración de estados como “acepta colaboraciones” o “busca integrantes”. | Opciones de disponibilidad. | Actualización de información del perfil. | Estado visible públicamente en el perfil. |
| **Administración de Contenido** | Administrador | Moderación de publicaciones y comentarios inapropiados. | Reportes o acciones administrativas. | Eliminación o edición de contenido. | Plataforma moderada y contenido actualizado. |

## 3- Tipos de usuarios

El acceso a las funcionalidades del sistema se segmenta en dos tipos principales de cuenta dentro de la plataforma:

- **Usuario Registrado:** Perfil individual destinado a bailarines o miembros de la comunidad. Puede crear y editar su perfil, publicar noticias o eventos, comentar publicaciones y configurar información relacionada con colaboraciones o búsqueda de integrantes.

- **Grupo Registrado:** Perfil orientado a grupos de dance cover o colectivos de baile. Dispone de funcionalidades similares a las del usuario registrado, permitiendo gestionar una ficha grupal pública, publicar contenido y mostrar información relacionada con integrantes o colaboraciones.

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

El proyecto All Dance Together se desarrolla cumpliendo con la legislación vigente en España y la Unión Europea en materia de privacidad y protección de datos, garantizando la seguridad de la información de los usuarios.

### Marco Legal Aplicable

La plataforma se ajusta a las siguientes normativas:

- **RGPD (Reglamento General de Protección de Datos - UE 2016/679):** Regula el tratamiento de datos personales dentro de la Unión Europea.
- **LOPDGDD (Ley Orgánica 3/2018):** Adapta el RGPD al marco legal español y garantiza los derechos digitales de los usuarios.
- **LSSI-CE (Ley 34/2002):** Regula los servicios digitales y las comunicaciones electrónicas en páginas web y plataformas online.

### Implementación en la Plataforma

La aplicación incluirá diferentes apartados accesibles desde el pie de página (*footer*) para informar correctamente al usuario:

1. **Política de Privacidad**
2. **Términos de Uso**
3. **Contacto**
4. **Ayuda**

### Ejemplo de Información Publicada en la Web

#### Política de Privacidad (Ejemplo)

> “Los datos personales facilitados por los usuarios serán utilizados exclusivamente para la gestión de perfiles, publicaciones y funcionalidades internas de la plataforma All Dance Together. En ningún caso se compartirán datos personales con terceros sin consentimiento previo. El usuario podrá solicitar la modificación o eliminación de sus datos mediante el apartado de contacto.”

#### Términos de Uso (Ejemplo)

> “El usuario se compromete a utilizar la plataforma de manera respetuosa, evitando la publicación de contenido ofensivo, discriminatorio o que incumpla la legislación vigente. All Dance Together se reserva el derecho de eliminar contenido inapropiado y suspender cuentas que incumplan las normas de la comunidad.”

#### Contacto (Ejemplo)

> “Para cualquier incidencia, consulta o solicitud relacionada con la plataforma, el usuario podrá utilizar los datos de contacto disponibles en la web dentro de los horarios establecidos.”

#### Ayuda (Ejemplo)

> “La sección de ayuda ofrece información básica sobre el funcionamiento de la plataforma, creación de perfiles, publicaciones y resolución de dudas frecuentes.”

## 6- Mejoras futuras
### Evolución Técnica
- **Adaptación móvil de la plataforma:** Desarrollo de una versión optimizada para dispositivos móviles utilizando tecnologías compatibles con PHP y APIs de conexión como Retrofit o Volley para la comunicación con el servidor.
- **Sistema de notificaciones:** Implementar avisos automáticos sobre nuevos eventos, publicaciones o comentarios relevantes para el usuario.
- **Sistema de favoritos:** Permitir guardar publicaciones o eventos favoritos para consultarlos posteriormente.
- **Relación entre usuarios y grupos:** Posibilidad de vincular perfiles individuales con grupos registrados dentro de la plataforma.
- **Mejoras en el buscador:** Incorporar filtros avanzados para localizar publicaciones, eventos o perfiles específicos.

### Nuevas Funcionalidades
- **Mensajería privada básica:** Sistema interno de contacto entre usuarios y grupos.
- **Sistema de publicidad integrado:** Inclusión de banners publicitarios administrables desde el panel de administración.
- **Galería multimedia:** Posibilidad de añadir más imágenes o vídeos en los perfiles y publicaciones.
- **Historial de actividad:** Visualización de publicaciones y comentarios recientes realizados por cada usuario.

### Expansión del Proyecto
- **Ampliación geográfica:** Extender el funcionamiento de la plataforma a otras comunidades autónomas manteniendo la organización por zonas y eventos locales.

[**<-Anterior**](../../README.md)
