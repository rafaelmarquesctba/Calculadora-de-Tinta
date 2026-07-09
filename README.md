# Calculadora de Custo-Benefício de Tintas — Tintas Renner

App web estático (HTML + JS puro, sem dependências de build) para comparar produtos de tinta pelo custo real por m² e pelo custo anualizado (considerando rendimento e durabilidade estimada de cada produto).

## Como usar localmente

Basta abrir o arquivo `index.html` em qualquer navegador — não precisa de servidor, build ou instalação.

## Publicar no GitHub Pages

1. Crie um repositório novo no GitHub e suba este arquivo `index.html` na raiz (branch `main`).
2. Vá em **Settings → Pages**.
3. Em **Source**, selecione a branch `main` e a pasta `/ (root)`.
4. Salve. Em alguns minutos o app estará disponível em:
   `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`

## Atualizar o catálogo de produtos

O catálogo fica em uma constante `catalog` dentro da tag `<script>`, no início do arquivo. Cada produto segue este formato:

```js
{
  "produto": "Nome do produto",
  "durabilidade": 5,        // em anos, ou null se não aplicável
  "embalagens": [
    { "label": "3,2 L", "rendimento": 25, "rendimentoTexto": "Até 25 m²" }
  ]
}
```

- `rendimento`: número em m² usado no cálculo. Use `null` quando o rendimento não for um valor fixo (ex: "conforme superfície") — nesse caso o produto aparece na lista mas fica fora do ranking de custo-benefício.
- `durabilidade`: número em anos. Use `null` quando a planilha não tiver essa informação — o app mostra "não aplicável" e não calcula o custo por m²/ano para esse produto.

Depois de editar, é só salvar e subir (`git commit` + `git push`) — o GitHub Pages atualiza automaticamente.

## Estrutura

- `index.html` — app completo (HTML, CSS e JS em um único arquivo).# Calculadora-de-Tinta
