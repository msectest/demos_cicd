# Github Actions

Repositorio de demostración de CI/CD con github actions

---

## Sesión 1

En esta sesión veremos, por este orden:
  - Github Actions: Qué son, para qué sirven y cómo configuralas.
  - Creación y configuración de ramas.
  - Pull requests.
  - Protección de ramas.

**Tarea:**

Crea un workflow que imprima en consola el listado de archivos del repositorio en respuesta a una pull request (PR).

**Prerequisitos:**

  - Cuenta Github + creación de repositorios + uso básico (commit, push).
  - Ubuntu 20.04 con permisos de administrador.
  - Instalación de dependencias.

**Dependencias:**

Para las sesiones futuras, es conveniente ir instalando las utilidades detalladas en INSTALL.txt  

## Sesión 2

Integración de scripts python en flujos de trabajo para realizar tareas personalizadas.

**Tarea:**

Validar una PR para que no permita realizar un merge desde una PR que contenga, en el código, la palabra **password**.

Códigos de salida: https://docs.github.com/en/actions/sharing-automations/creating-actions/setting-exit-codes-for-actions

Posibles pasos:

1. Crear un script en python en local que reciba por parámetro un directorio y palabra a buscar.
2. En caso de coincidencia, código de salida que corresponda.
3. Añadir workflow para ejecutar el script python, que deberá estar también disponible en el repositorio.

## Sesión 3

El objetivo de esta sesión es ver como, de modo sencillo, podemos implementar DevSecOps sin más que integrar y configurar una herramienta de detección de vulnerabilidades con Github Actiions.

**Tarea:**


