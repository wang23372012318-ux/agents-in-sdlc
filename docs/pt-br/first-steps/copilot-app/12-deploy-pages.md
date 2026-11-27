---
title: "Lição 12 - Publique o site com o GitHub Pages"
description: "Use o aplicativo GitHub Copilot para configurar um fluxo de trabalho do Pages, revisar a solicitação de pull e confirmar que o Space Quiz está no ar."
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

Publique o Space Quiz no GitHub Pages para que qualquer pessoa possa acessá-lo. O Copilot pode preparar o fluxo de trabalho e orientar a implantação, mas você continua responsável por revisar as alterações e confirmar que o site está no ar.

Nesta lição, você vai:

- Pedir ao Copilot que configure uma implantação no GitHub Pages.
- Revisar o fluxo de trabalho e a solicitação de pull antes de fazer o merge.
- Acompanhar a implantação e verificar o site publicado.

## Cenário

O Space Quiz já está em um repositório do GitHub, mas as pessoas ainda precisam de uma forma simples de experimentá-lo. Publicar o site de arquivo único com o GitHub Pages permite acessá-lo por uma URL pública sem adicionar um servidor ou uma dependência de runtime.

## Peça ao Copilot para preparar a implantação

> [!WARNING]
> Criar uma solicitação de pull pode fazer commit e push de código. Revise as configurações de aprovação e o repositório de destino antes de enviar este prompt. Com **Approve all**, não espere uma solicitação de confirmação separada.

Na sessão do aplicativo Copilot para `space-quiz`, envie este prompt:

```plaintext
Prepare uma implantação do GitHub Pages para este repositório. Crie um fluxo de trabalho do GitHub Actions que, se necessário, compile o site e o implante no GitHub Pages depois que as alterações chegarem à ramificação padrão. Adicione um README que descreva o aplicativo e como executá-lo localmente, caso ainda não exista. Crie uma solicitação de pull com essas alterações e informe o link e quaisquer configurações ou permissões do Pages necessárias. Não faça merge, não habilite o merge automático, não altere as configurações do Pages e não implante o site. Pare e aguarde minha revisão.
```

## Revise o fluxo de trabalho e a solicitação de pull

1. Confirme que o README só foi adicionado se o repositório ainda não tinha um.
2. Revise as alterações da solicitação de pull, incluindo as etapas de compilação e implantação do fluxo de trabalho, os gatilhos e as permissões.
3. Confirme que o fluxo de trabalho implanta a partir da ramificação padrão, e não de uma solicitação de pull ainda não integrada.
4. Peça as correções necessárias e revise o diff atualizado. Aguarde a aprovação nas verificações obrigatórias da solicitação de pull antes de autorizar o merge.

## Autorize o merge e a implantação

> [!WARNING]
> O prompt a seguir autoriza o agente a fazer merge da solicitação revisada, alterar as configurações do Pages no repositório e publicar o site. Envie-o somente depois de concluir a revisão e confirmar o repositório e a solicitação de pull. Dependendo das configurações de aprovação, essas ações podem ocorrer sem outra solicitação de confirmação.

Substitua `<PR_NUMBER>` pelo número da solicitação de pull revisada e envie este prompt separadamente:

```plaintext
Revisei a solicitação de pull <PR_NUMBER> neste repositório e autorizo o merge e a implantação. Habilite o GitHub Pages usando o GitHub Actions, faça merge dessa solicitação somente depois que as verificações obrigatórias forem aprovadas e acompanhe a implantação até que ela seja concluída com sucesso. Informe a URL final do site publicado. Se você não tiver permissão para habilitar o Pages ou fazer merge, diga exatamente o que preciso aprovar ou fazer; não informe que a implantação foi concluída antes de o site estar no ar.
```

![Diagrama em três etapas: uma solicitação de pull do space-quiz integrada; uma execução bem-sucedida do GitHub Actions Deploy website com as etapas Build website, Upload artifact e Deploy to Pages; e o Space Quiz publicado em yourname.github.io/space-quiz/.](../../../_images/first-steps-app-pages-deploy.svg)

## Verifique a implantação

1. Acompanhe a execução de implantação do GitHub Actions até que ela seja concluída com sucesso.
2. Abra a URL informada e confirme que o Space Quiz é carregado.

Se o agente não puder habilitar o Pages ou fazer merge da solicitação de pull, siga as instruções específicas fornecidas. Não considere a tarefa concluída até que a implantação seja bem-sucedida e o site esteja no ar.

## Resumo e próximas etapas

O Space Quiz agora está disponível como um site, e você verificou a implantação em vez de confiar apenas no relato do agente. Continue para a [Lição 13: Revisão e próximas etapas][next-lesson].

[next-lesson]: ../13-review/
