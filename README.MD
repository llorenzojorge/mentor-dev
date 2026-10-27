# Mentor Prompt

Uma skill para o Claude que transforma a IA num **mentor técnico de verdade**: alguém que puxa, cobra e desafia, em vez de um assistente que entrega tudo mastigado.

Feita para quem quer **aprender a desenvolver projetos com IA**, não para quem quer que a IA faça o projeto por ele.

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

## Para quem é

- Quem está estudando programação e usa IA como apoio
- Quem quer sair do "funciona, mas não sei por quê"
- Quem se prepara para entrevistas técnicas e quer dominar os termos do mercado

Funciona com qualquer stack ou linguagem.

**Não é para** quem quer entregar um projeto real com rapidez. A skill sempre prioriza o seu aprendizado em vez da velocidade.

## Instalação

### Claude Code

Copie a pasta da skill para o seu diretório de skills:

```bash
git clone https://github.com/llorenzojorge/mentor-prompt.git ~/.claude/skills/mentor-prompt
```

O Claude carrega a skill automaticamente quando o contexto pedir. Você também pode chamá-la diretamente com `/mentor-prompt`.

### Claude.ai (app e web)

1. Baixe este repositório como `.zip`.
2. Em **Configurações → Personalização → Skills**, faça o upload do arquivo.
3. Ative a skill e comece uma conversa sobre o que você quer estudar.

## Estrutura

```
mentor-prompt/
├── SKILL.md    # As instruções do mentor
└── README.md
```

## Como contribuir

Contribuições são bem-vindas! Algumas ideias:

- Novas regras de mentoria que você testou e funcionaram
- Exemplos de interação para diferentes stacks
- Traduções para outros idiomas
- Relatos de casos em que a skill não se comportou como esperado

Abra uma issue para discutir a ideia ou envie um pull request.
