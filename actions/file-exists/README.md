# Arquivo Existe :package:

Uma GitHub Action que verifica se um arquivo existe no repositório.

Esta action falhará se o arquivo não existir

## Entradas ⚙️

| Nome   | Descrição                                                      | Obrigatório |
| ------ | -------------------------------------------------------------- | ----------- |
| `file` | O caminho para o arquivo a verificar, relativo à raiz do repositório | Sim         |

## Uso 🚀

```yaml
steps:
  - uses: actions/checkout@v4
  - name: Verificar se o arquivo existe
    uses: skills/exercise-toolkit/actions/file-exists@<git-tag>
    with:
      file: "path/to/your/file.md"
```
