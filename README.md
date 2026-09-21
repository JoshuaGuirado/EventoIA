# EventoIA

Landing page de inscrição do Encontro Empresarial **“O que a IA não pode fazer por você”**.

Página única e estática (`index.html`), sem dependências ou build — basta abrir o
arquivo ou publicá-lo em qualquer host estático.

## Fluxo

1. **Passo 01 — Inscrição.** O formulário do ClickUp fica embedado na própria
   página (`<iframe>`), para não tirar a pessoa do site. Há também um link
   discreto para abrir em outra aba, como alternativa.
2. **Passo 02 — Testes.** Fica bloqueado (esmaecido, links inativos) até a
   inscrição. É liberado pelo botão *"Enviei minha inscrição"*, logo abaixo do
   formulário. O estado fica salvo em `localStorage`, então quem volta à página
   continua com os testes liberados.

A página também escuta `postMessage` vindo de `clickup.com`: se o ClickUp
sinalizar o envio, os testes liberam sozinhos, sem precisar do botão. Como esse
sinal não é documentado, o botão continua sendo o caminho garantido.

## Links usados

| Item | Destino |
| --- | --- |
| Inscrição | `forms.clickup.com/9005194772/f/8cc0qgm-33952/SS56CJWUL5GN8YLXW9` |
| Teste 01 — Positividade e Bem-Estar | `login.etzme.com.br/generic_link/index/257c806b2894dcfbee9b0861637567f6` |
| Teste 02 — Âncoras de Carreira | `login.etzme.com.br/generic_link/index/2d98db28d83337bd77ab7aa724d35fcc` |

Para trocar qualquer link, edite o `href` correspondente em `index.html`.

## Identidade visual

Mesma paleta e tipografia de [construcaoiagestao.com.br](https://construcaoiagestao.com.br):

- `--ink` `#0A0A0A` · `--accent` `#F5A623` · `--paper` `#FFFFFF`
- `--surface` `#1A1A1A` · `--support` `#6B6B6B` · `--line` `#232323`
- Tipografia Manrope (400 / 600 / 800), cantos retos, letter-spacing negativo nos títulos.
- Fundo da catedral (`media/catedral.jpg`) no topo, com o mesmo tratamento do site
  original: imagem a 42% de opacidade sob um véu em gradiente que funde no preto.
  Para deixá-lo mais ou menos visível, ajuste `opacity` em `.hero-bg img`.

## Rodar localmente

```
npx -y serve -l 4173 .
```

O `.claude/launch.json` já traz essa configuração pronta.
