# 🌐 MyBB Language Translator

Una potente y moderna herramienta web para traducir de forma sencilla y automatizada los paquetes de idioma (`.lang.php`) del sistema de foros **MyBB**.

![HTML5](https://img.shields.io/badge/HTML5-Static-E34F26?style=flat-square&logo=html5&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-3.0-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

---

## 📋 Descripción

**MyBB Language Translator** es una herramienta web estática basada en **HTML, JavaScript y Tailwind CSS**, diseñada para la gestión y traducción de paquetes de idioma de MyBB.

Permite cargar carpetas completas, archivos comprimidos en ZIP o ficheros `.lang.php` sueltos, traduciendo automáticamente sus cadenas mediante distintos motores de traducción. La aplicación funciona directamente en el navegador y está pensada para conservar la estructura de los archivos de idioma, incluyendo variables internas (`$1`, `%s`, etc.) y etiquetas HTML.

---

## ✨ Características Principales

- **📂 Flexibilidad de Carga**: Sube archivos `.lang.php` individuales, carpetas completas o paquetes comprimidos en `.zip`.
- **🤖 Motores de Traducción Integrados**:
  - Google Translate (Gratuito)
  - MyMemory Translate
  - Lingva Translate
- **🧠 Preservación Inteligente de Formato**:
  - Mantiene variables dinámicas (ej. `%s`, `{1}`, `$foo`) durante la traducción.
  - Conserva las etiquetas HTML presentes en las cadenas.
  - Respeta las mayúsculas iniciales según la convención del texto original.
- **🌍 Gestión de Idiomas Integrada**:
  - Los idiomas soportados están definidos directamente en la aplicación.
  - Ya no depende de un archivo `languages.xml` externo.
  - Permite seleccionar idioma de origen y destino y cambiarlos rápidamente.
- **⚙️ Personalización de la Traducción**:
  - Intercambio rápido entre idioma origen y destino.
  - Control del intervalo entre peticiones para reducir problemas de rate limit.
  - Configuración del nombre del Language Pack y del traductor/autor.
- **🎨 Interfaz Adaptativa e Intuitiva**:
  - Tema claro/oscuro (*Dark Mode*) con persistencia de la preferencia.
  - Diseño responsivo basado en **Tailwind CSS**.
  - Edición manual de cadenas directamente desde la tabla.
  - Filtros y búsqueda para localizar cadenas rápidamente.
  - Columnas redimensionables.
  - Resumen del número de archivos, cadenas, traducciones y pendientes.
- **📦 Exportación Completa o Individual**:
  - Descarga archivos modificados individualmente.
  - Genera un `.ZIP` con la estructura del idioma preparada para su uso en MyBB.

---

## 📁 Archivos del Proyecto

El proyecto se ha simplificado y actualmente está compuesto por los siguientes archivos principales:

```text
.
├── index.html         # Aplicación web completa (HTML / JavaScript / Tailwind CSS)
└── README.md          # Documentación general del repositorio
```

### Descripción de Componentes

1. **`index.html`**:
   - Contiene la interfaz completa de la aplicación.
   - Incluye la configuración de los idiomas soportados directamente en el código.
   - Procesa los archivos de idioma en el navegador.
   - Gestiona la traducción, edición, filtros, progreso y exportación.
   - Utiliza **JSZip** para trabajar con paquetes `.zip` directamente desde el navegador.

2. **`README.md`**:
   - Documentación y guía de uso del proyecto.

> ℹ️ **Nota:** El proyecto ya no utiliza `languages.xml`. La configuración de idiomas se encuentra integrada directamente en `index.html`, eliminando la dependencia de un archivo XML externo y de un procesamiento en servidor.

---

## 🚀 Instalación y Requisitos

### Requisitos

No necesita PHP ni una base de datos. Al tratarse de una aplicación web estática, puede ejecutarse prácticamente en cualquier servidor web o servicio de alojamiento de páginas estáticas.

- Navegador web moderno con soporte para JavaScript.
- Servidor web estático opcional (Apache, Nginx, LiteSpeed, GitHub Pages, etc.).
- Conexión a Internet para utilizar los servicios externos de traducción y cargar las librerías CDN.

### Pasos de Instalación

1. Clona este repositorio o descarga sus archivos:
   ```bash
   git clone https://github.com/MrUriosXD/mybb-language-translator.git
   ```
2. Abre `index.html` directamente en un navegador o publícalo en cualquier servidor web estático.
3. No es necesario configurar PHP, una base de datos ni ningún servicio backend.

---

## 💻 Uso de la Aplicación

1. **Carga los Archivos**: Arrastra o selecciona una carpeta de idiomas de MyBB (por ejemplo, la carpeta `english`), un archivo `.zip` o ficheros `.lang.php` individuales.
2. **Configura la Traducción**:
   - Selecciona el **Idioma Origen** y el **Idioma Destino**.
   - Elige el **Motor de Traducción** preferido.
   - Ajusta el intervalo entre peticiones si experimentas limitaciones del servicio.
   - Especifica el nombre del Pack y tu nombre como Traductor/Autor.
3. **Traduce**: Ejecuta la traducción automática masiva o edita manualmente cualquier cadena desde la tabla.
4. **Revisa**: Utiliza la búsqueda y los filtros para localizar cadenas traducidas o pendientes.
5. **Exporta**: Descarga los archivos individualmente o genera un `.ZIP` listo para colocar en el directorio de idiomas de MyBB (`inc/languages/`).

---

## 🛠️ Tecnologías Utilizadas

- **HTML5**: Estructura de la aplicación.
- **JavaScript (ES6+)**: Procesamiento de archivos, traducción, edición, filtros y exportación.
- **Tailwind CSS**: Estilizado moderno y responsivo.
- **Font Awesome 6**: Iconografía de la interfaz.
- **JSZip**: Lectura y generación de archivos `.zip` directamente en el navegador.

Las dependencias externas se cargan mediante CDN desde `index.html`.

---

## 📝 Licencia

Este proyecto está bajo la Licencia **MIT**. Consulta el archivo `LICENSE` para más detalles.
