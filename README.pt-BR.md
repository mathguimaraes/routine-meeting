<div align="center">

<img src="icon.png" width="128" height="128" alt="Routine Meeting icon">

# Routine Meeting

**Reuniões acontecem. Anotar não deveria ser trabalho seu.**

[Baixar para macOS](https://github.com/mathguimaraes/routine-meeting/releases/latest) · Apple Silicon · macOS 13+

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

## O problema

Você entra numa call e, no momento em que fica interessante, precisa escolher: prestar atenção ou anotar. Perde o começo da reunião procurando um app de notas. Esquece de apertar gravar. Chega na sexta com seis reuniões de decisões e tarefas que só existem na sua memória.

A maioria das ferramentas de gravação piora isso, não melhora — você precisa lembrar de apertar o botão, elas mandam o áudio bruto para algum servidor, e boa parte nem consegue diferenciar sua voz da dos outros.

## O que o Routine Meeting faz

O Routine Meeting fica discretamente na sua barra de menu e cuida de tudo sem você pedir:

- **Percebe que você está numa reunião e começa a gravar sozinho — em *qualquer* app.** Não é uma integração com Zoom/Meet/Teams limitada a uma lista fixa de apps suportados; ele escuta o padrão de microfone + áudio do sistema de uma conversa de verdade. Funciona do mesmo jeito no Google Meet, Zoom, Microsoft Teams, Webex, Slack huddles, Discord, FaceTime, chamadas de WhatsApp, ou uma ligação de telefone redirecionada pro seu Mac — qualquer coisa com áudio nos dois sentidos, sem configurar nada por app. Sem botão pra lembrar, sem aquele momento "nossa, isso estava sendo gravado?".
- **Transcreve tudo no seu Mac.** O [WhisperKit](https://github.com/argmaxinc/WhisperKit) roda no Neural Engine do Apple Silicon — o áudio nunca sai da sua máquina.
- **Sabe o que você falou e o que os outros falaram.** Microfone e áudio do sistema são capturados e separados, então resumos e insights são atribuídos à pessoa certa.
- **Transforma a transcrição em algo útil** — um título, um resumo em tópicos, itens de ação e, opcionalmente, uma leitura honesta de como você se saiu naquela conversa específica, seja um 1:1, uma call com cliente ou uma revisão de design.
- **Junta tudo num relatório diário** — o que aconteceu hoje, em todas as reuniões, e o que você ainda deve pra alguém.

Você usa sua própria [chave de API do Gemini](https://aistudio.google.com/apikey) pra camada de IA (o nível gratuito cobre tranquilamente o uso pessoal) — ou pula a chave completamente e roda um modelo local no dispositivo.

## Por que foi feito assim

- **Independente de app, por design.** A maioria dos gravadores de reunião só funciona com um ou dois apps grandes porque integra contra o SDK de cada um. O Routine Meeting captura no nível de áudio do sistema — qualquer app que faça som no seu Mac vale, então não importa o que seu time, seu cliente ou sua família usa.
- **Local em primeiro lugar.** Gravação e transcrição acontecem no seu Mac independentemente de você adicionar uma chave de API. A única coisa que pode sair da sua máquina é uma transcrição em texto, e só se você ligar os resumos na nuvem.
- **Sem contas, sem assinatura.** É um app nativo, não um SaaS disfarçado. O DMG é seu, seus dados são seus.
- **Feito pra como reuniões realmente acontecem.** Falsos positivos (música, uma mensagem de voz perdida) não viram gravações fantasma; um microfone que cai no meio da call não perde silenciosamente metade da transcrição.

## No que o Routine Meeting é diferente

A maioria dos assistentes de reunião, seja com bot visível (Fireflies, Otter) ou captura "sem bot" (Fellow, Fathom), ainda manda sua gravação e transcrição pros servidores deles pra processar. O Routine Meeting faz diferente: tudo acontece no seu Mac.

- **Nada sai do seu dispositivo.** Gravação e transcrição rodam inteiramente no dispositivo. Isso vale até comparado com ferramentas que se vendem como "sem bot", já que "sem bot" só significa que nenhum participante visível entra na call, não que seus dados ficam locais. A menos que você ative explicitamente os resumos de IA na nuvem, o Routine Meeting nunca envia nada.
- **Funciona em qualquer app, automaticamente.** O Routine Meeting detecta reuniões escutando o padrão de microfone + áudio do sistema de uma conversa real, não entrando como participante ou se conectando à API de um app específico. Isso significa que Google Meet, Zoom, Teams, Webex, Slack huddles, Discord, FaceTime, ou uma ligação redirecionada pro seu Mac funcionam todos do mesmo jeito, sem configurar nada por app.
- **Use sua própria chave, ou pule a nuvem completamente.** Os resumos de IA usam sua própria chave de API do Gemini (o nível gratuito cobre o uso pessoal), ou você roda um modelo totalmente local, sem chave e sem chamadas pra nuvem.
- **Sem conta, sem assinatura.** O Routine Meeting é gratuito e não pede pra você se cadastrar em nada.

### O que a gente ainda não tem

Pra ser transparente: o Routine Meeting é um app de macOS feito por uma pessoa só, não uma plataforma financiada. Algumas coisas que Fireflies, Fellow e ferramentas parecidas oferecem e o Routine Meeting não:

- Busca entre reuniões ou uma base de conhecimento pesquisável de longo prazo (por enquanto, limitado a um resumo diário)
- Integrações com CRMs, Slack, ferramentas de recrutamento ou discadores
- Certificações de compliance empresarial (SOC 2, HIPAA, GDPR)
- Suporte a Windows ou mobile

Se você precisa de algo disso hoje, uma plataforma como Fireflies ou Fellow provavelmente encaixa melhor, especialmente em setores regulados onde essas certificações importam. Se o que você quer é algo que nunca sai do seu Mac e não precisa de um bot (nem de uma conta na nuvem) pra funcionar, é exatamente essa lacuna que o Routine Meeting preenche.

## Instalação

1. Baixe o `RoutineMeeting.dmg` mais recente em [Releases](https://github.com/mathguimaraes/routine-meeting/releases/latest).
2. Abra o DMG e arraste o **Routine Meeting** pra pasta **Aplicativos**.
3. Abra o app. Um guia rápido explica cada permissão — por que ela é necessária, depois o prompt do sistema (Microfone, Gravação de Tela, Abrir no Login, Acessibilidade, Notificações) — e deixa você adicionar uma chave do Gemini ou pular pro modo local. O passo de Gravação de Tela é o que captura o áudio dos outros participantes e ativa o pontinho roxo de gravação; isso é esperado e necessário.
4. Rode esse guia de novo quando quiser, pelo ícone da barra de menu → **Guia de Configuração…**.

Gravações com mais de 7 dias são apagadas automaticamente depois de transcritas (transcrições e resumos ficam guardados pra sempre) — configurável em Ajustes → Armazenamento, com um botão manual de "Liberar Espaço Agora".

O Routine Meeting verifica atualizações automaticamente (via [Sparkle](https://sparkle-project.org)) e avisa dentro do app quando uma versão nova estiver pronta.

## Privacidade

Áudio e transcrições ficam no seu Mac. Nada é enviado pra lugar nenhum a menos que você ative um provedor de IA na nuvem — e mesmo assim, só o texto da transcrição sai, nunca o áudio bruto.

O app também manda um ping anônimo por dia (um ID aleatório, sem conteúdo de reunião, nome ou email) pra que eu consiga ver o uso de forma aproximada. Vem ativado por padrão; você pode desligar quando quiser em Ajustes → Privacidade, sem mudar mais nada.

## Feedback / Problemas

Ícone da barra de menu → **Enviar Feedback…** no app, ou abra uma [issue](https://github.com/mathguimaraes/routine-meeting/issues) aqui.
