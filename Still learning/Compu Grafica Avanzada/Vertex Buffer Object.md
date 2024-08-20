---
aliases:
  - VBO
tags:
  - CGA
---

Almacenan info mandada de los [[Vertex Shader|Vertices]] en memoria, para que se mantenga hasta que no sea utilizada.


El objeto no contiene info. Solo tiene un ID y un nombre al principio.
Pra copiar la info se usa la siguiente funcion:
`glBufferData(GL_ARRAY_BUFFER)`

### Pasos para generar un VBO
- `unisgned int VBO;`
- `glGenBuffers(1, &VBO);
Para este punto se cre un identificador sin informacion.
- `glBindBuffer(GL_ARRAY_BUFFER, VBO);`
Se debe indicar que tipo de buffer es. Por ello se indica que es un buffer de vertices.
- `glBufferData(GL_ARRAY_BUFFER, sizeof(vertices), vertices, GL_STATIC_DRAW);`
Se usa esta funcion para copiar la informacion del obejto vertices al buffer.


