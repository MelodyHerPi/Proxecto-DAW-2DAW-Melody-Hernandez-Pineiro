# 1- Empresa

- [1- Empresa](#1--empresa)
  - [1.1- Idea de negocio](#11--idea-de-negocio)
  - [1.2- Justificación de la idea](#12--justificación-de-la-idea)
  - [1.3- Segmento de clientes](#13--segmento-de-clientes)
  - [1.4- Competencia](#14--competencia)
  - [1.5- Propuesta de valor](#15--propuesta-de-valor)
  - [1.6- Forma jurídica](#16--forma-jurídica)
  - [1.7- Inversiones](#17--inversiones)
    - [1.7.1- Costes](#171--costes)
    - [1.7.2- Ingresos](#172--ingresos)
  - [1.8- Viabilidad](#18--viabilidad)
    - [1.8.1- Viabilidad técnica](#181--viabilidad-técnica)
    - [1.8.2- Viabilidad económica](#182--viabilidad-económica)
    - [1.8.3- Conclusión](#183--conclusión)

## 1.1- Idea de negocio
La idea de negocio consiste en crear una plataforma web centralizada y especializada en la comunidad de Kpop dance cover en Galicia. 
El proyecto trataría de resolver la fragmentación actual (interacciones dispersas en múltiples redes sociales), así se ofrecerá un ecosistema digital único para la gestión, promoción y socialización de este colectivo. 

El producto central es una red social para grupos, solistas y espectadores. Todos podrán crear un perfil profesional y localizar otros bailarines por cercanía geográfica. La utilidad principal es optimizar la visibilidad y simplificar la logística para los integrantes de la comunidad.

Los principales valores añadidos que tiene en comparación al resto de redes sociales genéricas son centralización especializada a través de filtros de búsqueda para el sector; agenda unificada con panel de eventos y concursos (evitando una problemática actual de solapamiento de fechas entre quedadas y concursos de diferentes grupos); por último, sería una herramienta comunitaria con foros de debate y sistema de noticias que fomenten el sentimiento de pertenencia a un grupo a nivel regional.  

Principalmente no está planteado realmente para ofrecer productos aumentados, pero en un futuro se podría usar a modo de plataforma de gestión para organizadores, por ejemplo en la ExpOtaku para evitar el exceso de participantes y poder acotar el número, venta de entradas, espacio publicitario, etc. 

## 1.2- Justificación de la idea
La creación de la web All Dance Together surge de la observación durante años de una comunidad que no deja de estar en auge pero desatendida tecnológicamente. El Kpop ha dejado de ser un nicho a ser un género musical ampliamente extendido, España siendo uno de los países europeos que muestran más interés en esta cultura. 

Las necesidades que se pretenden cubrir en este proyecto son simples, pero muy necesarias: centralizar la información (evitando la pérdida de datos sobre concursos, quedadas, etc., que suele ocurrir con el scroll infinito de las redes sociales), facilitar la formación de grupos mediante filtros geográficos (muchas personas nuevas quieren crear grupos, pero si no son de Vigo o A Coruña suele ser complicado porque no encuentran a otros bailarines ni saben dónde preguntar si hay más gente de su zona interesada) y dar visibilidad a organizadores nuevos (actualmente se crean muchos grupos, lo que hace que, al haber más demanda, también haya personas que quieran organizar sus propios concursos).

El análisis del mercado y de la competencia, por una parte, es sencillo, ya que actualmente no existen aplicaciones de este tipo. Sin embargo, por otro lado, es importante tener en cuenta que redes sociales como Instagram, TikTok y los grupos de WhatsApp son las herramientas que se utilizan hoy en día y, aunque el sistema sea caótico, siguen siendo una forma de organización dentro de la comunidad, por lo que también pueden considerarse competencia.

### Análisis DAFO
| DEBILIDADES | FORTALEZAS |
| :--- | :--- |
| Dependencia de la participación activa inicial de los usuarios para generar contenido. |  Conocimiento profundo del nicho de mercado y de la comunidad "kpoper" en Galicia. |
| Recursos limitados para marketing y publicidad en la fase de lanzamiento. | Tecnología escalable (Docker/PHP) con costes de mantenimiento y despliegue mínimos. |
| Resistencia al cambio de grupos ya asentados exclusivamente en redes sociales generales. | Plataforma única y especializada: no existe competencia directa con este nivel de centralización regional. |
| AMENAZAS | OPORTUNIDADES |
| Posibles cambios en las políticas de APIs de redes sociales externas (Instagram/TikTok). | Crecimiento sostenido del interés por la cultura coreana y el K-pop en España (datos de Statista). |
| Aparición de funcionalidades de "comunidad local" en plataformas gigantes ya consolidadas. | Alianzas estratégicas con academias de baile, tiendas de merchandising y eventos de cultura asiática. |
| Saturación de eventos en fechas específicas que dividan a la audiencia. | Posibilidad de expansión del modelo de negocio a otras comunidades autónomas tras validar el éxito en Galicia. |

## 1.3- Segmento de clientes
La plataforma identifica tres principales grupos de público, diferenciando claramente entre el usuario final (consumidor del servicio gratuito) y el cliente potencial (quien genera el retorno económico).

### Segmentación de Usuarios 
Este grupo es el motor de la plataforma, su perfil es:
- Perfil demográfico: Jóvenes de entre 14 y 30 años, residentes en Galicia, con especial concentración en las áreas metropolitanas de Vigo, A Coruña y Santiago de Compostela (zonas donde hay más grupos y se hacen la mayoría de concursos).
- Comportamiento: Bailarines (grupos o solistas) y aficionados a la cultura coreana que buscan eventos y socialización.
- Cuantificación: Se estima una comunidad de varios miles de personas en Galicia, basándonos en la alta participación en eventos como la Japan Weekend de Coruña o los concursos de baile locales, donde las inscripciones suelen agotarse en pocas horas.

### Segmentación de Clientes
Son las entidades o profesionales que ven en la plataforma un canal publicitario o de gestión:
- Academias de baile y Centros Culturales: Entidades que ofrecen clases de danza urbana y K-pop y buscan captar alumnos segmentados geográficamente (Por lo general los grupos de covers nacen de personas que iban a la misma academia de baile).
- Comercios especializados: Tiendas de merchandising, moda asiática y papelería temática.
- Organizadores de Eventos: Asociaciones o empresas de eventos que requieren una herramienta para gestionar inscripciones, votaciones o venta de entradas para concursos de baile.

### Diferenciación entre Usuario y Cliente
Es vital distinguir ambos roles para entender la viabilidad del proyecto:

| Perfil | Rol | Relación con la plataforma |
| :--- | :--- | :--- |
| Bailarines/Fans | Usuario | Acceden de forma gratuita a las fichas, foros y calendario. Aportan el tráfico y el contenido (valor social). |
| Empresas/Tiendas | Cliente | Pagan por espacios publicitarios segmentados o destacados en el directorio. |
| Organizadores | Cliente | Pagan por el uso de la infraestructura técnica para gestionar sus concursos o la comisión por venta de entradas. |

### Tamaño del Mercado
Como ya se comentó anteriormente es un nicho en expansión. A nivel nacional ha crecido exponencialmente el interés por esta cultura musical,siendo Galicia una de las comunidades con más concursos e interés en este género y lo que le rodea. 

## 1.4- Competencia
Actualmente, no existe una plataforma web integral que centralice el K-pop dance cover en Galicia, por lo que la competencia es indirecta o está fragmentada.

### Competencia Indirecta y Posicionamiento
- Redes Sociales Genéricas (Instagram, TikTok, X): Poseen la mayor cuota de mercado en cuanto a difusión de vídeos. Sin embargo, su posicionamiento es de consumo rápido y no ofrecen herramientas de gestión, foros o bases de datos localizadas.
- Grupos de Mensajería (WhatsApp, Discord): Utilizados para la comunicación interna de grupos. Tienen un posicionamiento de nicho cerrado que dificulta la llegada de nuevos integrantes y la visibilidad pública.

### Productos/Servicios Sustitutivos
- Páginas de Eventos Generales: Webs como Japan Weekend o festivales de cultura asiática. Cubren la parte de eventos de gran escala, pero ignoran la actividad diaria de los grupos locales y los ensayos, además de ser, en ocasiones, un entorno frío y estresante para nuevos miembros de la comunidad.
- Google Maps/Directorios Locales: Podrían usarse para buscar academias, pero carecen del componente social y la especialización en el género K-pop.

### Ventaja Competitiva de All Dance Together
Frente a la competencia, la plataforma se posiciona como el único canal especializado y estructurado que ofrece todas las funcionalidades (red social, foro, eventos y gestión) en un mismo espacio diseñado exclusivamente para el territorio gallego.

## 1.5- Propuesta de valor

La propuesta de valor se basa en la especialización técnica y geográfica, ofreciendo una solución integral que las redes sociales genéricas no cubren.

Se diferencia de las demás al centralizar en un solo punto toda la información e interacción comunitaria, con sus filtros de búsqueda locales y herramientas de gestión profesional. 

A los usuarios de la comunidad les aporta un ahorro de tiempo en la búsqueda de información y vías directas para profesionalizar su imagen cara a eventos. Por otro lado, las posibles empresas interesadas en obtener atención de este sector social, le podemos ofrecerles espacio publicitario para sus eventos.

A todo aquel que se pregunte: ¿por qué elegir All Dance Together?
La respuesta es sencilla: estarán eligiendo una plataforma única que ayudará a que la comunidad esté menos fragmentada y hará más fácil que tanto las personas nuevas como quienes llevan más tiempo puedan integrarse y conectar con otros miembros de la comunidad.

## 1.6- Forma jurídica

La forma jurídica elegida para el desarrollo y explotación  es la de Empresario Individual (Autónomo), ya  que se ha optado por la simplicidad de la gestión de trámites (más rápidos y económicos que los de sociedad mercantil), baja inversión inicial y control total del proyecto. 

## 1.7- Inversiones

La puesta en marcha de All Dance Together requiere una inversión inicial centrada en activos tecnológicos y operativos. Al ser un negocio digital, no se contempla la adquisición o alquiler de locales físicos, operando bajo un modelo de teletrabajo.

| Elemento | Descripción | Coste Estimado |
| :--- | :--- | :--- |
| Equipo informático | Ordenador de alto rendimiento para desarrollo y virtualización (Docker). | 1.200 € |
| Infraestructura de red | Router profesional y periféricos de conectividad. | 150 € |
| Software y Licencias | Licencias de IDE, herramientas de diseño y dominio web (.es/.com). | 100 € |
| Servidores (Hosting) | Pago inicial de servidor VPS optimizado para Docker y MariaDB (anual). | 180 € |
| Mobiliario de oficina | Puesto de trabajo ergonómico (mesa y silla). | 350 € |
| Gastos de constitución | Trámites administrativos y alta de actividad. | 60 € |
| TOTAL INVERSIÓN | | 2.040 € |

La mayor parte del capital se destina al equipo informático, ya que es la herramienta clave para garantizar la fluidez del desarrollo en PHP y el despliegue de contenedores. El resto de la inversión cubre la infraestructura digital mínima necesaria para que la plataforma sea accesible desde el primer día.

### 1.7.1- Costes

Para el mantenimiento de la actividad, se distinguen los costes operativos según su naturaleza, incluyendo la carga fiscal y social obligatoria.

Los costes fijos mensuales serían: 
- Cuota de Autónomos (Coste Social): 80 € (Tarifa plana para nuevos autónomos durante el primer año).
- Mantenimiento de Servidor y Dominios: 15 € (Alojamiento del entorno Docker y BD).
- Gestoría fiscal: 50 € (Gestión de declaraciones trimestrales y anuales).
- Suministros (Proporcional): 40 € (Internet y energía eléctrica).

Los costes variables serían: 
- Marketing y Publicidad: 50 € - 150 € (Inversión en redes sociales según el calendario de eventos).
- Comisiones de Pasarela de Pago: 1,5% por transacción (en caso de venta de entradas).

En cuanto a impuestos: 
- IVA (21%): Se repercute a los clientes y se liquida trimestralmente.
- IRPF: Retención del 7% en facturas emitidas a empresas (bonificación para nuevos autónomos).

### 1.7.2- Ingresos
La estrategia de ingresos se basa en un modelo donde el uso básico es gratuito para los usuarios, mientras que las empresas y organizadores pagan por servicios específicos.

Previsión de ventas: 
Se estima un crecimiento progresivo durante el primer año de actividad:
- Publicidad y Patrocinios: 1.200 € anuales (Venta de banners y fichas destacadas para academias y tiendas).
- Comisiones por Venta de Entradas: 600 € anuales (Gestión de inscripciones y entradas para concursos locales).
- Servicios Premium para Organizadores: 400 € anuales (Herramientas avanzadas de votación y analíticas).

Política de precios: 
- Fichas de Usuario/Grupo: Gratuito (Estrategia de captación de tráfico).
- Anuncios Locales: Desde 20 €/mes para tiendas y negocios gallegos.
- Gestión de Concursos: Comisión del 3% sobre el valor de la entrada o cuota fija de 50 € por evento.
- Espacios Patrocinados: 100 €/evento para aparecer como colaborador principal en la sección de noticias.

## 1.8- Viabilidad

### 1.8.1- Viabilidad técnica

La realización de All Dance Together es plenamente viable desde el punto de vista técnico por las siguientes razones:

- Recursos Humanos y Medios: El proyecto es desarrollado por un único perfil técnico con los conocimientos necesarios en PHP, MariaDB y Docker. No se requiere maquinaria pesada ni instalaciones complejas; la producción se realiza de forma íntegra con un equipo informático estándar y conexión a internet.
- Tecnología Dominada: El uso del patrón MVC en PHP y contenedores Docker permite un desarrollo controlado y estable. Al no depender de frameworks externos complejos, se reduce el riesgo de incompatibilidades.
- Infraestructura: La disponibilidad de servidores VPS económicos garantiza que el despliegue y mantenimiento de la plataforma sea sencillo y escalable según crezca la base de usuarios. No existen impedimentos técnicos significativos que dificulten el proceso productivo.

### 1.8.2- Viabilidad económica
La viabilidad económica se sustenta en la baja estructura de costes y la inversión inicial reducida:
- Inversión Inicial: Se requiere una inversión de 2.040 €, destinada principalmente a activos que tienen una vida útil de varios años (equipo informático y mobiliario).
- Costes Operativos: Los costes fijos mensuales son de aproximadamente 185 € (incluyendo la cuota de autónomos bonificada). Esto significa que el proyecto necesita unos ingresos mínimos de 2.220 € anuales para cubrir sus gastos operativos básicos.
- Proyección de Ingresos: Con una previsión de ingresos de 2.200 € anuales en el primer año (entre publicidad, comisiones y servicios premium), el proyecto alcanza prácticamente el punto de equilibrio desde sus inicios, con una tendencia al alza a medida que la plataforma se consolide en la comunidad gallega.

### 1.8.3- Conclusión
¿Es viable?: Sí, el proyecto es viable tanto técnica como económicamente. Los Beneficios vs. Costes: A partir del segundo año, una vez amortizada la inversión inicial y estabilizada la base de clientes (tiendas y academias), los beneficios previstos superan los costes operativos, generando un flujo de caja positivo.Por último, financiación y cobertura: Dada la naturaleza del proyecto (innovación digital y cultura juvenil), las posibles pérdidas iniciales o la inversión inicial podrían cubrirse mediante subvenciones locales o autonómicas para el fomento del empleo autónomo y la digitalización, reduciendo aún más el riesgo económico del emprendedor.

[<-Anterior](../../README.md)
