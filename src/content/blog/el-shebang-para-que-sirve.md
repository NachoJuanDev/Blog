---
title: 'El shebang, ¿para qué sirve?'
description: 'Shebang, la primera línea de tu script.'
pubDate: 'Apr 19 2024'
heroImage: '/blog/shebang/terminal-1.png'
---

Seguro has notado que los script en bash que ejecutas en tu terminal traen la siguiente primera línea:

```bash
#!/bin/bash
```

O inclusive, algunos scripts en python traen algo similar:

```bash
#!/usr/bin/python3
```

> ¿Y esto para que sirve?

En palabras simples, esta línea indica cual es el intérprete que será utilizado para ejecutar los comandos del script. En el primer ejemplo, estamos indicando que utilizaremos `/bin/bash` y en el segundo `/usr/bin/python3`. Veamos unos ejemplos para que quede más claro.

Crearemos los siguientes dos archivos `script_1.sh` y `script_2.sh`, respectivamente:

```bash
#!/bin/bash
echo "Hello World!"
```

```python
#!/usr/bin/python3
print("Hello World!")
```

> ¿Qué? ¿Un archivo de `Python3` qué termina en `.sh`?

Si, el shebang lo hace posible. Las extensiones de los archivos por lo general indican el tipo de archivo al cual corresponden, sin embargo, en este caso, el shebang será el encargado de señalar a nuestra terminal que interprete debe ejecutar nuestro script cuando lo ejecutemos como un script bash cualquiera. No debemos olvidar dar los permisos de ejecución a nuestros script:

```bash
chmod +x script_1.sh script_2.sh
```

Con esto, podemos ejecutar nuestros scripts:

![Terminal con ejecución de los dos scripts](/blog/shebang/terminal-1.png)

Como vemos, ambos scripts funcionaron correctamente. Nuestra terminal, eligió el interprete señalado por el shebang.

Por último, por si te estás preguntando por qué se llama shebang, Jason Cannon en su libro de Shell Scripting[^1] señala lo siguiente:

> The number sign is very similar to the sharp sign used in music notation.  Also, some people refer to the exclamation mark as a "bang."  So, #! can be spoken as "sharp bang."  The term "Shebang" is an inexact contraction of "sharp bang."

> El signo de número es muy similar al signo sostenido utilizado en notación musical. Además, algunas personas se refieren al signo de exclamación como "bang". Así, #! puede pronunciarse como "sharp bang". El término "Shebang" es una contracción inexacta de "sharp bang".

[^1]: Cannon, Jason. Shell Scripting: How to Automate Command Line Tasks Using Bash Scripting and Shell Programming (English Edition) (p. 3). Edición de Kindle.
