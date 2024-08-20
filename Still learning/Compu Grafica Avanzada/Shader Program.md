Se trata de un conjunto de [[Shader|Shaders]] relcionados entre si, que se encampsula dentro de un objeto del programa.

`unsigned int shaderProgram;
`shaderProgram = glCreateProgram();`

`glAttachShader(shaderProgram, vertexShader);`
`glAttachShader(shaderProgram, fragmentShader);`
`glLinkProgram(shaderProgram);`

`glUseProgram(shaderProgram);`
