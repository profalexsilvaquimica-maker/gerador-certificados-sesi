# Gerador de Certificados SESI — versão 1.0

Sistema web Next.js para importar Excel (.xls/.xlsx), carregar um modelo Word (.docx) com marcadores, relacionar campos da planilha e produzir certificados Word individuais ou em lote (.zip).

## Rodar localmente

```bash
npm install
npm run dev
```
Acesse http://localhost:3000.

## Publicar GitHub + Vercel

1. Envie **o conteúdo desta pasta** para um repositório GitHub privado.
2. No Vercel, importe o repositório e mantenha o framework Next.js.
3. Deploy. Não são necessárias chaves de ambiente para a versão atual.

## Marcadores do Word

Edite uma cópia do modelo original em Word e substitua o dado variável por um marcador sem espaços internos, por exemplo:
- `{{NOME_ALUNO}}`
- `{{NOME_MAE}}`
- `{{NOME_PAI}}`
- `{{DATA_NASCIMENTO}}`
- `{{CIDADE_NASCIMENTO}}`
- `{{ANO_CONCLUSAO}}`
- `{{CURSO}}`
- `{{NUMERO_REGISTRO}}`
- `{{LIVRO}}`, `{{FOLHA}}`, `{{DATA_REGISTRO}}`

O site detecta os marcadores e oferece a escolha da coluna correspondente da planilha ou um valor fixo. Para adicionar novos dados, basta escrever outro marcador no Word.

**Limitação:** a primeira linha do Excel deve conter o cabeçalho (ou uma linha posterior contendo coluna 'Nome'). A versão atual usa apenas a primeira aba; novos modelos têm de ser preparados manualmente com marcadores, e não há conversão PDF nativa. Documentos gerados devem ser conferidos antes do uso. Não há autenticação, banco de dados, histórico ou validação de conclusão. Os dados são processados no navegador e não são enviados pelo app ao servidor. Não hospede dados escolares reais em um repositório público.
