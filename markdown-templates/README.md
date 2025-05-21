# Templates Markdown para Exercícios Skills

Uma coleção de templates para uso em exercícios Skills.

## Coleções de Templates

- `/readme/*` - templates destinados à atualização do arquivo readme principal de um exercício.
- `/step-feedback/*` - templates para compartilhar o progresso das etapas, aprovação/reprovação e congratulações. Normalmente usados para comentários em issues.

## Variáveis de Template

Vários templates contêm [variáveis no estilo mustache](https://mustache.github.io/mustache.5.html). Eles são destinados ao uso com a GitHub Action [skills/action-text-variables](https://github.com/skills/action-text-variables), que oferece suporte completo a templates mustache.

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
> Veja a [sintaxe mustache](https://mustache.github.io/mustache.5.html) para todas as capacidades como iteração e lógica if/then.
