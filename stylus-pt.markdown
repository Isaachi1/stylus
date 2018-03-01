---
language: stylus
filename: learnStylus-pt.styl
contributors:
  - ["Salomão Neto", "https://github.com/salomaosnff"]
  - ["Isaac Henrique", "https://github.com/Isaachi1"]
lang: pt-br
---

Stylus tem como propósito, adicionar funcionalidades às suas folhas de estilos CSS que te ajudam no desenvolvimento, sem que haja a quebra de compartibilidade entre os navegadores Web.
Entre elas estão variáveis, aninhamento, mixins, funções e muito mais.

A sintaxe do Stylus é muito flexivel podendo utilizar a sintaxe padrão do CSS e deixando opcional o ponto e vírgula (;), dois pontos (:) e até mesmo as chaves ({ e }), tornando assim o seu código ainda mais legível.

Stylus não fornece novas opções de estilos, mas dá funcionalidades que permitem deixar seu CSS muito mais dinâmico.


```stylus

// Comentários de linha única são removidos quando Stylus é compilado para CSS.

/* Comentários multi-line são preservados. */





/*Variáveis
==============================*/


/* 
  É possível armazenar um valor CSS (tais como a cor) de uma variável.
  Embora seja opcional, é recomendado adicionar $ antes de um nome de variável 
  para que você possa diferenciar uma variável de outro valor CSS.
*/

$primary-color = #A3A4FF
$secondary-color = #51527F
$body-font = 'Roboto', sans-serif

/* Você pode usar as variáveis em toda a sua folha de estilo.
Agora, se você quer mudar a cor, você só tem que fazer a mudança uma vez. */

body
	background-color $primary-color
	color $secondary-color
	font-family $body-font

/* Quando compilar ficaria assim: */
body {
	background-color: #A3A4FF;
	color: #51527F;
	font-family: 'Roboto', sans-serif;
}

/ * 
Este é muito mais fácil de manter do que ter de mudar a cor
cada vez que aparece em toda a sua folha de estilo. 
* /



/*Mixins
==============================*/

/* Se você achar que você está escrevendo o mesmo código para mais de um
elemento, você pode querer armazenar esse código em um mixin.

center()
  display block
	margin-left auto
	margin-right auto
	left 0
	right 0

/* Utilizando um mixin */
body {
  center()
  background-color: $primary-color
}

/* Apoś compilar ficaria assim: */
div {
	display: block;
	margin-left: auto;
	margin-right: auto;
	left: 0;
	right: 0;
	background-color: #A3A4FF;
}

/* Você pode usar mixins para criar uma propriedade estenográfica. */

size($width, $height)
  width $width
  height $height

.rectangle
  size(100px, 60px)

.square
	size(40px, 40px)

/* Isso compilado ficará assim: */
.rectangle {
  width: 100px;
  height: 60px;
}

.square {
  width: 40px;
  height: 40px;
}

/* Você pode usar um mixin como uma propriedade CSS. */
circle($ratio)
  width $ratio * 2
  height $ratio * 2
  border-radius $ratio

.ball
  circle 25px

/* Isso compilado ficará assim: */
.ball {
  width: 50px;
  height: 50px;
  border-radius: 50px;
}

/*Funções
==============================*/

/* Funções no Styluss permitem fazer uma variedade de tarefas, como por exemplo, manipular cores. */

body {
  background darken(#0088DD, 50%) // Escurece a cor #0088DD em 80%
}
```
