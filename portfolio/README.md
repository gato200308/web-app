# Portafolio - plantilla

Esta carpeta contiene una plantilla sencilla para publicar tu proyecto Android con enlace de descarga del APK y una explicación.

Cómo usar
- Copia tu APK dentro de `portfolio/assets/` y nómbralo `myapp.apk`, o cambia el enlace en `index.html` a la URL donde esté alojado el APK (por ejemplo GitHub Releases, Google Drive, un bucket S3 o CDN).
- Personaliza el título, la explicación, capturas y enlaces en `index.html`.


Probar localmente

1) Archivo APK ya incluido (nombre)

 - En esta copia he puesto el enlace a <code>assets/app-release.apk</code> porque el APK en `assets/` se llama `app-release.apk`. Si prefieres otro nombre, renombra el archivo en `assets/` o actualiza el enlace en `index.html`.

2) Servir la carpeta estática (sitio)

Si tienes Python instalado, puedes servir la carpeta `portfolio` con un servidor HTTP estático:

```fish
cd /home/molina/Documentos/opta-2/web-app/portfolio
python3 -m http.server 8000
# luego abre http://localhost:8000 o http://<TU-IP>:8000 en tu navegador
```

3) Probar la app con tu backend

- Repositorio cliente (Flutter): https://github.com/gato200308/guru-flutter.git
- Repositorio API (backend): https://github.com/gato200308/backendguru.git
- Backend en producción: https://gurubackend.usbtopia.usbbog.edu.co/

Descripción del proyecto (ejemplo)

Guru App es una plataforma de comercio para artesanías que permite a los artesanos crear cuentas,
publicar productos con imágenes y descripciones, gestionar inventarios, y recibir pedidos de
compradores en cualquier lugar. Incluye funciones de carrito, favoritos, reseñas y un flujo de
pedidos con historial. El cliente está hecho en Flutter (multiplataforma) y el backend en PHP
con MySQL para almacenar usuarios, productos y pedidos.

Puedes usar este texto como base para la página del proyecto y personalizarlo con ejemplos
concretos, capturas y enlaces.

Si ejecutas la API localmente en tu máquina (por ejemplo PHP+Apache o `php -S`), usa la IP de tu máquina (ej. `http://192.168.1.5:8000`) como base URL en la app durante las pruebas.

Nota sobre emuladores/dispositivos:

- Si pruebas desde un emulador Android estándar (Android Studio), la IP especial `10.0.2.2` apunta a la máquina host.
- Si pruebas en un dispositivo físico, asegúrate de que el dispositivo y tu PC estén en la misma red y usa la IP local de tu PC.

Verificación de integridad (recomendada)

Genera el hash SHA256 del APK y muéstralo en la página para que los usuarios verifiquen la integridad:

```fish
cd /home/molina/Documentos/opta-2/web-app/portfolio/assets
sha256sum app-relase.apk
# copia el hash y pégalo en index.html cerca del botón de descarga si quieres
```

Alternativas de despliegue
- GitHub Pages: Si pones esta carpeta en la rama `gh-pages` o en la raíz de un repo y habilitas Pages.
- Netlify / Vercel: Arrastra la carpeta `portfolio` a la interfaz o conecta el repo.
- GitHub Releases: Para ofrecer el APK como descarga oficial, súbelo como un release y enlaza ese archivo desde `index.html`.

Seguridad y privacidad
- No subas claves privadas, certificados o archivos con datos sensibles al APK ni al repositorio público.
- Indica claramente los permisos que solicita la app para evitar desconfianza.

Siguientes mejoras sugeridas
- Añadir un formulario de contacto o enlaces a redes.
- Agregar contadores de descargas (requiere servidor o servicio externo).
- Implementar verificación de integridad automatizada (mostrar hash y firma), y/o GitHub Actions para publicar releases automáticamente.

