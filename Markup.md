# `<focusnetworks />`

Focusnetworks markup code styleguide.

## Table of contents

* [Disclaimer](#disclaimer)
* [Doctype](#doctype)
* [`lang`](#lang)
* [IE compatibility mode](#ie-compatibility-mode)
* [Encoding](#encoding)
* [CSS and JavaScript includes](#css-and-javascript-includes)
* [Naming](#naming)
* [Attribute order](#attribute-order)
* [Boolean attributes](#boolean-attributes)
* [Quotes](#quotes)
* [Self closing tags](#self-closing-tabs)
* [Optional closing tags](#optional-closing-tags)
* [Inline JavaScript](#inline-javascript)
* [Semantics](#semantics)
* [Whitespace](#whitespace)
  * [Tabs](#tabs)
  * [EOF](#eof)
  * [Multiple attributes](#multiple-attributes)
  * [Closing self closing tags](#closing-self-closing-tags)
* [Templates](#templates)
* [`x-template`](#x-template)
* [`id` over `class`](#id-over-class)
* [Links](#links)
  * [Websites](#websites)

## Disclaimer

Esse documento foi inspirado nos guides de [Mark Otto's Code Guide](http://mdo.github.io/code-guide/#html), [Harry Roberts's coding style](http://csswizardry.com/2012/04/my-html-css-coding-style) e [Idiomatic HTML](https://github.com/necolas/idiomatic-html).

**[⬆ voltar ao topo](#table-of-contents)**

## Doctype

* Use HTML5 doctype para assegurar padrões e uma maior consistência em diferentes browsers.

```html
<!doctype html>
<html>
  <head></head>
  <body></body>
</html>
```

**[⬆ voltar ao topo](#table-of-contents)**

## `lang`

* Você deve especificar o idioma dos documentos. Em nossos projetos utilizamos com maior frequência o `pt-br`.

```html
<html lang="pt-br">
</html>
```

**[⬆ voltar ao topo](#table-of-contents)**

## Modo de compatibilidade IE

Utilizamos a tag `<meta>` de compatibilidade para especificar ao IE qual versão do browser deve ser renderizada. Por padrão forçamos o Edge Mode.

```html
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```

**[⬆ voltar ao topo](#table-of-contents)**

## Encoding

* Usamos o `UTF-8` como encoding padrão dos documentos HTML.

```html
<head>
  <meta charset="utf-8">
</head>
```

**[⬆ voltar ao topo](#table-of-contents)**

## CSS e JavaScript includes

* Não há a necessidade de informar o atributo `type`.

```html
<!-- CSS -->
<link rel="stylesheet" href="path/to/external.css">

<!-- JavaScript -->
<script src="path/to/script.js"></script>
```

**[⬆ voltar ao topo](#table-of-contents)**

## Nomenclatura

* Sempre utilizamos lowercase nos nomes de tags e atributos.

```html
<!-- Bad -->
<div id="adversitingModal" class="ModalBase dropShadowFX"></div>

<!-- Good -->
<div id="adversitingModal-modal" class="modal-base drop-shadow-FX"></div>
```

**[⬆ voltar ao topo](#table-of-contents)**

## Ordem dos atributos

* A ordem dos atributos deve seguir essa regra:
	1. Elemento `id` e/ou `name`
	2. Nome da classe JavaScript `js-selector`
	3. Classes genéricas (clearfix, grid stuff, etc)
	4. Outras classes
	5. Estados
	6. Data attributes `data-*`
	7. Outros atributos
	8. Atributos booleanos

```html
<!-- Bad -->
<div class="clearfix is-opaque js-button button grid-size-2" id="btn" hidden data-fx="fade"></div>

<!-- Good -->
<div id="btn" class="js-button clearfix grid-size-2 button is-opaque" data-fx="fade" hidden></div>
```

**[⬆ voltar ao topo](#table-of-contents)**

## Atributos booleanos

* Não adicione valores aos atributos booleanos.

```html
<!-- Bad -->
<input type="checkbox" value="Bar" checked="checked">Foo</input>

<!-- Good -->
<input type="checkbox" value="Bar" checked>Foo</input>

<!-- Bad -->
<input type="submit" disabled="disabled">Send email</input>

<!-- Good -->
<input type="submit" disabled>Send email</input>
```

**[⬆ voltar ao topo](#table-of-contents)**

## Quotes

* Sempre use aspas duplas `"` para envolver os atributos.

```html
<!-- Bad -->
<button id=my-button data-fx='fade'>Fade!</button>

<!-- Good -->
<button id="my-button" data-fx="fade">Fade!</button>
```

**[⬆ voltar ao topo](#table-of-contents)**

## Tags de auto fechamento

* Sempre feche as tags de auto fechamento `/`, não importa quais sejam.

```html
<!-- Bad -->
<p>Lorem ipsum<br>dolor sit</p>

<!-- Good -->
<p>Lorem ipsum<br />dolor sit</p>

<!-- Bad -->
<img src="path/to/image.png">

<!-- Good -->
<img src="path/to/image.png" />
```

**[⬆ voltar ao topo](#table-of-contents)**

## Tags de fechamento opcional

* Sempre feche as tags de fechamento opcional

```html
<!-- Bad -->
<ul>
  <li>Once
  <li>Upon
  <li>A Time
</ul>

<!-- Good -->
<ul>
  <li>Once</li>
  <li>Upon</li>
  <li>A Time</li>
</ul>
```

**[⬆ voltar ao topo](#table-of-contents)**

## Inline JavaScript

* Evite escrever Javascript em documentos HTML, eles são difíceis de detectar.

**[⬆ voltar ao topo](#table-of-contents)**

## Inline CSS

* Evite escrever CSS em documentos HTML, eles são difíceis de detectar.

**[⬆ voltar ao topo](#table-of-contents)**

## Semântica

* Esforce-se para manter os padrões de HTML e semântica, mas não às custas da praticidade. Use a menor quantidade de marcação sempre que possível.

**[⬆ voltar ao topo](#table-of-contents)**

## Espaços em branco

### Tabs

* Use soft tabs definido para 2 espaços e nunca misture espaços com tabs.

### EOF

* Sempre adicione uma linha em branco ao final do seu documento.

### Fechando tags de auto fechamento

* Quando fechar tags de auto fechamento, sempre adicione um espaço antes de `/>`.

```html
<!-- Bad -->
<img src="doge.png"/>

<!-- Good -->
<img src="doge.png" />

```

## Templates

### `x-template`

* Elementos template devem ter o valor de seu `type` definido como `x-template`.

```html
<!-- Bad -->
<script type="text-template" id="box-template">
  <div class="box"></div>
</script>

<!-- Good -->
<script type="x-template" id="box-template">
  <div class="box"></div>
</script>
```

### `id` over `class`

* Elementos template devem ser identificados através de `id` ao invés de` class`. Adicionar o sufixo `template` também.

```html
<!-- Bad -->
<script type="x-template" class="js-component">
  <p>Component</p>
</script>

<!-- Good -->
<script type="x-template" id="component-template">
  <p>Component</p>
</script>
```

**[⬆ voltar ao topo](#table-of-contents)**

## Links

### Websites

* [HTML5 Doctor](http://html5doctor.com)

**[⬅ voltar à página inicial](../../)**&nbsp;&nbsp;&nbsp;&nbsp;**[⬆ voltar ao topo](#table-of-contents)**