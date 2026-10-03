# AURA Music

Android music player personal/local-first usando:

- `ytmusicapi`: búsqueda y metadatos de YouTube Music, sin YouTube Data API v3.
- `yt-dlp`: resolución del stream de audio sin descargar el archivo.
- `Media3 / ExoPlayer`: reproducción y sesión multimedia Android.
- `Chaquopy`: integra Python dentro del APK.
- WebView: interfaz AURA ligera y modificable desde `app/src/main/assets/index.html`.

## Flujo

`AURA UI -> Kotlin bridge -> Python -> ytmusicapi -> videoId -> yt-dlp -> URL temporal -> Media3`

No se incluye una API key de YouTube Data API v3.

## Compilar

Abrir la carpeta en Android Studio y ejecutar `assembleDebug`.

También hay un workflow de GitHub Actions en `.github/workflows/build.yml`.

## Nota sobre YouTube

La extracción no está garantizada permanentemente: YouTube cambia sus clientes y mecanismos de reproducción. Si yt-dlp necesita una actualización, se actualiza únicamente el componente Python.

El proyecto no descarga ni almacena canciones: reproduce el stream obtenido en tiempo real. El uso debe respetar los derechos y términos aplicables al contenido reproducido.
