# Kit de Ferramentas para Exercícios de Habilidades :hammer_and_wrench:

<p align="center">
  <img src="https://octodex.github.com/images/manufacturetocat.png" alt="Manufacturetocat" width="300" />
</p>

## Objetivo

Este repositório serve como um kit de ferramentas abrangente para criar e gerenciar exercícios do GitHub Skills. Ele fornece uma coleção de ferramentas, modelos e utilitários projetados para simplificar o processo de desenvolvimento de conteúdo educacional para o GitHub Skills.

### Conteúdo

- **[.github/workflows](/.github/workflows)**: Fluxos de trabalho do GitHub Actions para automatizar partes comuns dos Exercícios de Skills
- **[markdown-templates](/markdown-templates)**: Modelos de Markdown prontos para uso na criação de documentação, instruções e arquivos README consistentes para exercícios

## Exemplos

### ⚙️ Fluxos de Trabalho Reutilizáveis

Para uma lista completa de fluxos de trabalho reutilizáveis, acesse o diretório **[.github/workflows](/.github/workflows)**.

#### Iniciando um exercício

```yaml
jobs:
  start_exercise:
    name: Start Exercise
    uses: skills/exercise-toolkit/.github/workflows/start-exercise.yml@<git-tag>
    with:
      exercise-title: "Introdução ao GitHub Copilot"
      intro-message: "Vamos começar com o GitHub Copilot :robot:! Aprenderemos ..."

```

#### Localizando um exercício

```yaml

jobs:
  find_exercise:
    name: Find Exercise Issue
    uses: skills/exercise-toolkit/.github/workflows/find-exercise-issue.yml@<git-tag>

```


### 📋 Modelos de Markdown

Para uma lista completa de modelos de markdown, acesse o diretório **[markdown-templates](/markdown-templates)**.

```yaml
steps:
  - name: Get markdown templates
    uses: actions/checkout@v4
    with:
      repository: skills/exercise-toolkit
      path: exercise-toolkit
      ref: <git-tag>

  - name: Use the template
    run: |
      cat exercise-toolkit/markdown-templates/step-feedback/checking-work.md

```

Modelos de markdown são frequentemente usados em conjunto com a Action [skills/action-text-variables](https://github.com/skills/action-text-variables) do GitHub

```yaml
steps:
  - name: Get markdown templates
    uses: actions/checkout@v4
    with:
      repository: skills/exercise-toolkit
      path: exercise-toolkit
      ref: <git-tag>

  - name: Build message - congratulations
    id: build-message-congratulations
    uses: skills/action-text-variables@v2
    with:
      template-file: exercise-toolkit/markdown-templates/readme/congratulations.md
      template-vars: |
        login: ${{ github.actor }}

  - name: Echo updated text
    run: echo "$UPDATED_TEXT"
    env:
      UPDATED_TEXT: ${{ steps.build-message-congratulations.outputs.updated-text }}

```
