Existen diferentes caminos para programar una aplicación móvil así que primero haremos una revisión rápida de las opciones disponibles:

## Crear una App nativa
Su principal ventaja es que el resultado ofrece la mejor performance y las mejores características y opciones de ajuste de accesibilidad. Además la mayor cantidad de documentación y tutoriales que existen son para este camino. Ejemplos de herramientas que se necesitan conocer para ir por este camino: Java o Kotlin para Android, Objective-C o Swift para iOS. Conocer y usar a detalle las herramientas IDE como Android Studio o Xcode. Como consecuencia este camino es generalmente el más difícil de aprender pero el que otorga mayores beneficios a largo plazo. Históricamente además crear este tipo de pantallas requiere conocer y usar archivos de configuración o diseño de pantallas basados en formato XML u otro, que complica todavía más su uso, sin embargo, versiones recientes de Kotlin y otras tecnologías muestran la tendencia a reducir o simplificar esto, por ejemplo con Kotlin Compose ya no es necesario siquiera utilizar archivos XML y solamente se requiere declarar la pantalla en código.

Notas:
- Con Flutter se pueden crear aplicaciones nativas, usando el lenguaje Dart y no es obligatorio usar Android Studio.
- React es una tecnología para crear aplicaciones web. React Native es una tecnología para crear aplicaciones nativas App para dispositivos móviles.

## Crear una App híbrida
En este camino se utilizan archivos html, css o javascript, que mediante un proceso especial de compilación genera una App que por fuera tiene toda la característica de una App nativa pero que por dentro tiene un mini navegador web embebido. Es como crear una mini página web que vive dentro de la App. Ejemplos de herramientas que se utilizan para hacer Apps híbridas:

- Apache Phonegap (No se recomienda usarlo más, está quedando desfazado)
- Capacitor (Es lo que se recomienda ahora en lugar de Apache Phonegap)
- Appcelerator Titanium (Muy popular y recomendado, sin embargo su documentación indica que posiblemente esta herramienta sea cancelada o pierda soporte pronto. Tener cuidado y revisar siempre la documentación de una herramienta antes de usarla)
- Ionic (Es el camino recomendado para crear una aplicación híbrida porque permite reutilizar conocimiento de Vue o Angular o React y combinarlo con Capacitor para crear una App híbrida)

Notas:
- Existen otras formas y alternativas pero en esta guía solamente nos enfocaremos en las que el proceso de creación de la app sea accesible y que además el resultado generado sea una app accesible.

## Que camino elegir
Es inútil discutir cuál es el mejor camino o la mejor herramienta y descartar el resto. La tecnología cambia constantemente y mañana una puede ofrecer alguna ventaja que antes no tenía. Es mejor conocer al menos a alto nivel cada una, compararla con el proyecto que se necesita hacer y también con las habilidades que el equipo de programación ya posea. Bajo esa perspectiva existen varios escenarios posibles pero aquí van algunas guías (no son reglas, solamente recomendaciones) a seguir para ayudar a elegir que camino tomar:

- Si nunca haz programado antes o nunca haz programa una App para dispositivo móvil, se recomienda primero programar una web para que primero consigas experiencia programando y no te compliques con hardware adicional (el dispositivo móvil). Programar una web por ejemplo solamente requiere un bloc de notas y un navegador web y con eso ya puedes empezar. Y luego de eso puedes intentar programar una aplicación App híbrida.
- Si bien es cierto la mejor accesibilidad se obtiene usualmente solamente haciendo una aplicación nativa, si tu App tiene una funcionalidad básica de solamente algunas pantallas, botones y algunos textos, es probable que el mayor tiempo y costo de hacer una aplicación nativa no justifique el esfuerzo si solamente requieres accesibilidad básica.
- Si tu aplicación requiere procesar una cantidad grande de datos y mostrar gráficas avanzas en 3D o requiere una interfaz visual muy compleja o avanzada, por ejemplo un juego muy avanzando, la recomendación es hacer una App nativa.
- Si tu aplicación tiene funcionalidad básica solamente como de botones, listas, formularios, .etc. entonces es suficiente utilizar una herramienta de creación de App híbrida.
- Existe una herramienta llamada React Native Expo que promete hacer aplicaciones nativas muy rápidas y de manera muy fácil. Esto es cierto, pero se recomienda no utilizarla porque en tecnología siempre se cumple que mientras más fácil y rápida sea trabajar con una herramienta más complicado luego será modificarla o mejorarla después cuando desees añadirle funcionalidad adicional. Se recomienda evitar su uso o usarla solamente para una prueba inicial y descartarla lo más pronto posible. Si vas por el camino React Native, se recomienda utilizar React Native (así a secas, sin "Expo").
- Si tu intención a largo plazo es dedicarte a la creación de aplicaciones App a nivel profesional o empresarial, te conviene enfocarte en la creación de aplicationes nativas.
- Si es importante que desde el inicio la aplicación exista tanto en Android como en iOS te conviene enfocarte no en si la App debe ser nativa o híbrida sino en que sea multiplataforma desde su nacimiento, en ese caso te conviene utilizar una de estas tecnologías: Flutter o IONIC o React Native.
- Históricamente las aplicaciones Android se hacían con java. Para toda App nueva para Android se recomienda utilizar Kotlin.
- Si deseas hacer un juego básico que por ejemplo solamente utiliza imágenes en 2D o mecánicas simples como juegos de cartas, es posible que una aplicación híbrida sea suficiente. De hecho ya se han hecho juegos que combinan Phaser (librería javascript para juegos) con Capacitor.

## Qué haremos en esta guía de desarrollo
Crearemos Apps para Android de manera práctica y accesible como prioridad y como objetivo adicional que sea una base para los que luego quieran especializarse en considerarlo una carrera profesional. Un camino interesante y práctico es utilizar la tecnología React, porque, si uno aprende a hacer webs con React, lo aprendido sirve luego para hacer Apps híbridas con IONIC+React y eso a su vez sirve de experiencia para aprender a hacer una App nativa con React Native (es importante notar que con React se reutiliza conocimiento, no código). Teniendo eso en cuenta haremos:

- [Crear una App híbrida con IONIC+React](http://docs.dalatcomunidad.org/repositorio/ionic/)
- Crear una App nativa con React Native
- Crear una App nativa con Kotlin
