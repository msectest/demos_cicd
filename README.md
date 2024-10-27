# Github Actions

Repositorio de demostración de CI/CD con github actions

## Sesión 1

En esta sesión aprenderemos:
  - Github Actions: Qué son, para qué sirven y cómo configuralas.
  - Creación y configuración de ramas.
  - Gestión de Pull requests.
  - Introducción a Rulesets (Requerir pull-requests para merges sobre develop y main)

**Tarea 1:**

Crea un repositorio con tu cuenta Github que contenga el contenido de este, que puedes descargar como .zip desde la interfaz.

En ese repositorio, realiza la siguiente configuración:

 - Configura el repositorio para que no se pueda subir contenido directamente a develop y/o main.
 - Crea una nueva rama develop y súbela al repositorio.
 - Copia el contenido descargado previamente a dicha rama develop.

**Tarea 2:**

Crea un flujo de trabajo nuevo "Hola Mundo" que saque este mensaje en consola y muestre el contenido del repositorio con un pequeño script Bash.

 - Estando en la rama develop, crea una nueva rama, por ejemplo feature/nuevo-flujo-holamundo
 - Crea y edita el flujo en el directorio .github/workflows empleando la ayuda disponible en Github.
 - Sube el contenido de la nueva rama y activa el flujo creando una pull request de la rama sobre develop.
 - Verifica el funcionamiento del flujo.
 - Fin!

**Prerequisitos:**

  - Cuenta Github + creación de repositorios + uso básico (commit, push).
  - Ubuntu 20.04 con permisos de administrador.
  - Instalación de dependencias.

**Dependencias:**

Para las sesiones futuras, es conveniente ir instalando las utilidades detalladas en INSTALL.txt  

## Sesión 2

En esta sesión continuaremos creando un flujo de trabajo adicional, poniendo en práctica los conocimientos de python adquiridos.

Aprenderemos:
  - Integrar un script python en un Github Action.
  - Técnicas de análisis estático de código, verificación de fuga de secretos, etc.
  - Mecanismos de protección de ramas (Bloquear merges de PRs en base a resultados).

**Tarea 1:**

Crear una rama nueva (por ejemplo, feature/check-secrets) que permita detectar posibles fugas de secretos. 

Esta rama debe contener:
  - Script en python (a desarrollar) que analice un directorio en busca de una palabra clave.
  - Flujo de trabajo que utilice el script anterior para buscar, en el repositorio de código, cualquier archivo que pueda contener la palabra reservada **password** 
  - El script deberá terminar con error en caso de que se encuentre algún secreto.

Tip! Códigos de salida: https://docs.github.com/en/actions/sharing-automations/creating-actions/setting-exit-codes-for-actions

**Tarea 2:**

¿Se han detectado passwords? Si es así, ¿Nos ha dejado realizar el merge igualmente?. Para evitarlo, debemos configurar Github para que no permita ejecutar las PR.

Una vez configurado, ¿Permite mezclar la PR? Eliminar el password, subir a la rama con commit + push y volver a probar.

## Sesión 3

El objetivo de esta sesión es ver como, de modo sencillo, podemos implementar DevSecOps sin más que integrar y configurar una herramienta de detección de vulnerabilidades con Github Actions.

Aprenderemos:

  - Conexión con herramientas externas desde Github Actions.
  - Uso de secretos en Github Actions.
  - Bloqueo de modificaciones inseguras.
  - Informes de Seguridad en formato SARIF (Static Analysis Results Interchange Format).
  - Modelado de seguridad en función de criticidad.

**Tarea 1:**

Crear una nueva rama desde develop (por ejemplo, feature/security-check) para añadir nuevo workflow para conectar con Snyk. Sobre esta rama, probamos en local el cliente Snyk (si no se ha instalado, instalar con instrucciones INSTALL.txt)

  - Ejecutar, en el directorio base (package.json), el comando: snyk test
  - Revisar resultados. Existen vulnerabilidades, por lo que configuraremos Github para que no permita consolidar este código fuente.
  - Crear el workflow apoyándonos en las actions preconfiguradas.
  - Para ello, será imprescindible añadir un secreto con el TOKEN que se haya obtenido de: https://app.snyk.io/account
  - Revisar resultado del flujo y comprobar que se reportan las vulnerabilidades.

**Tarea 2:**

Añadir nueva verificación para que este flujo pase a formar parte de los checkeos obligatorios:

  - Verificar que no se puede completar la PR tras añadir el checkeo.
  - Modificar el flujo para que, además, se reporten los resultados en formato SARIF. El resultado estará dipsonible en la pestaña Security.
  - Por último, integrar desde Snyk para ver otras posibilidaes. ¿Qué inconvenientes veis? ¿Preferencias?

## Sesión 3
