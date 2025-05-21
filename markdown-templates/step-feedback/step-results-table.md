{{#passed}}

## Etapa {{ step_number }} - Aprovado ✅

{{/passed}}
{{^passed}}

## Etapa {{ step_number }} - Falha ❌

{{/passed}}

{{#passed}}
<img src="https://octodex.github.com/images/inflatocat.png" align="right" height="150px" alt="Imagem Inflatocat indicando que a etapa foi aprovada" />
{{/passed}}
{{^passed}}
<img src="https://octodex.github.com/images/spidertocat.png" align="right" height="100px" alt="Imagem Spidertocat indicando que a etapa falhou" />
Algumas verificações falharam. Por favor, revise os resultados abaixo e tente novamente.

Hora de encontrar o bug! 🤔
{{/passed}}

| Status | Descrição |
| --- | --- |
{{#results_table}}
| {{#passed}}✅ - Aprovado{{/passed}}{{^passed}}❌ - Falha{{/passed}} | {{ description }} |
{{/results_table}}

{{#tips.length}}

### Dicas

{{#tips}}

- {{.}}
  {{/tips}}
  {{/tips.length}}
