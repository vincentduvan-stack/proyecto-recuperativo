# Bitácora de Pruebas y Control de Incidencias (TESTING.md)

## 1. Testing Local
* **Herramientas de Entorno:** Visual Studio Code, extensión *Live Server* y terminal integrada de Python.
* **Validación de Ejecución:**
  * Se ejecutó con éxito el comando `python scripts/generador.py` en la terminal del sistema, comprobando la creación automática del archivo `novedades.html` en la ruta raíz.
  * Se validó mediante *Live Server* la correcta interconexión de hipervínculos entre `index.html` y `novedades.html`, confirmando que los estilos CSS cargan de forma impecable sin errores visuales.

## 2. Testing Remoto
* **Plataforma:** GitHub Pages (Configurado sobre la rama principal `main`).
* **Verificación en la Nube:**
  * Se comprobó la accesibilidad pública a través del dominio web oficial, validando la integridad del diseño responsivo en dispositivos móviles y de escritorio.

## 3. Tabla de Incidencias y Soluciones

| N° | Incidencia Detectada | Tipo | Causa Raíz | Solución Aplicada | Estado |
|---|---|---|---|---|---|
| 1 | Error 404 al cargar la hoja de estilos en la vista previa secundaria. | Enrutamiento CSS | La ruta relativa estaba configurada de manera plana (`style.css`) en vez de apuntar a la subcarpeta. | Se estandarizó la ruta en todos los archivos HTML utilizando `<link rel="stylesheet" href="styles/style.css">`. | Solucionado |
| 2 | El script de Python compilaba el archivo `novedades.html` dentro de la carpeta interna de scripts. | Directorio Python | El método de escritura guardaba el archivo en la misma ruta de ejecución local. | Se ajustó el módulo `os.path` incorporando `..` para redirigir el guardado directamente a la raíz del proyecto. | Solucionado |