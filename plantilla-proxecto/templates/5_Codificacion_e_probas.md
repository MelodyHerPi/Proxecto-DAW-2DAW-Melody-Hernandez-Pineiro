# FASE DE CODIFICACIÓN E PROBAS

- [FASE DE CODIFICACIÓN E PROBAS](#fase-de-codificación-e-probas)
  - [1- Codificación](#1--codificación)
  - [2- Prototipos](#2--prototipos)
  - [3- Innovación](#3--innovación)
  - [4- Pruebas](#4--pruebas)

> Este documento explica como se debe realizar a fase de codificación e probas.

## 1- Codificación

La carpeta se encuentra subida en plantilla-proxecto/AllDanceTogether.zip

## 2- Prototipos

https://www.figma.com/design/ukKq3Y8y8XER9wNLB7jRoA/Demo-All-Dance-Together?m=auto&t=bVj0iDurSxHSnzT7-6

## 3- Innovación

No caso de utilizar tecnoloxías diferentes ás estudadas no ciclo formativo, fai unha descrición dos retos asumidos e como se resolveron.
> (No uso ninguna tecnología nueva)

## 4- Pruebas

### Pruebas de despliegue

El principal reto durante esta fase fue la configuración del entorno. El objetivo era replicar el comportamiento de un script `install.sh` utilizado en la empresa de prácticas, que al ejecutarse levanta los contenedores Docker y abre automáticamente el navegador en el localhost. Una vez resuelto, el script quedó funcional y automatiza todo el proceso de despliegue.

### Pruebas funcionales
> ✅ = Funcionalidades testeadas y verificado su correcto funcionamiento; ❌ = Funcionalidades que presentan algún problema.

| Funcionalidad | Resultado | Observaciones |
| :--- | :---: | :--- |
| Registro de usuario | ✅ | |
| Inicio de sesión | ✅ | |
| Cierre de sesión | ✅ | |
| Edición de perfil | ✅ | |
| Publicación de noticia/evento | ✅ | |
| Edición solo de las publicaciones propias | ✅ | |
| Comentarios en publicaciones | ✅ | |
| Buscador de eventos | ✅ | |
| Visualización responsive (móvil) | ✅ | |
| Comprobación de tests de accesibilidad (validator y wave extension) | ✅/❌ | Al usar los archivos de las vistas como .php me aparecen muchos errores en el validator de "Saw <?. Probable cause: Attempt to use an XML processing instruction in HTML. (XML processing instructions are not supported in HTML.)" pero en wave me dice que todo es correcto |

[**<-Anterior**](../../README.md)
