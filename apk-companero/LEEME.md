# Mi Compañero – proyecto Android (Capacitor 8)

La app web está en `www/index.html`. Este proyecto la convierte en app nativa para que los
**avisos de eventos suenen con la app cerrada** (también tras reiniciar el teléfono).

## Compilar sin instalar nada (GitHub)
1. Sube esta carpeta a un repositorio de GitHub.
2. Pestaña **Actions → Compilar APK → Run workflow**.
3. Al terminar, descarga `MiCompanero-debug-apk` (APK para probar en tu teléfono).

## Compilar en tu PC (para Play Store)
1. Instala Node 22 y Android Studio.
2. En esta carpeta: `npm install` y luego `npx cap sync android`.
3. `npx cap open android` → menú **Build → Generate Signed Bundle / APK → Android App Bundle (.aab)**.
4. Crea tu llave (keystore) y **guárdala y respáldala: sin ella no podrás actualizar la app**.
5. Sube el `.aab` a Google Play Console.

## Después de cambiar la app
Edita `www/index.html`, ejecuta `npx cap sync android` y vuelve a compilar.

## Antes de publicar
- Cambia `appId` en `capacitor.config.json` (ahora `com.micompanero.app`); no se puede cambiar después de publicar.
- Sube `icono-512-playstore.png` como icono de la ficha.
- Play exige política de privacidad (di que los datos se guardan solo en el teléfono) y el formulario de seguridad de datos.
- Permisos que declara la app: notificaciones, alarmas exactas, micrófono, vibración y reinicio. Justifícalos en Play Console.
- En el teléfono: al abrir la app acepta las notificaciones y activa "Alarmas y recordatorios" para que avise a la hora exacta.
