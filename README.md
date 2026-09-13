# 🌐 MyBB Language Translator

Una potente y moderna herramienta web para traducir de forma sencilla y automatizada los paquetes de idioma (`.lang.php`) del sistema de foros **MyBB**.

![PHP Version](https://img.shields.io/badge/PHP-7.4%2B-777BB4?style=flat-square&logo=php&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-3.0-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue.style=flat-square)

---

## 📋 Descripción

**MyBB Language Translator** es un traductor web dinámico en PHP/JS diseñado para la gestión de paquetes de traducción de MyBB. Permite cargar carpetas completas, archivos comprimidos en ZIP o ficheros `.lang.php` sueltos, traduciendo automáticamente sus cadenas mediante diversos motores de traducción, mientras respeta la estructura, variables internas (`$1`, `%s`, etc.) y etiquetas HTML del framework MyBB.

---

## ✨ Características Principales

- **📂 Flexibilidad de Carga**: Sube archivos `.php` individuales, carpetas completas o paquetes comprimidos en `.zip`.
- **🤖 Motores de Traducción Integrados**:
  - Google Translate (Gratuito)
  - MyMemory Translate
  - Lingva Translate
- **🧠 Preservación Inteligente de Formato**:
  - Mantiene intactas las variables dinámicas (ej. `%s`, `{1}`, `$foo`) y etiquetas HTML durante el proceso de traducción.
  - Respeta las mayúsculas iniciales según la convención del texto original.
- **⚙️ Personalización de Metadatos**:
  - Configura automáticamente el nombre del paquete de idioma (*Language Pack*) y la autoría (*Translator*) en las cabeceras PHP.
- **🎨 Interfaz Adaptativa e Intuitiva**:
  - Tema claro/oscuro (*Dark Mode*) con diseño responsivo potenciado por **Tailwind CSS**.
  - Control de intervalo de peticiones (ms) para evitar bloqueos por límite de tasa (*rate limit*).
  - Edición manual interactiva de cualquier cadena directamente desde la tabla.
  - Redimensionamiento de columnas y filtros por estado (*Pendientes*, *Traducidas*, *Buscar*).
- **📦 Exportación Completa o Individual**:
  - Descarga archivos modificados de forma independiente o genera la estructura completa en un archivo `.zip` mapeado al directorio del idioma destino (ej. `inc/languages/spanish/`).

---

## 📁 Archivos del Proyecto

El repositorio se compone de los siguientes ficheros principales:

```text
.
├── index.php         # Interfaz web principal y motor lógico (PHP / HTML5 / JS / Tailwind CSS)
├── languages.xml     # Archivo de configuración XML con los idiomas de origen/destino soportados
└── README.md         # Documentación general del repositorio
```

### Descripción de Componentes

1. **`index.php`**:
   - Carga la configuración del archivo `languages.xml`.
   - Proporciona la interfaz de usuario completa (Sidebar de configuración, Drag & Drop zona de carga, tabla interactiva de edición y métricas de progreso).
   - Procesa la extracción de cadenas `$l['clave'] = 'valor';` mediante JavaScript en el navegador.

2. **`languages.xml`**:
   - Define los idiomas disponibles tanto para la detección/origen como para el destino.
   - Vincula cada código ISO de idioma con el nombre estándar de la carpeta en MyBB (por ejemplo: `es` $\rightarrow$ `spanish`).

---

## 🚀 Instalación y Requisitos

### Requisitos Prácticos
- Servidor web con **PHP 7.4** o superior (Apache, Nginx, LiteSpeed, XAMPP, Local, etc.).
- Módulo `SimpleXML` de PHP activado para la lectura de `languages.xml`.

### Pasos de Instalación
1. Clona este repositorio o descarga los archivos en tu servidor web:
   ```bash
   git clone https://github.com/tu-usuario/mybb-language-translator.git
   ```
2. Asegúrate de colocar `index.php` y `languages.xml` en la misma carpeta raíz de tu servidor web.
3. Abre tu navegador y accede a la URL correspondiente (ej. `http://localhost/mybb-translator/index.php`).

---

## 💻 Uso de la Aplicación

1. **Carga los Archivos**: Arrastra o selecciona una carpeta de idiomas de MyBB (por ejemplo, la carpeta `english`), un archivo `.zip` o ficheros `.lang.php` individuales.
2. **Configura la Traducción**:
   - Selecciona el **Idioma Origen** y el **Idioma Destino**.
   - Elige el **Motor de Traducción** preferido.
   - Ajusta la velocidad/intervalo entre peticiones si experimentas saturación.
   - Especifica el nombre del Pack y tu nombre como Traductor/Autor.
3. **Traduce**: Haz clic en **Traducir** para la traducción automática masiva o edita individualmente cualquier celda en la tabla.
4. **Exporta**: Descarga el resultado comprimido en un archivo `.ZIP` listo para subir a tu directorio MyBB (`inc/languages/`).

---

## 🛠️ Tecnologías Utilizadas

- **PHP**: Lectura y parsing de configuración XML.
- **JavaScript (ES6+)**: Procesamiento en cliente, manipulación del DOM, comunicación con APIs de traducción y manipulación de ZIPs.
- **Tailwind CSS**: Estilizado moderno y responsivo.
- **FontAwesome 6**: Iconografía.
- **JSZip**: Generación y lectura de archivos comprimidos `.zip` directamente desde el navegador.

---

## 📝 Licencia

Este proyecto está bajo la Licencia **MIT**. Consulta el archivo `LICENSE` para más detalles.
