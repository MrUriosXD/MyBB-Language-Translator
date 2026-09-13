# 🌐 MyBB Language Translator

Una herramienta web moderna para traducir de forma sencilla y automatizada los paquetes de idioma (`.lang.php`) del sistema de foros **MyBB**.

![HTML5](https://img.shields.io/badge/HTML5-Static-E34F26?style=flat-square&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6%2B-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-3.x-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

> **Aplicación 100 % del lado del cliente:** ya no necesita PHP, `languages.xml` ni un servidor con procesamiento PHP. Puede ejecutarse como una página web estática.

---

## 📋 Descripción

**MyBB Language Translator** es un traductor web diseñado para trabajar con paquetes de idioma de **MyBB**. Permite cargar carpetas completas, archivos `.ZIP` o ficheros `.lang.php` individuales y procesar sus cadenas directamente en el navegador.

La aplicación está construida como una página estática (`index.html`) y utiliza JavaScript para analizar, editar, traducir y exportar los archivos. Durante el proceso se conservan las variables dinámicas de MyBB (`%s`, `{1}`, `$foo`, etc.) y las etiquetas HTML presentes en las cadenas.

---

## ✨ Características principales

- 📂 **Carga flexible**: carpetas completas, archivos `.ZIP` o ficheros `.lang.php` individuales.
- 🤖 **Motores de traducción**: Google Translate (gratuito), MyMemory Translate y Lingva Translate.
- 🧠 **Preservación inteligente**: mantiene variables dinámicas, etiquetas HTML y patrones de mayúsculas.
- ⚙️ **Idiomas integrados**: los idiomas de origen y destino están definidos directamente en `index.html`, sin XML externo.
- 🎨 **Interfaz moderna**: diseño responsive, tema claro/oscuro, Tailwind CSS, Font Awesome, Drag & Drop, filtros y edición manual.
- ⏱️ **Control de peticiones**: intervalo configurable entre peticiones para reducir problemas de rate limit.
- 📊 **Estadísticas**: archivos, cadenas totales, traducidas y pendientes, además del progreso de traducción.
- 📦 **Exportación**: descarga individual o generación de un `.ZIP` con la estructura del paquete para `inc/languages/`.
- 📝 **Cabecera editable**: nombre del Language Pack y traductor/autor.

---

## 📁 Estructura del proyecto

El proyecto se ha simplificado y actualmente está compuesto por:

```text
.
├── index.html    # Aplicación web completa (HTML + JavaScript + Tailwind CSS)
└── README.md     # Documentación del proyecto
```

### `index.html`

Contiene toda la aplicación: interfaz, configuración de idiomas, procesamiento de archivos `.lang.php`, lectura/generación de ZIP mediante JSZip, traducción, edición manual, estadísticas y exportación.

### Configuración de idiomas

La configuración que anteriormente se encontraba en `languages.xml` ahora está **integrada directamente en `index.html`** mediante estructuras JavaScript.

Se mantienen internamente los mapeos entre código ISO, nombre visible y nombre de la carpeta utilizada por MyBB. Esto elimina la petición y el análisis de un XML externo.

---

## 🔄 Cambios recientes

### 🆕 Arquitectura completamente estática

El proyecto ha dejado de utilizar `index.php` como punto de entrada y ahora utiliza:

```text
index.html
```

La lógica que anteriormente dependía de PHP para cargar `languages.xml` se ha trasladado al navegador mediante JavaScript.

### 🗑️ Eliminación de `languages.xml`

`languages.xml` ha sido eliminado. Los datos de idiomas, junto con los nombres de carpetas y nombres visibles, están ahora integrados en `index.html`.

### ⚡ Inicialización de idiomas en cliente

Los selectores de **Idioma Origen** e **Idioma Destino** se rellenan directamente desde las configuraciones JavaScript integradas en la página.

Los valores iniciales son:

- 🇬🇧 **Origen:** English (`en`)
- 🇪🇸 **Destino:** Spanish (`es`)

### 🌐 Ventajas

El nuevo modelo permite alojar la aplicación en servicios de hosting estático, incluyendo **GitHub Pages**, sin PHP ni configuración de servidor.

---

## 🚀 Instalación y requisitos

### Requisitos

No necesita PHP ni base de datos. Solo necesitas un navegador moderno compatible con JavaScript ES6+.

Para alojarla en un servidor, basta con publicar:

```text
index.html
```

### Ejecución local

Puedes abrir `index.html` directamente en el navegador. También puedes utilizar un servidor web estático local, por ejemplo mediante **Live Server** en VS Code.

### Publicación online

Puede desplegarse en servicios compatibles con sitios estáticos, como:

- GitHub Pages.
- Vercel.
- Netlify.
- Cualquier servidor web capaz de servir HTML, CSS y JavaScript.

---

## 💻 Uso de la aplicación

### 1. Seleccionar los idiomas

En la barra lateral selecciona el **Idioma Origen** y el **Idioma Destino**. El botón de intercambio permite invertir ambos idiomas.

### 2. Cargar el paquete de MyBB

Puedes utilizar:

- 📁 **Carpeta Completa**.
- 🗜️ **Archivo `.ZIP`**.
- 📄 **Archivos Sueltos**.

### 3. Configurar la traducción

Selecciona el motor de traducción y ajusta el intervalo entre peticiones si es necesario. También puedes definir el nombre del Language Pack y el traductor/autor.

### 4. Traducir

Pulsa **Traducir** para procesar las cadenas automáticamente. También puedes editar manualmente cualquier cadena desde la tabla.

### 5. Revisar

Utiliza los filtros y las estadísticas para localizar cadenas pendientes y revisar las traducciones generadas.

### 6. Exportar

Descarga archivos individuales o genera un `.ZIP` con la estructura preparada para:

```text
inc/languages/
```

---

## 🛠️ Tecnologías utilizadas

- **HTML5** — estructura de la aplicación.
- **JavaScript ES6+** — lógica, procesamiento de archivos y comunicación con los servicios de traducción.
- **Tailwind CSS** — interfaz y diseño responsive.
- **Font Awesome 6** — iconografía.
- **JSZip 3.10.1** — lectura y generación de archivos `.ZIP` en el navegador.
- **Web APIs** — selección y lectura de archivos y gestión de la interfaz.

---

## 🔐 Privacidad y funcionamiento

El procesamiento principal de los archivos se realiza en el navegador. El proyecto no necesita una base de datos ni un backend propio.

Ten en cuenta que las cadenas enviadas a un motor de traducción externo pueden salir del navegador hacia el servicio correspondiente. Evita utilizar esta herramienta con contenido que no deba enviarse a servicios externos.

---

## ⚠️ Consideraciones

Los motores de traducción dependen de servicios externos y pueden aplicar límites de uso, cambios de disponibilidad o restricciones de tasa.

El intervalo configurable entre peticiones ayuda a reducir problemas de rate limit, pero **no garantiza** la disponibilidad permanente de ninguno de los servicios.

Antes de instalar un paquete traducido en un foro de producción, revisa las cadenas y comprueba que las variables y etiquetas de MyBB se hayan conservado correctamente.

---

## 📜 Licencia

Este proyecto está publicado bajo la **Licencia MIT**. Consulta el archivo `LICENSE` del repositorio para conocer los términos completos.

---

## 🔗 Demo

Puedes probar la aplicación desde:

**https://mybb-language-translator.vercel.app/**

---

## 👤 Autor

Desarrollado por **MrUriosXD**.

Repositorio:

**https://github.com/MrUriosXD/mybb-language-translator**
