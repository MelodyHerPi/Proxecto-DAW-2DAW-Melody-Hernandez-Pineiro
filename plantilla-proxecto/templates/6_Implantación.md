# FASE DE IMPLANTACIÓN

- [FASE DE IMPLANTACIÓN](#fase-de-implantación)
  - [1- Manual técnico](#1--manual-técnico)
    - [1.1- Instalación](#11--instalación)
    - [1.2- Administración del sistema](#12--administración-del-sistema)
  - [2- Manual de usuario](#2--manual-de-usuario)
  - [3- Mejoras futuras](#3--mejoras-futuras)

## 1- Manual técnico

### 1.1- Instalación

Este apartado describe todos los pasos necesarios para que cualquier persona pueda descargar el código del proyecto y continuar su desarrollo o ponerlo en marcha en un entorno propio.

#### Requisitos de hardware
- **CPU:** Procesador de doble núcleo o superior.
- **RAM:** Mínimo 2 GB disponibles para los contenedores Docker.
- **Almacenamiento:** Al menos 5 GB libres para la imagen, la base de datos y los archivos subidos por los usuarios.
- **Red:** Conexión a internet para la descarga de imágenes Docker y dependencias.

#### Software necesario
| Software | Versión mínima | Función |
| :--- | :--- | :--- |
| Docker Engine | 24.x | Contenedor del servidor web y la base de datos |
| Docker Compose | 2.x | Orquestación de los servicios |
| Git | 2.x | Descarga del repositorio del proyecto |
| Navegador web moderno | Últimas 2 versiones | Acceso a la plataforma |

> Añade aquí la URL de tu repositorio Git (GitHub, GitLab, etc.) donde esté alojado el código fuente.

#### Pasos de instalación

**1. Clonar el repositorio**
```bash
  git clone https://github.com/MelodyHerPi/Proxecto-DAW-2DAW-Melody-Hernandez-Pineiro.git
  cd plantilla_proxecto
  # descomprimir AllDanceTogether.zip
  ```

**2. Acceder a la carpeta del proyecto**
```bash
cd AllDanceTogether
```

**3. Ejecutar el script de instalación**
```bash
bash ./install.sh
```

Esto levanta automáticamente todos los contenedores necesarios, crea y rellena la base de datos y abre el navegador en `http://localhost:8085`.

#### Usuarios iniciales de la aplicación
| Rol | Email | Contraseña |
| :--- | :--- | :--- |
| admin | admin@admin.com | abc |
| grupo | grupo@admin.com | abc |
> _(admin funciona como usuario tipo solista)_ 

#### Diagrama de despliegue

La arquitectura de despliegue no presenta variaciones respecto a la definida en la fase de diseño. El sistema se compone de dos contenedores Docker orquestados por Docker Compose:
```
┌──────────────────────────────────────┐
│           Docker Compose             │
│                                      │
│  ┌─────────────────┐  ┌───────────┐  │
│  │  apache-php     │  │  mariadb  │  │
│  │  PHP 8.4 + MVC  │◄─►  10.x     │  │
│  └────────┬────────┘  └───────────┘  │
└───────────┼──────────────────────────┘
            │ HTTP :80
     ┌──────▼──────┐
     │  Navegador  │
     └─────────────┘
```

### 1.2- Administración del sistema

#### Copias de seguridad de la base de datos

Se recomienda realizar volcados periódicos de la base de datos con el siguiente comando:
```bash
docker exec <nombre_contenedor_mariadb> mariadb-dump -u<usuario> -p<contraseña> alldancetogether > backup_$(date +%Y%m%d).sql
```
Los ficheros generados deben almacenarse en una ubicación externa al servidor (servicio de almacenamiento en la nube, equipo local, etc.).

#### Copias de seguridad de archivos subidos

Los archivos multimedia subidos por los usuarios (fotos de perfil, imágenes de publicaciones) se almacenan en el volumen Docker correspondiente. Para respaldarlos:
```bash
docker cp <nombre_contenedor_apache>:/var/www/html/uploads ./backup_uploads_$(date +%Y%m%d)
```

#### Gestión de usuarios

La gestión de cuentas (alta, baja, cambio de rol) se realiza desde el panel de administración de la plataforma, accesible únicamente con una cuenta de tipo **Administrador**. Desde este panel se pueden:
- Listar, buscar y filtrar todos los usuarios registrados.
- Cambiar el rol de una cuenta (usuario, organizador, administrador).
- Suspender o eliminar cuentas que incumplan las normas de la comunidad.

#### Gestión de la seguridad

- **Inyección SQL:** Todas las consultas a la base de datos se realizan mediante PDO con sentencias preparadas, eliminando este vector de ataque.
- **Sesiones:** Se utiliza el sistema nativo de sesiones de PHP con regeneración de ID tras el inicio de sesión para prevenir ataques de fijación de sesión.
- **Actualizaciones:** Se recomienda revisar periódicamente las actualizaciones de la imagen Docker base (`php:8.4-apache`) y de MariaDB para aplicar parches de seguridad.

#### Gestión de incidencias
| Tipo | Ejemplo | Acción recomendada |
| :--- | :--- | :--- |
| Fallo de sistema | Contenedor caído | `docker compose restart` / revisar logs con `docker compose logs` |
| Acceso no autorizado | Intentos de login repetidos | Revisar logs de Apache; considerar bloqueo por IP a nivel de servidor |



## 2- Manual de usuario

### Formación necesaria
La plataforma está diseñada para ser intuitiva y no requiere formación técnica previa. Cualquier usuario familiarizado con redes sociales (Instagram, TikTok) será capaz de utilizarla sin dificultad. No se contempla un plan de formación formal en la fase inicial.

### Guía de inicio rápido

#### Registro e inicio de sesión
1. Accede a la página principal de **All Dance Together**.
2. Haz clic en **Registrarse** e introduce tu nombre, email, contraseña y tipo de cuenta (usuario individual o grupo).
3. Una vez registrado, inicia sesión con tus credenciales.

#### Gestión de tu perfil
1. Accede a **Mi perfil** desde el menú de navegación.
2. Pulsa **Editar perfil** para añadir tu foto, descripción, enlaces a redes sociales y estado de colaboración (ej. *"Busca integrantes"*).
3. Guarda los cambios. Tu perfil será visible para toda la comunidad.

#### Publicar una noticia o evento
1. Desde el tablón principal, haz clic en **Nueva publicación**.
2. Rellena el título, descripción, fecha y, opcionalmente, añade una imagen.
3. Publica el contenido. Aparecerá en el tablón principal para todos los usuarios.

#### Buscar eventos y grupos cercanos
1. Utiliza el **buscador** de la parte superior para buscar por palabras clave.
2. Aplica filtros de localización para encontrar eventos o grupos cerca de ti.

### Preguntas frecuentes (FAQ)

**¿Cómo indico que mi grupo busca integrantes?**
Accede a tu perfil, pulsa en *Editar perfil* y activa la opción *"Busca integrantes"* en el apartado de colaboración.

**¿Puedo tener a la vez un perfil individual y uno de grupo?**
Actualmente cada cuenta corresponde a un único perfil. Si perteneces a un grupo, el grupo puede crear su propia cuenta de tipo *Grupo Registrado*.

**¿Cómo reporto contenido inapropiado?**
Encontrarás en la parte inferior de la página una opción de *Contacto*, en ella se muestran diversas formas de contactar con el equipo técnico.

**¿Mis datos son seguros?**
Sí. La plataforma cumple con el RGPD y la LOPDGDD. Puedes consultar la política de privacidad completa en el pie de página de la web. Puedes solicitar la modificación o eliminación de tus datos a través del apartado de *Contacto*.


## 3- Mejoras futuras

Las siguientes mejoras están identificadas como líneas de evolución prioritarias para versiones posteriores del proyecto, recogiendo tanto las necesidades detectadas durante el desarrollo como las propuestas de la comunidad:

### Evolución técnica
- **Aplicación móvil nativa:** Desarrollo de una versión optimizada para Android e iOS, aprovechando la API del backend PHP existente mediante tecnologías como Retrofit o Volley.
- **Sistema de notificaciones en tiempo real:** Implementación de avisos automáticos (push o email) para nuevos eventos, comentarios o publicaciones relevantes para el usuario.
- **Sistema de favoritos:** Posibilidad de guardar publicaciones y eventos para consultarlos posteriormente desde el perfil.
- **Vinculación usuario-grupo:** Permitir que los perfiles individuales se asocien oficialmente a un grupo registrado en la plataforma.
- **Buscador avanzado:** Incorporación de filtros adicionales por ciudad, tipo de evento, disponibilidad de colaboración, etc.

### Nuevas funcionalidades
- **Mensajería privada:** Sistema de contacto directo entre usuarios y grupos dentro de la plataforma, eliminando la dependencia de redes externas para la comunicación.
- **Sistema de publicidad integrado:** Panel de administración para gestionar banners publicitarios orientados a academias de baile, tiendas de merchandising y organizadores de eventos.
- **Galería multimedia:** Ampliación de los perfiles y publicaciones con soporte para múltiples imágenes y vídeos embebidos.
- **Historial de actividad:** Visualización del registro de publicaciones, comentarios y eventos recientes de cada usuario.
- **Gestión de inscripciones y venta de entradas:** Módulo para que los organizadores puedan gestionar el aforo y la venta de entradas de sus concursos directamente desde la plataforma (ej. integración con ExpOtaku).

### Expansión del proyecto
- **Ampliación geográfica:** Una vez validado el modelo en Galicia, extender la plataforma a otras comunidades autónomas manteniendo la organización por zonas y eventos locales, con el objetivo de convertirse en el directorio de referencia nacional del K-pop dance cover.

[**<-Anterior**](../../README.md)
