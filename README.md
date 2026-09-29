# Plataforma de Codificación Documental – Aqua Service

## Descripción

Plataforma interna para la gestión, generación y control de códigos de documentos de Aqua Service.

El sistema permitirá centralizar la codificación documental y facilitar la consulta del Listado Maestro y la Matriz de Trazabilidad.

## Funcionalidades

- Inicio de sesión de usuarios autorizados.
- Generación de códigos documentales.
- Control de correlativos.
- Control de revisiones.
- Consulta del Listado Maestro.
- Consulta de la Matriz de Trazabilidad.
- Registro de documentos.
- Trazabilidad de las modificaciones.
- Control de acceso mediante Firebase.
- Actualización de los registros almacenados en Google Sheets.

## Estructura de codificación

La plataforma considera las estructuras definidas en el procedimiento de Codificación de Documentos.

### Proyecto interno / pequeño

`AQ-[Área]-[Tipo]-[Correlativo]-[Revisión]`

Ejemplo:

`AQ-SGI-PROC-01-Rev0`

### Proyecto grande

`AQ-[Cliente]-[N° Cliente]-[Área]-[Tipo]-[Correlativo]-[Revisión]`

Ejemplo:

`AQ-DPM-01-PR-PROC-01-Rev01`

## Tecnologías

- HTML
- CSS
- JavaScript
- GitHub
- Firebase Authentication
- Firebase Cloud Functions
- Google Sheets API

## Seguridad

La plataforma utiliza autenticación para controlar el acceso de los usuarios.

Las credenciales sensibles y claves privadas no deben almacenarse en el repositorio de GitHub.

## Documentación de referencia

El sistema se desarrolla de acuerdo con el procedimiento interno de Codificación de Documentos de Aqua Service.

## Estado del proyecto

En desarrollo.
