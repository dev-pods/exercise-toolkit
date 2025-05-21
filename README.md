# Kit de Ferramentas para Exercícios Skills :hammer_and_wrench:

<p align="center">
  <img src="https://octodex.github.com/images/manufacturetocat.png" alt="Manufacturetocat" width="300" />
</p>

- [Kit de Ferramentas para Exercícios Skills :hammer\_and\_wrench:](#kit-de-ferramentas-para-exercícios-skills-hammer_and_wrench)
  - [Propósito](#propósito)
    - [Conteúdos](#conteúdos)
  - [Exemplos](#exemplos)
    - [⚙️ Workflows Reutilizáveis](#️-workflows-reutilizáveis)
      - [Iniciando um exercício](#iniciando-um-exercício)
      - [Localizando um exercício](#localizando-um-exercício)
    - [📋 Templates Markdown](#-templates-markdown)
  - [Recursos Notáveis](#recursos-notáveis)

## Propósito

Este repositório serve como um kit de ferramentas abrangente para criar e gerenciar exercícios do GitHub Skills. Ele fornece uma coleção de ferramentas, modelos e utilitários projetados para simplificar o processo de desenvolvimento de conteúdo educacional para o GitHub Skills.

### Conteúdos

- **[.github/workflows](/.github/workflows)**: Workflows do GitHub Actions para automatizar partes comuns dos exercícios Skills
- **[markdown-templates](/markdown-templates)**: Templates Markdown prontos para uso na criação de documentação consistente de exercícios, instruções e arquivos README
- **[actions](/actions)**: Actions compostas simples para ajudar na construção de exercícios do GitHub Skills


## Exemplos

### ⚙️ Workflows Reutilizáveis

Para uma lista completa de workflows reutilizáveis, acesse o diretório **[.github/workflows](/.github/workflows)**.

#### Iniciando um exercício

```yaml
jobs:
  start_exercise:
    name: Start Exercise
    uses: skills/exercise-toolkit/.github/workflows/start-exercise.yml@<git-tag>
    with:
      exercise-title: "Introdução ao GitHub Copilot"
      intro-message: "Vamos começar com o GitHub Copilot :robot: ! Vamos aprender ..."
```

#### Localizando um exercício

```yaml
jobs:
  find_exercise:
    name: Find Exercise Issue
    uses: skills/exercise-toolkit/.github/workflows/find-exercise-issue.yml@<git-tag>
```

### 📋 Templates Markdown

Para uma lista completa de templates markdown, acesse o diretório **[markdown-templates](/markdown-templates)**.

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

Templates Markdown são frequentemente usados em conjunto com a GitHub Action [skills/action-text-variables](https://github.com/skills/action-text-variables)

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

## Recursos Notáveis

Estas GitHub Actions são particularmente úteis ao criar Exercícios GitHub Skills:

- **[skills/action-text-variables](https://github.com/skills/action-text-variables)**: Substitui variáveis em arquivos de template com conteúdo dinâmico
- **[skills/action-keyphrase-checker](https://github.com/skills/action-keyphrase-checker)**: Verifica se frases-chave específicas existem em arquivos ou conteúdo

