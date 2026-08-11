<div align="center">

<img src="icon.png" width="128" height="128" alt="Routine Meeting icon">

# Routine Meeting

**Les réunions arrivent. Prendre des notes ne devrait pas être votre travail.**

[Télécharger pour macOS](https://github.com/mathguimaraes/routine-meeting/releases/latest) · Apple Silicon · macOS 13+

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

## Le problème

Vous rejoignez un appel, et dès que ça devient intéressant, il faut choisir : écouter ou noter. Vous ratez le début de la réunion en cherchant une appli de notes. Vous oubliez d'appuyer sur enregistrer. Vendredi arrive avec six réunions de décisions et de tâches qui n'existent nulle part ailleurs que dans votre mémoire.

La plupart des outils d'enregistrement empirent les choses au lieu de les améliorer — il faut penser à appuyer sur le bouton, ils envoient l'audio brut sur un serveur, et la moitié n'arrive même pas à distinguer votre voix de celle des autres.

## Ce que fait Routine Meeting

Routine Meeting reste discrètement dans votre barre de menu et s'occupe de tout sans qu'on le lui demande :

- **Remarque que vous êtes en réunion et se met à enregistrer tout seul — dans *n'importe quelle* appli.** Ce n'est pas une intégration Zoom/Meet/Teams limitée à une liste fixe d'applis prises en charge ; il écoute le motif micro + audio système d'une vraie conversation. Ça fonctionne donc pareil avec Google Meet, Zoom, Microsoft Teams, Webex, les huddles Slack, Discord, FaceTime, les appels WhatsApp, ou un appel téléphonique relayé sur votre Mac — tout ce qui a de l'audio dans les deux sens, sans réglage par appli. Pas de bouton à retenir, pas de moment "attends, est-ce que ça enregistrait ?".
- **Transcrit tout sur votre Mac.** [WhisperKit](https://github.com/argmaxinc/WhisperKit) tourne sur le Neural Engine d'Apple Silicon — l'audio ne quitte jamais votre machine.
- **Sait ce que vous avez dit et ce que les autres ont dit.** Le micro et l'audio système sont capturés et séparés, donc les résumés et les insights sont attribués à la bonne personne.
- **Transforme la transcription en quelque chose d'utile** — un titre, un résumé à puces, des actions à mener et, en option, un retour honnête sur votre performance dans cette conversation précise, que ce soit un 1:1, un appel client ou une revue de design.
- **Regroupe tout dans un rapport quotidien** — ce qui s'est passé aujourd'hui, à travers toutes les réunions, et ce que vous devez encore à quelqu'un.

Vous utilisez votre propre [clé API Gemini](https://aistudio.google.com/apikey) pour la couche IA (le niveau gratuit couvre largement un usage personnel) — ou vous vous passez complètement de clé et faites tourner un modèle local sur l'appareil.

## Pourquoi c'est conçu comme ça

- **Indépendant des applis, par conception.** La plupart des enregistreurs de réunion ne fonctionnent qu'avec quelques grandes applis parce qu'ils s'intègrent au SDK de chacune. Routine Meeting capture plutôt au niveau de l'audio système — n'importe quelle appli qui fait du son sur votre Mac est prise en compte, peu importe ce que votre équipe, votre client ou votre famille utilise.
- **Local d'abord.** L'enregistrement et la transcription se font sur votre Mac, que vous ajoutiez ou non une clé API. La seule chose qui peut quitter votre machine est une transcription texte, et seulement si vous activez les résumés cloud.
- **Sans compte, sans abonnement.** C'est une appli native, pas un habillage SaaS. Le DMG vous appartient, vos données vous appartiennent.
- **Conçu pour la réalité des réunions.** Les faux départs (musique, un message vocal égaré) ne se transforment pas en enregistrements fantômes ; un micro qui lâche en pleine conversation ne fait pas silencieusement disparaître la moitié de la transcription.

## Ce qui rend Routine Meeting différent

La plupart des assistants de réunion, qu'ils utilisent un bot visible (Fireflies, Otter) ou une capture "sans bot" (Fellow, Fathom), envoient quand même votre enregistrement et votre transcription à leurs serveurs pour traitement. Routine Meeting fait autrement : tout se passe sur votre Mac.

- **Rien ne quitte votre appareil.** L'enregistrement et la transcription s'exécutent entièrement sur l'appareil. C'est vrai même comparé aux outils qui se présentent comme "sans bot", car sans bot signifie simplement qu'aucun participant visible ne rejoint l'appel, pas que vos données restent locales. À moins d'activer explicitement les résumés IA cloud, Routine Meeting n'envoie jamais rien.
- **Fonctionne dans toutes les applis, automatiquement.** Routine Meeting détecte les réunions en écoutant le motif micro + audio système d'une vraie conversation, pas en rejoignant en tant que participant ni en s'accrochant à l'API d'une appli précise. Cela signifie que Google Meet, Zoom, Teams, Webex, les huddles Slack, Discord, FaceTime ou un appel relayé sur votre Mac fonctionnent tous pareil, sans réglage par appli.
- **Utilisez votre propre clé, ou passez du cloud complètement.** Les résumés IA utilisent votre propre clé API Gemini (le niveau gratuit couvre l'usage personnel), ou vous faites tourner un modèle entièrement local, sans clé et sans appel au cloud.
- **Sans compte, sans abonnement.** Routine Meeting est gratuit et ne vous demande de vous inscrire à rien.

### Ce qu'on n'a pas (encore)

Pour être transparent : Routine Meeting est une appli macOS construite par une seule personne, pas une plateforme financée. Quelques éléments que Fireflies, Fellow et des outils similaires proposent et que Routine Meeting n'a pas :

- Recherche inter-réunions ou base de connaissances consultable à long terme (limité pour l'instant à un récapitulatif quotidien)
- Intégrations avec des CRM, Slack, des outils de recrutement ou des numéroteurs
- Certifications de conformité entreprise (SOC 2, HIPAA, GDPR)
- Prise en charge Windows ou mobile

Si vous en avez besoin aujourd'hui, une plateforme comme Fireflies ou Fellow conviendra sans doute mieux, surtout dans les secteurs régulés où ces certifications comptent. Si ce que vous voulez, c'est quelque chose qui ne quitte jamais votre Mac et n'a besoin ni d'un bot ni d'un compte cloud pour fonctionner, c'est exactement le vide que comble Routine Meeting.

## Installation

1. Téléchargez le dernier `RoutineMeeting.dmg` depuis [Releases](https://github.com/mathguimaraes/routine-meeting/releases/latest).
2. Ouvrez le DMG et glissez **Routine Meeting** dans **Applications**.
3. Lancez-le. Un court guide de configuration explique chaque permission — pourquoi elle est nécessaire — puis la demande système (Micro, Enregistrement d'écran, Ouverture à la connexion, Accessibilité, Notifications), et vous laisse ajouter une clé Gemini ou passer en mode local. L'étape Enregistrement d'écran est ce qui capture l'audio des autres participants et déclenche le point violet d'enregistrement ; c'est normal et nécessaire.
4. Relancez ce guide à tout moment depuis l'icône de la barre de menu → **Guide de configuration…**.

Les enregistrements de plus de 7 jours sont supprimés automatiquement une fois transcrits (les transcriptions et résumés sont conservés indéfiniment) — configurable dans Réglages → Stockage, avec un bouton manuel "Libérer de l'espace maintenant".

Routine Meeting vérifie automatiquement les mises à jour (via [Sparkle](https://sparkle-project.org)) et vous prévient dans l'appli quand une nouvelle version est prête.

## Confidentialité

L'audio et les transcriptions restent sur votre Mac. Rien n'est envoyé nulle part sauf si vous activez un fournisseur d'IA cloud — et même là, seul le texte de la transcription sort, jamais l'audio brut.

L'appli envoie aussi un ping anonyme par jour (un identifiant aléatoire, sans contenu de réunion, nom ni email) pour me permettre de voir l'usage approximatif. Activé par défaut ; désactivable à tout moment dans Réglages → Confidentialité, sans que rien d'autre ne change.

## Retours / Problèmes

Icône de la barre de menu → **Envoyer un retour…** dans l'appli, ou ouvrez une [issue](https://github.com/mathguimaraes/routine-meeting/issues) ici.
