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
