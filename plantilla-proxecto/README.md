# Proxecto fin de ciclo

- [Proxecto fin de ciclo](#proxecto-fin-de-ciclo)
  - [Taboleiro do proyecto](#taboleiro-do-proyecto)
  - [Descrición](#descrición)
  - [Instalación / Posta en marcha](#instalación--posta-en-marcha)
  - [Uso](#uso)
  - [Sobre o autor](#sobre-o-autor)
  - [Licenza](#licenza)
  - [Índice](#índice)
  - [Guía de contribución](#guía-de-contribución)
  - [Links](#links)

## Taboleiro do proyecto

El proyecto actualmente está en fase de desarrollo. 

## Descrición

**All Dance Together - Encuentra grupos de kpop dance cover a tu alrededor.**
Este proyecto nace con la ilusión de crear un punto de encuentro entre la comunidad "kpoper" de Galicia en un mismo espacio digital.
La idea es sencilla pero útil, ya que no existe dicha plataforma: centralizar en una sola web toda la información de grupos y solistas locales, contando con fichas de presentación, foros, sistema de noticias, acceso a las redes sociales, alertas de eventos próximos a ti, ¡incluso podrás crear tus propias quedadas y concursos! 
El concepto clave del proyecto es la unión de la comunidad. 

En cuanto al ámbito tecnológico, se usará HTML 5 y CSS 3 para la parte visual (frontend), conjuntamente con JavaScript para dotar a la web de dinamismo e interactividad, la lógica interna y gestión de datos con PHP, mientras que el almacenamiento de datos con MariaDB. 

## Instalación / Posta en marcha

Para que la puesta en marcha sea lo más sencilla posible, el proyecto contará con un script de configuración automática dentro de una máquina virtual. Se usarán contenedores Docker, que permitirán crear la infraestructura del servidor web, el motor de PHP y la base de datos en MariaDB.
En cuanto a la preparación del entorno, se usará una máquina virtual con Docker instalado, accediendo a la carpeta raíz del proyecto donde se encuentra la configuración del docker-compose.yml; después, se ejecutará el despliegue de todos los contenedores con un único comando, instalando las imágenes y configurando las redes internas necesarias, además de crear todas las vinculaciones necesarias. Por último, se podrá acceder a la web a través de la dirección local de la máquina virtual.

## Uso

Plataforma de uso sencillo y personalizable: 
- Explora y descubre los grupos y solistas de Dance Cover de Kpop gallegos, sus perfiles, presentaciones, fotos y vídeos. 
- Mantente conectado/a a la comunidad con el foro, debates, preguntas, interacciones dentro de un ambiente sano y amigable.
- ¿Buscas integrantes para tu grupo? ¿Necesitas personal de edición de fotos? Comparte estos anuncios en nuestro tablón. 
- Organiza y asiste a eventos consultando el panel de eventos para estar al día de las próximas actuaciones y la ubicación de estas. 
- Mantente al día con las alertas personalizadas. 


## Sobre o autor

Soy desarrolladora enfocada en la creación de páginas web dinámicas, en proceso de orientarse hacia un ámbito Full Stack. 
Mi mayor punto fuerte es la adaptación al proyecto y al entorno de trabajo, buscando resolución de problemas rápido, mantenible y dejando la puerta abierta a la mejora futura del programa. 
Las tecnologías con las que más cómoda me siento son Javascript, Java, HTML, CSS, PHP y Bases de Datos relacionales (MariaDB, MySQL y PostgreSQL).

Este proyecto nació del conocimiento de que en ocasiones es muy complicado hacer amigos en el mundo de la danza, incluso en un ámbito tan informal como el de los covers.

## Licenza

He seleccionado la licencia GNU GPLv3, ya que garantiza la libertad fundamental del software libre, pudiendo usar, estudiar, modificar y redistribuir el código; pero teniendo en cuenta que cualquier derivado de esta plataforma debe mantenerse bajo estos términos de libertad y apertura. 

## Índice

> *EXPLICACIÓN*: Simplemente indexa ordenadamente todo o tey proxecto.

1. [Anteproyecto](templates/1_Anteproxecto.md)
2. [Empresa](templates/2_Empresa.md)
3. [Análise](templates/3_Analise.md)
4. [Deseño](templates/4_Deseño.md)
5. [Codificación e probas](templates/5_Codificacion_e_probas.md)
6. [Implantación](templates/6_Implantación.md)
7. [Referencias](templates/7_Referencias.md)
8. [Incidencias](templates/8_Incidencias.md)

## Guía de contribución

La mejor forma de contribuir en el proyecto es aumentando las funcionalidades basadas en las necesidades de la comunidad en ese momento. 
Unos ejemplos serían la integración de APIs de Youtube/Spotify, mejorar el rendimiento y depurar el código, añadir nuevos temas visuales más personalizados,... En conclusión, cualquier aporte a mejorar la experiencia del usuario, manteniendo la simpleza del uso de la web.

## Links

