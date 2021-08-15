En esta guía haremos una App demostrativa utilizando IONIC con REACT. Es importante aclarar que el objetivo principal no es aprender a programar sino dar a conocer IONIC para tener una base de que es y como funciona a nivel básico, y con ese conocimiento decidir si se desea continuar estudiándola a profundidad.

## Qué es IONIC
Es un framework para construir Apps híbridas. Básicamente es una herramienta que nos permite utilizar nuestros conocimientos haciendo páginas web con Vue, Javascript, Angular o React para aplicarlas en la creación de una App híbrida que funcione en un dispostivo móvil. Si bien es cierto no es requisito conocer ni Vue ni Angular ni React y solamente utilizar Javascript, no es lo recomendable porque la mejor documentación disponible es cuando se utiliza una de las librerías mencionadas y porque además, a largo plazo, conocer ya sea Vue o Angular o React tiene ventajas adicionales así que es mejor utilizar una de ellas. Las tres opciones son válidas y elegir una depende principalmente de con cuál te sientas mas a gusto. Para esta guía vamos a utilizar IONIC combinado con React porque la visión general es que el conocimento adquirido sirva también luego cuando aprendamos React para páginas web o React Native para hacer Apps nativas.

Es importante saber que IONIC nos permite fácilmente utilizar Capacitor, porque luego de que hemos programado nuestra aplicación usando IONIC, el siguiente paso es empaquetarla de manera tal que funcione en dispositivos móviles y allí es donde usaremos Capacitor.

En este enlace se pueden leer [Detalles de IONIC](https://profile.es/blog/que-es-ionic/)

En este enlace se pueden leer [Detalles de Capacitor](https://alotroladodeltelefonoblog.wordpress.com/2020/02/01/capacitor-el-nuevo-apache-cordova/)

## Verificar requisitos antes de continuar
- Un dispostivo móvil con sistema operativo Android
- Contar con Sistema Operativo Windows (Se utilizó Windows 10 para elaborar esta guía pero los pasos en teoría pueden ajustarse para ser usados en cualquier Windows 7 o superior)
- Tener Android Studio instalado. Nota: la última versión de Android Studio (Agosto 2021) coloca por defecto la versión de compilación de android en versión 31 para Android 12 que no funciona correctamente. Cambia la configuración por defecto y usar la versión 30 para Android 11)[https://developer.android.com/about/versions/11/setup-sdk?hl=es-419], lo cual no significa que solamente se van a poder hacer aplicaciones para Android versión 11, es solamente un ajuste de compilación.
- Conocer el manejo de la terminal de Windows
- Conocimiento básico de NodeJS

## Configuración de ambiente
Verifica que tiens NodeJS versión 12.x instalado. No se recomienda utilizar una versión superior a esa. Si ya tienes otra versión instalada y deseas tener más de una versión de NodeJS en Windows puedes ver la guía de [como tener varias versiones de NodeJS en Windows](http://docs.dalatcomunidad.org/repositorio/como-tener-varias-versiones-de-nodejs-en-windows/)

Verifica que tienes java versión 8 con este comando, es importante que no uses openJDK, utiliza la versión de Oracle:
```bash
java -fullversion
```
Es complicado pero no imposible conseguir específicamente esa versión de java 8 porque es algo vieja. Si no logras encontrarlo en internet aquí hay una copia para (descarga de oracle java 8)[https://drive.google.com/drive/folders/1ix3hB9nyfgTLpWXhcf0CEuzkVuS-1_b3?usp=sharing]. Descomprime java en cualquier carpeta y y agrega su subcarpeta "bin" en tu ruta path.

Ubica donde se están las librerías de desarrollo de Android, conocido como Android SDK en tu computador. Esto se descargó cuando instalaste Android Studio. Aquí un ejemplo de donde suelen estar, considera que en este ejemplo "zaq" es el nombre del usuario:
```bash
C:\Users\zaq\AppData\Local\Android\Sdk
```

Una vez que ubicaste esa carpeta, crea una variable de ambiente llamada ANDROID_SDK_ROOT que apunte a esa carpeta. Puedes hacerlo en el panel de control de Windows o con el siguiente comando como administrador en una Power Shell:
```bash
setx ANDROID_SDK_ROOT C:\Users\zaq\AppData\Local\Android\Sdk /M
```

La carpeta Android SDK tiene subcarpetas que necesitamos agregar en el path, estos son los comandos para hacerlo (recuerda que "zaq" varía según nombre de usuario):
```bash
set path=%path%;C:\Users\zaq\AppData\Local\Android\Sdk\tools\bin
set path=%path%;C:\Users\zaq\AppData\Local\Android\Sdk\platform-tools
set path=%path%;C:\Users\zaq\AppData\Local\Android\Sdk\emulator
set path=%path%;C:\Users\zaq\AppData\Local\Android\Sdk\build-tools
```

Verifica que puedes utilizar el comando adb (es parte del Android SDK) para detectar tu dispostivo Android conectado a un puerto USB de tu computadora:
```bash
adb devices
```
Si el comando anterior no lista tu dispositivo móvil prueba otro puerto USB y también prueba utilizar otro cable de datos USB ya que éstos suelen averiarse con el uso. Nota: Que que un cable USB sirva para darle corriente eléctrica a un dispostivo móvil no es prueba suficiente para demostrar que también debería funcionar con el comando adb, son dos temas diferentes.
 
Instala el software gradle, para esta guía fue suficiente con (descargar la versión binaria versión 5.6.2 de gradle)[https://gradle.org/next-steps/?version=5.6.2&format=bin]. Descomprime gradle en cualquier carpeta y agrega su subcarpeta "bin" en tu ruta path de manera tal que el siguiente comando te funcione correctamente:
```bash
gradle -version
```

## Crear una App con IONIC
Ejecutar el comando de instalación de IONIC:
```bash
npm install -g @ionic/cli
```

Ahora vamos a crear un esqueleto de proyecto IONIC que utiliza React y de nombre le pondremos "demo2"
```bash
ionic start demo2 tabs --type=react
```
Si ese comando en algún momento nos pide crear un usuario o registrarnos, decirle que no (o solamente apretar enter porque "no" es la opción por defecto)

Si el comando anterior funcionó correctamente, tenemos un proyecto IONIC que usó la plantilla llamada "tabs" que muestra tres pantallas diferentes, con pantallas creadas con html y React.

Este paso es opcional: Si deseas, puedes ver la aplicación en tu computador primero, antes de compilarla para un dispositivo móvil, para esto, ingresa en la carpeta del proyecto y enciéndelo como si fuera un proyecto web:
```bash
cd demo2
ionic serve
```
Y eso te va a dar una ruta que si la ingresas en tu navegador puedes ver las pestañas y probarlas. Vas a notar que la accesibilidad de lo creado es muy básica pero recuerda que primero nos enfocamos en conocer la herramienta como tal.

## Ejecutar la App IONIC en nuestro dispositivo móvil
Asegúrate primero que tu computador puede detectar tu dispositivo con el comando adb como mencionamos en un paso previo. Y déjalo conectado.

Ingresa a la carpeta del proyecto y ejecuta los siguientes comandos para primero agregar Capacitor al proyecto, y luego empaquetarlo, instalarlo y ejecutarlo en el dispotivo móvil:
```bash
cd demo2
ionic capacitor add android
ionic capacitor run android
```

Si no hubieron problemas debes tener ahora la aplicación funcionando en tu dispositivo móvil Android. Felicitaciones!.
