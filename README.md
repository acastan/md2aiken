# md2aiken

Programa sencillo para convertir tests en formato Markdown a tests en formato Aiken

Mi lenguaje preferido para edición de textos es [Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax). Con él edito apuntes, ejercicios, tests, etc.

Algunos de los tests que publico en Markdown me interesa importarlos después en Moodle en [formato Aiken](https://docs.moodle.org/500/en/Aiken_format).

Ejemplo de test em Markdown:

> 01. ¿Cuantos bytes tiene una dirección de IP versión 4?
>    - [ ]  2
>    - [x]  4
>    - [ ]  32

Ejemplo del mismo test en Aiken:

> ¿Cuantos bytes tiene una dirección de IP versión 4?
> A) 2
> B) 4
> C) 32
> ANSWER: C

Este es un sencillo programa para convertir de un formato al otro. Lo comparto, por si os puede servir, aunque en esta era con IA LLM podéis generar vuestro propio programa al instante. En este código pretendo priorizar la sencillez a la elegancia y versatilidad. No utilizo clases ni expresiones regulares. No cubro el [formato GIFT](https://docs.moodle.org/500/en/GIFT_format) , mucho más potente.

Asumo que las preguntas em Markdown son identificadas por `##` o `número.` , que la pregunta ocupa una línea, que pueden haber líneas en blanco entre preguntas y respuestas, y varias líneas en blanco entre preguntas, y que las respuestas son identificadas por `- [ ]` o por `- [x]`

Uso:
    $ md2aiken test.md test.txt
    $ aiken2md test.txt test.md
