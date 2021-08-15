Es posible tener más de una versión de NodeJS en Windows porque diferentes librerías de programación o diferentes proyectos pueden requerir que usemos una versión diferente. Para lograrlo podemos usar la herramienta nvm para instalar y activar diferentes versiones de nvm según lo necesitemos.

## Instalación de NVM para Windows
- [Descargar la última versión de NVM](https://github.com/coreybutler/nvm-windows/releases)
- Para esta guía se utilizó la versión 1.1.7 del archivo nvm-setup.zip
- Luego de descargar y descomprimir el archivo nvm-setup.zip. Ejecutar el instalador y éste preguntará las rutas de donde instalar el NVM y ubicar el NodeJS activo, es suficiente con aceptar la rutas por defecto.
- Para comprobar que la instalación fue correcta, abrir una terminal y ejecutar el comando que lista las instalaciones actuales de NodeJS (obviamente mostrará una lista vacía para empezar):

```bash
nvm ls
```

## Uso de NVM
Abre una terminal de Power Shell y utiliza el comando de instalación con la versión de NodeJS que deseas instalar como parámetro. Ejemplo para instalar la versión 12.22.5 de NodeJS:

```bash
nvm install 12.22.5
```

Y así puedes installar todas las versiones de NodeJS que necesites, y cuando quieras utilizar o activar una de ellas por defecto usas el comando de activación con la versión que necesitas. Ejemplo:

```bash
nvm use 12.22.5
```

Luego de eso cuando abras una consola de Windows (no tiene que ser una Power Shell) ya puedes utilizar los comandos node y npm, por ejemplo:

```bash
C:\Windows\system32>node -v
v12.22.5

C:\Windows\system32>npm -v
6.14.14
```
