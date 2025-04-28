# Modelos de Markdown para Exercícios de Skills

Uma coleção de modelos para uso em exercícios de Skills.

## Coleções de Modelos

- `/readme/*` - modelos destinados a atualizar o arquivo readme principal de um exercício.
- `/step-feedback/*` - modelos para compartilhar progresso de etapas, aprovar/reprovar e parabenizar. Normalmente usados para comentários em issues.

## Variáveis de Modelos

Vários modelos contêm [variáveis no estilo mustache](https://mustache.github.io/mustache.5.html). Eles são destinados a serem usados com a Action [skills/action-text-variables](https://github.com/skills/action-text-variables) do GitHub, que suporta modelagem completa com mustache.

### Exemplo

#### hello.md

```markdown
Olá {{ login }}, prazer em conhecê-lo!
```

#### entrada json

```json
{
  "login": "${{ github.actor }}"
}
```

> [!DICA]
> Veja a [sintaxe mustache](https://mustache.github.io/mustache.5.html) para todas as capacidades, como iteração e lógica if/then.
