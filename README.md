# Site de Redirecionamento

Este repositório consiste de um site estático mínimo no GitHub Pages com a função
de redirecionar acessos para o projeto piloto da Igreja Alianca do Paraiso. Futuramente,
o projeto pode ser ampliado para os sites de outras igrejas da Aliança no Brasil.

## Objetivo

Centralizar o acesso público em um único domínio canônico:

- `https://iacmparaiso.org.br/`

Redirecionamentos esperados:

- `https://iacm.org.br` → `https://iacmparaiso.org.br/`
- `https://iacm.org.br/paraiso` → `https://iacmparaiso.org.br/`

## Como funciona

O projeto utiliza páginas HTML estáticas com redirecionamento por meio de:

- tag `<meta http-equiv="refresh">`
- link canônico com `<link rel="canonical">`
- JavaScript como reforço para navegação automática

Essa abordagem é compatível com hospedagem estática e adequada para
uso no GitHub Pages.

## Estrutura esperada

```text
.
├── index.html
├── paraiso/
│   └── index.html
└── README.md
```

## Comportamento de cada página

### `index.html`

Arquivo responsável por redirecionar o acesso feito à raiz do domínio antigo:

- origem: `https://iacm.org.br`
- destino: `https://iacmparaiso.org.br/`

### `paraiso/index.html`

Arquivo responsável por redirecionar o acesso feito ao caminho legado:

- origem: `https://iacm.org.br/paraiso`
- destino: `https://iacmparaiso.org.br/`

## Observações importantes

### Barra final no destino

Prefira usar a URL canônica com barra final:

- `https://iacmparaiso.org.br/`

Isso evita inconsistências sutis entre a URL informada no redirecionamento e a
URL canônica da página.

### Posição do script

O script pode ficar no `<head>` em um redirecionamento mínimo como este, pois a
intenção é redirecionar o mais cedo possível. Ainda assim, manter o HTML
estruturado e legível continua sendo recomendado.

### Igualdade entre os dois arquivos

Os arquivos `index.html` da raiz e de `/paraiso` podem ser idênticos quando o
destino final é o mesmo. Isso reduz complexidade e facilita manutenção.

## Publicação no GitHub Pages

1. Envie os arquivos para o repositório.
2. Ative o GitHub Pages nas configurações do projeto.
3. Configure o domínio personalizado desejado no repositório correspondente.
4. Ajuste os registros DNS do domínio para apontar ao GitHub Pages.
5. Aguarde a propagação do DNS e a emissão do certificado HTTPS.

## Quando usar esta abordagem

Esta solução é recomendada quando:

- o site antigo não precisa mais de conteúdo próprio
- apenas o redirecionamento permanente é necessário
- a hospedagem será feita de forma simples e estática

## Limitações

Este modelo é intencionalmente minimalista. Ele não substitui:

- regras avançadas de redirecionamento no servidor
- múltiplos destinos condicionais
- lógica dinâmica baseada em rota, idioma ou origem

## Manutenção

Sempre que o domínio de destino mudar, atualize nos arquivos HTML:

- a URL do `meta refresh`
- a URL do `canonical`
- a URL usada no JavaScript
- o link visível no conteúdo da página

## Licença

Salvo definição diferente da igreja, este projeto deve ser tratado como material
institucional da **Igreja Aliança Cristã e Missionária do Paraíso**, com uso e
manutenção controlados pela equipe responsável.
