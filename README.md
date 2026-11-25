# 🐟 Asesinato en el mar

Aplicación Android hecha en **Kotlin** con **Android Studio**. Es un proyecto académico de 2.º de DAM (Davante),
centrado en el diseño de pantallas, la navegación entre actividades y la interfaz de usuario.

## Qué hace

- **Inicio de sesión y registro** con los usuarios guardados en **SQLite** (`BaseDeDatos.kt`).
- **Contraseñas cifradas**: no se guardan en claro. Se usa **PBKDF2 con HMAC-SHA256**, una sal aleatoria por usuario
  y 120 000 iteraciones, y se comparan en tiempo constante (`MessageDigest.isEqual`).
- **Vídeo de fondo** en bucle en la pantalla de inicio, con un `TextureView` y un recorte que llena la pantalla sin deformar la imagen.
- **Animaciones de zoom** al pasar del login al registro y al volver.
- **Selección de personaje**: una rejilla (`GridView`) con 30 peces, cada uno con su imagen, y música de fondo.
- **Panel de administración** independiente.
- Las consultas a la base de datos se hacen en un hilo aparte para no bloquear la interfaz.

## Tecnologías

- Kotlin · Android SDK (minSdk 24)
- SQLite (`SQLiteOpenHelper`)
- `MediaPlayer`, `TextureView`, `GridView`, animaciones de vistas
- Gradle (Kotlin DSL)

## Cómo ejecutarlo

1. Clona el repositorio y ábrelo en **Android Studio**.
2. Espera a que Gradle sincronice.
3. Ejecuta en un emulador o un móvil con Android 7.0 o superior.

## Estructura

```
app/src/main/java/com/example/asesinatoenelmar/
├── MainActivity.kt          # Login + vídeo de fondo
├── RegistroActivity.kt      # Alta de usuarios
├── SeleccionPezActivity.kt  # Elegir personaje
├── AdminActivity.kt         # Panel de administración
├── BaseDeDatos.kt           # SQLite + hash de contraseñas
├── ListaPeces.kt / Pez.kt   # Datos de los personajes
```
