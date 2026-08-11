<div align="center">

<img src="icon.png" width="128" height="128" alt="Routine Meeting icon">

# Routine Meeting

**Las reuniones pasan. Tomar notas no debería ser cosa tuya.**

[Descargar para macOS](https://github.com/mathguimaraes/routine-meeting/releases/latest) · Apple Silicon · macOS 13+

[![en](https://img.shields.io/badge/lang-en-red.svg)](README.md)
[![es](https://img.shields.io/badge/lang-es-yellow.svg)](README.es.md)
[![pt--br](https://img.shields.io/badge/lang-pt--br-green.svg)](README.pt-BR.md)
[![ja](https://img.shields.io/badge/lang-ja-blue.svg)](README.ja.md)
[![de](https://img.shields.io/badge/lang-de-orange.svg)](README.de.md)
[![fr](https://img.shields.io/badge/lang-fr-lightgrey.svg)](README.fr.md)
[![ko](https://img.shields.io/badge/lang-ko-blueviolet.svg)](README.ko.md)
[![zh--cn](https://img.shields.io/badge/lang-zh--cn-critical.svg)](README.zh-CN.md)

</div>

---

## El problema

Te unes a una llamada y, en cuanto se pone interesante, tienes que elegir: prestar atención o escribir. Te pierdes el inicio de la reunión buscando una app de notas. Se te olvida darle a grabar. Llegas al viernes con seis reuniones de decisiones y tareas que solo viven en tu memoria.

La mayoría de las herramientas de grabación empeoran esto, no lo mejoran: hay que acordarse de pulsar grabar, mandan el audio en bruto a algún servidor, y muchas ni siquiera distinguen tu voz de la de los demás.

## Qué hace Routine Meeting

Routine Meeting se queda en tu barra de menú y se encarga de todo sin que se lo pidas:

- **Detecta que estás en una reunión y empieza a grabar solo, en *cualquier* app.** No es una integración con Zoom/Meet/Teams limitada a una lista fija de apps compatibles; escucha el patrón de micrófono + audio del sistema de una conversación real. Funciona igual con Google Meet, Zoom, Microsoft Teams, Webex, Slack huddles, Discord, FaceTime, llamadas de WhatsApp, o una llamada de teléfono redirigida a tu Mac — cualquier cosa con audio en ambos sentidos, sin configurar nada por app. Sin botón que recordar, sin ese momento de "¿esto se estaba grabando?".
- **Transcribe todo en tu Mac.** [WhisperKit](https://github.com/argmaxinc/WhisperKit) corre en el Neural Engine de Apple Silicon — el audio nunca sale de tu equipo.
- **Sabe qué dijiste tú y qué dijeron los demás.** El micrófono y el audio del sistema se capturan y separan, así que los resúmenes e insights se atribuyen a la persona correcta.
- **Convierte la transcripción en algo útil** — un título, un resumen en puntos, tareas pendientes y, opcionalmente, una lectura honesta de cómo te desempeñaste en esa conversación concreta, sea un 1:1, una llamada con un cliente o una revisión de diseño.
- **Lo junta todo en un informe diario** — qué pasó hoy, en todas las reuniones, y qué le debes todavía a alguien.

Usas tu propia [clave de API de Gemini](https://aistudio.google.com/apikey) para la capa de IA (el nivel gratuito cubre de sobra el uso personal) — o te saltas la clave por completo y corres un modelo local en tu equipo.

## Por qué está construido así

- **Agnóstico a la app, por diseño.** La mayoría de los grabadores de reuniones solo funcionan con un par de apps grandes porque se integran contra el SDK de cada una. Routine Meeting captura a nivel de audio del sistema — cualquier app que haga sonido en tu Mac vale, así que no importa qué haya estandarizado tu equipo, tu cliente o tu familia.
- **Local primero.** La grabación y la transcripción ocurren en tu Mac sin importar si añades o no una clave de API. Lo único que puede salir de tu equipo es una transcripción en texto, y solo si activas los resúmenes en la nube.
- **Sin cuentas, sin suscripción.** Es una app nativa, no un envoltorio de SaaS. El DMG es tuyo, tus datos son tuyos.
- **Pensado para cómo son las reuniones de verdad.** Los falsos positivos (música, un mensaje de voz suelto) no se convierten en grabaciones fantasma; que se caiga el micrófono a mitad de llamada no te hace perder silenciosamente media transcripción.

## En qué se diferencia Routine Meeting

La mayoría de los asistentes de reuniones, ya usen un bot visible (Fireflies, Otter) o captura "sin bot" (Fellow, Fathom), igual mandan tu grabación y transcripción a sus servidores para procesarlas. Routine Meeting hace algo distinto: todo pasa en tu Mac.

- **Nada sale de tu equipo.** La grabación y la transcripción se ejecutan enteramente en el dispositivo. Esto es cierto incluso frente a herramientas que se venden como "sin bot", porque eso solo significa que ningún participante visible se une a la llamada, no que tus datos se queden en local. A menos que actives explícitamente los resúmenes de IA en la nube, Routine Meeting nunca sube nada.
- **Funciona en cualquier app, automáticamente.** Routine Meeting detecta reuniones escuchando el patrón de micrófono + audio del sistema de una conversación real, no uniéndose como participante ni enganchándose a la API de una app concreta. Eso significa que Google Meet, Zoom, Teams, Webex, Slack huddles, Discord, FaceTime o una llamada de teléfono redirigida a tu Mac funcionan todos igual, sin configurar nada por app.
- **Usa tu propia clave, o sáltate la nube por completo.** Los resúmenes de IA usan tu propia clave de API de Gemini (el nivel gratuito cubre el uso personal), o puedes correr un modelo completamente local, sin clave y sin llamadas a la nube.
- **Sin cuenta, sin suscripción.** Routine Meeting es gratis y no te pide que te registres en nada.

### Lo que todavía no tenemos

Para ser honestos: Routine Meeting es una app de macOS hecha por una sola persona, no una plataforma con financiación. Algunas cosas que Fireflies, Fellow y herramientas similares ofrecen y Routine Meeting no:

- Búsqueda entre reuniones o una base de conocimiento buscable a largo plazo (por ahora, limitado a un resumen diario)
- Integraciones con CRMs, Slack, herramientas de reclutamiento o marcadores telefónicos
- Certificaciones de cumplimiento empresarial (SOC 2, HIPAA, GDPR)
- Soporte para Windows o móvil

Si necesitas algo de eso hoy, una plataforma como Fireflies o Fellow probablemente encaje mejor, sobre todo en sectores regulados donde esas certificaciones importan. Si lo que quieres es algo que nunca sale de tu Mac y no necesita un bot (ni una cuenta en la nube) para funcionar, ese es exactamente el hueco que llena Routine Meeting.

## Instalación

1. Descarga el último `RoutineMeeting.dmg` desde [Releases](https://github.com/mathguimaraes/routine-meeting/releases/latest).
2. Abre el DMG y arrastra **Routine Meeting** a **Aplicaciones**.
3. Ábrelo. Una guía corta te explica cada permiso — por qué hace falta, y luego el aviso del sistema (Micrófono, Grabación de pantalla, Abrir al iniciar sesión, Accesibilidad, Notificaciones) — y te deja añadir una clave de Gemini o saltar al modo local. El paso de Grabación de pantalla es el que captura el audio de los demás participantes y activa el punto morado de grabación; eso es normal y necesario.
4. Vuelve a esta guía cuando quieras desde el ícono de la barra de menú → **Guía de configuración…**.

Las grabaciones de más de 7 días se borran automáticamente una vez transcritas (las transcripciones y resúmenes se guardan para siempre) — configurable en Ajustes → Almacenamiento, con un botón manual de "Liberar espacio ahora".

Routine Meeting busca actualizaciones automáticamente (vía [Sparkle](https://sparkle-project.org)) y te avisa dentro de la app cuando hay una versión nueva.

## Privacidad

El audio y las transcripciones se quedan en tu Mac. No se envía nada a ningún sitio salvo que actives un proveedor de IA en la nube — e incluso entonces, solo sale el texto de la transcripción, nunca el audio en bruto.

La app también manda un ping anónimo al día (un ID aleatorio sin contenido de reuniones, nombre ni email) para que pueda ver el uso aproximado. Está activado por defecto; puedes desactivarlo cuando quieras en Ajustes → Privacidad, sin que cambie nada más.

## Comentarios / Problemas

Ícono de la barra de menú → **Enviar comentarios…** en la app, o abre un [issue](https://github.com/mathguimaraes/routine-meeting/issues) aquí.
