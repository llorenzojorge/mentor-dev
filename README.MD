# Mentor Dev

Uma skill para o Claude que transforma a IA num **mentor técnico de verdade**: alguém que puxa, cobra e desafia, em vez de um assistente que entrega tudo mastigado.

Feita para quem quer **aprender a desenvolver projetos com IA** ou **estudar para entrevistas técnicas** (estrutura de dados, algoritmos, system design), não para quem quer que a IA faça o trabalho por ele.

## O problema

Quando você estuda com uma IA, o caminho mais fácil é pedir a resposta e copiar. O código funciona, o projeto avança… e você não aprendeu quase nada. Na hora de uma entrevista ou de um problema novo, o gap aparece.

## O que a skill faz

Com a skill ativa, o Claude assume o papel de professor durante toda a conversa:

- **Não entrega a resposta pronta.** Ele faz perguntas que guiam você até a solução e, se você travar, quebra o problema em partes menores.
- **Ajusta o desafio ao seu nível.** Se você já tem base, ele mantém a pressão. Se o assunto é totalmente novo, ele dá o mínimo de contexto (o nome do conceito, uma analogia ou um exemplo em outro cenário) e devolve o problema para você.
- **Cobra justificativa.** Toda decisão técnica precisa de um porquê. Sem justificativa, não foi uma decisão: foi um chute.
- **Não aceita resposta vaga.** "Fazer da melhor forma" não é resposta. O que, como e por quê?
- **Bloqueia a fuga para a zona de conforto.** Se você tem um gap num fundamento, ele não deixa você pular para algo mais fácil.
- **Aponta quando você resolve no lugar errado.** Ele leva você a atacar a raiz do problema, não o sintoma.
- **Cobra consistência.** Ele avisa quando você contradiz uma decisão anterior ou repete o mesmo erro.
- **Pensa antes de codar.** Design primeiro, código depois.
- **Dá nome às hard skills.** Quando você aplica uma competência que o mercado procura (modelagem de dados, design de APIs, testes automatizados…), ele diz isso explicitamente. Assim você aprende o vocabulário que aparece em vagas e entrevistas.
- **Reconhece progresso real**, sem elogiar resposta medíocre só para ser simpático.

## Exemplo

> **Aluno:** Como eu faço o cadastro de usuário salvar no banco?
>
> **Mentor:** Antes de falar de banco: quais dados um usuário tem no seu sistema, e quais deles são obrigatórios? Me descreve a estrutura que você imagina.
>
> **Aluno:** Nome, e-mail e senha. Vou salvar tudo numa tabela.
>
> **Mentor:** E a senha vai ser salva como o usuário digitou? O que acontece se alguém tiver acesso a essa tabela?

## Modo estudo

Além de projetos, a skill tem um **modo estudo**, para quem segue um plano de estudos ou se prepara para entrevistas. A postura continua a mesma; o que muda é o método:

- **Três modos com regras diferentes:**
  - **Diagnóstico:** o Claude só pergunta e avalia (nível 0 a 3 por tema), sem ensinar no meio, para o resultado ser honesto.
  - **Aula:** a postura de mentor aplicada a um conceito ou exercício, com **abordagem antes de código**: problema, exemplos, solução ingênua, solução melhor e Big O, só então o código.
  - **Simulado:** o Claude vira entrevistador, com tempo de 30 a 40 minutos, pouca ajuda e nota no final.
- **Recuperação ativa:** toda sessão começa com perguntas rápidas sobre o que foi estudado antes.
- **Saída quando você trava:** dicas em escada; depois de 3 dicas sem avanço, ou se você pedir, ele mostra a solução, cobra que você explique de volta e agenda o exercício para você refazer em 2 dias (repetição espaçada).
- **Técnicas de aprendizado:** técnica Feynman, prática deliberada nos temas fracos e problemas misturados nas revisões (interleaving).
- **Memória entre sessões:** o Claude lê e atualiza um arquivo de progresso do projeto (por exemplo `progresso.md`) com nível por tema, simulados e erros que se repetem.
- **Fechamento:** resumo da sessão e, se você usar Anki, flashcards prontos para importar.

### Exemplo no modo estudo

> **Aluno:** Vamos fazer o "Two Sum".
>
> **Mentor:** Antes do código: me dá um exemplo de entrada e saída, e qual a solução mais simples que você consegue pensar, mesmo lenta.
>
> **Aluno:** Dois laços, testando todos os pares.
>
> **Mentor:** Certo. Qual a complexidade disso? E o que você precisaria guardar para olhar cada número uma vez só?

## Para quem é

- Quem está estudando programação e usa IA como apoio
- Quem quer sair do "funciona, mas não sei por quê"
- Quem se prepara para entrevistas técnicas e quer dominar os termos do mercado

Funciona com qualquer stack ou linguagem.

**Não é para** quem quer entregar um projeto real com rapidez. A skill sempre prioriza o seu aprendizado em vez da velocidade.

## Instalação

### Claude Code (recomendado: como plugin, com atualizações)

Este repositório é um **marketplace de plugins** do Claude Code. Dentro de uma sessão do Claude Code (terminal ou VS Code), rode:

```
/plugin marketplace add llorenzojorge/mentor-dev
/plugin install mentor-dev@llorenzojorge-skills
```

O Claude carrega a skill automaticamente quando o contexto pedir. Para chamar diretamente: `/mentor-dev:mentor-dev`.

Para usar só em um projeto e deixar registrado para quem abrir o projeto, rode no terminal, dentro da pasta do projeto, e faça commit do `.claude/settings.json` gerado:

```bash
claude plugin marketplace add llorenzojorge/mentor-dev --scope project
```

### Atualizações

Por padrão, o Claude Code **não** atualiza marketplaces de terceiros sozinho. Você escolhe:

- **Automático:** em `/plugin`, vá em **Marketplaces**, selecione `llorenzojorge-skills` e escolha **Enable auto-update**. Depois disso, as versões novas chegam sozinhas quando uma sessão começa.
- **Manual:** rode `/plugin marketplace update llorenzojorge-skills` quando quiser a versão mais recente.

O plugin não fixa número de versão: cada commit na `main` é uma versão nova.

### Claude.ai (app e web)

1. Baixe a pasta `plugins/mentor-dev/skills/mentor-dev` (ou o repositório inteiro) e compacte a pasta da skill como `.zip`.
2. Em **Configurações → Personalização → Skills**, faça o upload do arquivo.
3. Ative a skill e comece uma conversa sobre o que você quer estudar.

No claude.ai a skill não se atualiza sozinha: para pegar uma versão nova, faça o upload de novo.

## Estrutura

```
mentor-dev/
├── .claude-plugin/
│   └── marketplace.json          # Catálogo do marketplace (lista os plugins)
├── plugins/
│   └── mentor-dev/
│       ├── .claude-plugin/
│       │   └── plugin.json       # Manifesto do plugin
│       └── skills/
│           └── mentor-dev/
│               └── SKILL.md      # As instruções do mentor (inclui o modo estudo)
├── LICENSE
└── README.md
```

## Como contribuir

Contribuições são bem-vindas! Algumas ideias:

- Novas regras de mentoria que você testou e funcionaram
- Exemplos de interação para diferentes stacks
- Traduções para outros idiomas
- Relatos de casos em que a skill não se comportou como esperado

Abra uma issue para discutir a ideia ou envie um pull request.
