<div align="center">

<img src="icon.png" width="128" height="128" alt="Routine Meeting icon">

# Routine Meeting

**Meetings passieren. Notizen sollten nicht deine Aufgabe sein.**

[Website](https://mathguimaraes.github.io/routine-meeting/de/) · [Für macOS herunterladen](https://github.com/mathguimaraes/routine-meeting/releases/latest) · Apple Silicon · macOS 13+

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

## Das Problem

Du gehst in einen Call, und sobald es interessant wird, musst du dich entscheiden: zuhören oder mitschreiben. Den Anfang des Meetings verpasst, weil du nach einer Notiz-App suchst. Vergessen, die Aufnahme zu starten. Am Freitag angekommen mit sechs Meetings voller Entscheidungen und Aufgaben, die nur noch in deinem Kopf existieren.

Die meisten Aufnahme-Tools machen es schlimmer, nicht besser — man muss selbst an den Start-Knopf denken, sie laden das rohe Audio auf irgendeinen Server hoch, und die Hälfte kann deine Stimme nicht von den anderen unterscheiden.

## Was Routine Meeting macht

Routine Meeting sitzt still in deiner Menüleiste und erledigt alles, ohne dass du fragen musst:

- **Merkt, dass du in einem Meeting bist, und startet die Aufnahme von selbst — in *jeder* App.** Es ist keine Zoom/Meet/Teams-Integration mit einer festen Liste unterstützter Apps; es hört auf das Muster aus Mikrofon- und Systemaudio eines echten Gesprächs. Das funktioniert genauso mit Google Meet, Zoom, Microsoft Teams, Webex, Slack Huddles, Discord, FaceTime, WhatsApp-Anrufen oder einem Telefonanruf, der über deinen Mac läuft — alles mit Audio in beide Richtungen, ohne App-spezifische Einrichtung. Kein Knopf, an den man denken muss, kein "Moment, wurde das gerade aufgenommen?".
- **Transkribiert alles auf deinem Mac.** [WhisperKit](https://github.com/argmaxinc/WhisperKit) läuft auf der Apple-Silicon-Neural-Engine — das Audio verlässt nie dein Gerät.
- **Weiß, was du gesagt hast und was die anderen gesagt haben.** Mikrofon und Systemaudio werden getrennt aufgenommen, sodass Zusammenfassungen und Insights der richtigen Person zugeordnet werden.
- **Macht aus dem Transkript etwas Nützliches** — einen Titel, eine Stichpunkt-Zusammenfassung, Aufgaben und optional eine ehrliche Einschätzung, wie du dich in diesem konkreten Gespräch geschlagen hast, egal ob 1:1, Kundengespräch oder Design-Review.
- **Fasst alles in einem Tagesbericht zusammen** — was heute in allen Meetings passiert ist und was du jemandem noch schuldest.

Du bringst deinen eigenen [Gemini-API-Key](https://aistudio.google.com/apikey) für die KI-Ebene mit (die kostenlose Stufe reicht für den persönlichen Gebrauch locker) — oder verzichtest ganz auf den Key und lässt ein lokales Modell auf deinem Gerät laufen.

## Warum es so gebaut ist

- **App-unabhängig by design.** Die meisten Meeting-Recorder funktionieren nur mit ein paar großen Apps, weil sie gegen deren jeweilige SDKs integrieren. Routine Meeting erfasst stattdessen auf Systemaudio-Ebene — jede App, die auf deinem Mac Ton macht, zählt, egal was dein Team, dein Kunde oder deine Familie nutzt.
- **Local-first.** Aufnahme und Transkription laufen auf deinem Mac, unabhängig davon, ob du je einen API-Key hinzufügst. Das Einzige, was dein Gerät verlassen kann, ist ein Text-Transkript, und nur wenn du Cloud-Zusammenfassungen aktivierst.
- **Keine Konten, kein Abo.** Es ist eine native App, kein SaaS-Wrapper. Dir gehört die DMG, dir gehören deine Daten.
- **Gebaut für echte Meetings.** Fehlalarme (Musik, eine zufällige Sprachnachricht) werden nicht zu Phantom-Aufnahmen; ein Mikrofon, das mitten im Call ausfällt, lässt nicht heimlich die Hälfte des Transkripts verschwinden.

## Was Routine Meeting anders macht

Die meisten Meeting-Assistenten, ob mit sichtbarem Bot (Fireflies, Otter) oder "botloser" Aufnahme (Fellow, Fathom), schicken deine Aufnahme und dein Transkript trotzdem zur Verarbeitung an ihre Server. Routine Meeting geht anders vor: Alles passiert auf deinem Mac.

- **Nichts verlässt dein Gerät.** Aufnahme und Transkription laufen vollständig lokal. Das gilt auch im Vergleich zu Tools, die sich als "botlos" vermarkten, denn botlos bedeutet nur, dass kein sichtbarer Teilnehmer dem Call beitritt — nicht, dass deine Daten lokal bleiben. Solange du nicht explizit Cloud-KI-Zusammenfassungen aktivierst, lädt Routine Meeting nie etwas hoch.
- **Funktioniert automatisch in jeder App.** Routine Meeting erkennt Meetings am Muster aus Mikrofon- und Systemaudio eines echten Gesprächs, nicht durch Beitritt als Teilnehmer oder Anbindung an die API einer bestimmten App. Das heißt, Google Meet, Zoom, Teams, Webex, Slack Huddles, Discord, FaceTime oder ein über den Mac laufender Telefonanruf funktionieren alle gleich, ohne App-spezifische Einrichtung.
- **Eigener Key oder ganz ohne Cloud.** KI-Zusammenfassungen nutzen deinen eigenen Gemini-API-Key (die kostenlose Stufe reicht für den persönlichen Gebrauch), oder du lässt ein vollständig lokales Modell laufen — ohne Key und ohne Cloud-Aufrufe.
- **Kein Konto, kein Abo.** Routine Meeting ist kostenlos und verlangt keine Registrierung.

### Was noch fehlt

Um ehrlich zu sein: Routine Meeting ist eine von einer einzelnen Person gebaute macOS-App, keine finanzierte Plattform. Ein paar Dinge, die Fireflies, Fellow und ähnliche Tools bieten, Routine Meeting aber nicht:

- Meetingübergreifende Suche oder eine langfristig durchsuchbare Wissensdatenbank (aktuell nur ein Tagesüberblick)
- Integrationen mit CRMs, Slack, Recruiting-Tools oder Dialern
- Enterprise-Compliance-Zertifizierungen (SOC 2, HIPAA, GDPR)
- Windows- oder Mobile-Unterstützung

Falls du das heute brauchst, ist eine Plattform wie Fireflies oder Fellow wahrscheinlich die bessere Wahl, besonders in regulierten Branchen, wo diese Zertifizierungen zählen. Wenn du dagegen etwas willst, das nie deinen Mac verlässt und weder einen Bot noch ein Cloud-Konto braucht, ist genau das die Lücke, die Routine Meeting füllt.

## Installation

1. Lade das aktuelle `RoutineMeeting.dmg` von [Releases](https://github.com/mathguimaraes/routine-meeting/releases/latest) herunter.
2. Öffne die DMG und ziehe **Routine Meeting** in den **Programme**-Ordner.
3. Starte die App. Eine kurze Einrichtungshilfe erklärt jede Berechtigung — wofür sie gebraucht wird — und dann den Systemdialog (Mikrofon, Bildschirmaufnahme, Anmeldeobjekt, Bedienungshilfen, Mitteilungen), bevor du einen Gemini-Key hinzufügst oder den lokalen Modus wählst. Der Bildschirmaufnahme-Schritt erfasst das Audio der anderen Teilnehmer und löst den lila Aufnahme-Punkt aus; das ist normal und erforderlich.
4. Diese Anleitung kannst du jederzeit über das Menüleisten-Symbol → **Setup-Anleitung…** erneut aufrufen.

Aufnahmen, die älter als 7 Tage sind, werden automatisch gelöscht, sobald sie transkribiert wurden (Transkripte/Zusammenfassungen bleiben für immer erhalten) — einstellbar unter Einstellungen → Speicher, mit einem manuellen "Jetzt Speicherplatz freigeben"-Button.

Routine Meeting prüft automatisch auf Updates (über [Sparkle](https://sparkle-project.org)) und benachrichtigt dich in der App, sobald eine neue Version bereitsteht.

## Datenschutz

Audio und Transkripte bleiben auf deinem Mac. Es wird nichts irgendwohin gesendet, es sei denn, du aktivierst einen Cloud-KI-Anbieter — und selbst dann geht nur der Transkript-Text raus, nie das rohe Audio.

Die App sendet außerdem einmal täglich einen anonymen Ping (eine zufällige ID ohne Meeting-Inhalte, Namen oder E-Mail), damit ich die grobe Nutzung sehen kann. Standardmäßig aktiviert; jederzeit abschaltbar unter Einstellungen → Datenschutz, ohne dass sich sonst etwas ändert.

## Feedback / Probleme

Menüleisten-Symbol → **Feedback senden…** in der App, oder öffne hier ein [Issue](https://github.com/mathguimaraes/routine-meeting/issues).
