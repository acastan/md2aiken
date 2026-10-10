# Covertir entre test Markdown y test Aiken

Mi lenguaje preferido para edición de textos es [Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax). Con él edito apuntes, ejercicios, tests, etc. Algunos de los tests que publico en Markdown me interesa importarlos después en Moodle en [formato Aiken](https://docs.moodle.org/500/en/Aiken_format).

Este es un ejemplo de test en Markdown:

```
    01. ¿Cuantos bytes tiene una dirección de IP versión 4?
        - [ ]  2
        - [x]  4
        - [ ]  32
```

Y este es un ejemplo del mismo test en Aiken:

```
    ¿Cuantos bytes tiene una dirección de IP versión 4?
    A) 2
    B) 4
    C) 32
    ANSWER: B
```

Comparto un sencillo programa para convertir de un formato al otro. En este código pretendo priorizar la sencillez a la elegancia y versatilidad. No utilizo clases ni expresiones regulares, ni cubro el [formato GIFT](https://docs.moodle.org/500/en/GIFT_format), mucho más potente.

Asumo que las preguntas en Markdown son identificadas al inicio por `##` o `número.` , que la pregunta ocupa una línea, que pueden haber líneas en blanco entre preguntas y respuestas, y varias líneas en blanco entre preguntas, y que las respuestas son identificadas al inicio por `- [ ]` o por `- [x]`

Uso:

    $ md2aiken test.md test.txt
    $ aiken2md test.txt test.md
