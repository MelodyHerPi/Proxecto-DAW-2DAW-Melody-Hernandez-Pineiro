# FASE DE DESEÑO

- [FASE DE DESEÑO](#fase-de-deseño)
  - [1- Diagrama da arquitectura](#1--diagrama-da-arquitectura)
  - [2- Casos de uso](#2--casos-de-uso)
  - [3- Diagrama de Base de Datos](#3--diagrama-de-base-de-datos)
  - [4- Diseño de interfaz de usuarios](#4--diseño-de-interfaz-de-usuarios)

## 1- Diagrama da arquitectura
La arquitectura de All Dance Together se basa en un modelo Cliente-Servidor estructurado en tres capas, utilizando el patrón de diseño MVC (Modelo-Vista-Controlador) para separar la lógica de negocio de la interfaz de usuario. 

Para garantizar la portabilidad y un entorno de ejecución idéntico en desarrollo y producción, todo el sistema se despliega mediante contenedores Docker.

### Descripción de las capas:

- Capa de Presentación (Frontend): Construida con HTML5, CSS3 y JavaScript nativo. Se encarga de renderizar las fichas de los grupos, el calendario de eventos y los foros de discusión, asegurando una experiencia responsive para dispositivos móviles y escritorio.
- Capa de Negocio (Backend): Implementada en PHP 8.4 siguiendo el patrón MVC. Procesa las peticiones del usuario, gestiona la lógica de las notificaciones de eventos próximos y asegura la comunicación con la base de datos de forma segura.
- Capa de Datos: Gestionada por un servidor MariaDB. El acceso a los datos se realiza exclusivamente mediante PDO (PHP Data Objects) para prevenir ataques de inyección SQL y garantizar la integridad de la información de la comunidad.

### Diagrama de componentes y despliegue:

```mermaid
graph LR
    subgraph "Dispositivo de Usuario"

        A[Navegador Web / HTML5 + JS]
    end

    subgraph "Contenedor Docker (Servidor Web)"

        B[Servidor Apache]
        C[Motor PHP 8.4 - Lógica MVC]
    end

    subgraph "Contenedor Docker (Base de Datos)"

        D[(MariaDB)]
    end

    A <-->|Peticiones HTTP/HTTPS| B
    B --- C
    C <-->|Conexión Segura PDO| D
  ```

## 2- Casos de uso

### Actores del Sistema
| Actor | Descripción | Nivel de Acceso |
|-------|-------------|-----------------|
| Visitante (Anónimo) | Persona que puede acceder a la pantalla de regsitro |
| Usuario Registrado | Bailarín o grupo que se ha autenticado | Lectura/Escritura en su perfil |
| Organizador | Usuario con permisos para crear y gestionar eventos | Lectura/Escritura de eventos |
| Administrador | Superusuario con control total del sistema | Control total |

![alt text](image-1.png)

## 3- Diagrama de Base de Datos

                        ┌──────────────────┐
                        │  NOTIFICACION    │
                        ├──────────────────┤
                        │ ◉ id             │
                        │ • tipo           │
                        │ • contenido      │
                        │ • leída          │
                        │ • fecha_creación │
                        │ • FK: usuario_id │
                        │ • FK: evento_id  │
                        └────┬────────┬────┘
                             │        │
                    RECIBE (1:N)   GENERA (1:N)
                             │        │
                             │        └──────────┐
                    ┌────────▼────────┐          │
                    │     USUARIO     │          │
                    ├─────────────────┤          │
                    │ ◉ id            │          │
                    │ • email         │          │
                    │ • contraseña    │          │
                    │ • nombre        │          │
                    │ • rol           │          │
                    │ • provincia     │          │
                    │ • ciudad        │          │
                    │ • teléfono      │          │
                    │ • bio           │          │
                    │ • foto_perfil   │          │
                    │ • estado        │          │
                    │ • fecha_registro│          │
                    │ • redes_sociales│          │
                    └────────┬────────┘          │
                             │                   └──────────┐ 
            ┌────────────────┼────────────────┐             │
            │                │                │             │
       CREA (1:N)     ORGANIZA (1:N)   ESCRIBE (1:N)        │
            │                │                │             │
     ┌──────▼──────┐  ┌──────▼──────┐  ┌──────▼───────┐     │
     │    GRUPO    │  │   EVENTO    │  │  HILO_FORO   │     │
     ├─────────────┤  ├─────────────┤  ├──────────────┤     │
     │ ◉ id        │  │ ◉ id        │ │ ◉ id         │     │
     │ • nombre    │  │ • nombre    │  │ • título     │     │
     │ • miembros  │  │ • tipo      │  │ • contenido  │     │
     │ • galería   │  │ • fecha_hora│  │ • categoría  │     │
     │ • ciudad    │  │ • ciudad    │  │ • estado     │     │
     │ • descripción  │ • capacidad │  │ • fecha_crea │     │
     │ • año_form  │  │ • descripción  └──────┬───────┘     │
     └─────────────┘  │ • estado    │         │             │
                      │ • fecha_crea   CONTIENE (1:N)       │
                      └─────▲───────┘         │             │
                            │         ┌───────▼─────────┐   │
                            │         │ MENSAJE_FORO    │   │
                            │         ├─────────────────┤   │
                            │         │ ◉ id            │   │
                            │         │ • contenido     │   │
                            │         │ • fecha_creación│   │
                            │         │ • reportes      │   │
                            │         └─────────────────┘   │
                            └───────────────────────────────┘

Leyenda: ◉ = Atributo identificador (clave primaria) • = Atributo descriptor FK = Clave foránea (relación)

| # | Relación | Entidad 1 | Entidad 2 | Cardinalidad | Atributo FK | Descripción |
|---|----------|-----------|-----------|--------------|-------------|-------------|
| R1 | CREA | USUARIO | GRUPO | 1:N | usuario_id | Un usuario puede crear 0 o más grupos |
| R2 | ORGANIZA | USUARIO | EVENTO | 1:N | organizador_id | Un usuario organizador puede crear múltiples eventos |
| R3 | ESCRIBE (Hilos) | USUARIO | HILO_FORO | 1:N | usuario_id | Un usuario puede crear múltiples hilos |
| R4 | ESCRIBE (Mensajes) | USUARIO | MENSAJE_FORO | 1:N | usuario_id | Un usuario puede escribir múltiples mensajes |
| R5 | CONTIENE | HILO_FORO | MENSAJE_FORO | 1:N | hilo_id | Un hilo contiene 0 o más mensajes |
| R6 | RECIBE | USUARIO | NOTIFICACION | 1:N | usuario_id | Un usuario puede recibir múltiples notificaciones |
| R7 | GENERA | EVENTO | NOTIFICACION | 1:N | evento_id | Un evento puede generar múltiples notificaciones |



## 4- Diseño de interfaz de usuarios
https://www.figma.com/design/ukKq3Y8y8XER9wNLB7jRoA/Demo-All-Dance-Together?m=auto&t=bVj0iDurSxHSnzT7-6

[<-Anterior](../../README.md)
