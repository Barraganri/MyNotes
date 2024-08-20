## Pipeline de renderizado de [[Computacion Grafica Avanzada]]

### [[Vertex Shader]]
 Coordenada 3D y un color.
 Usado para realizar transformaciones
### Alpha test and blending
- se ejecuta antes de determinar el color del pixel
- revisa la profundidad del fragmento y determina si esta detras o enfrente
- revisa el valor del alpha y mezcla los colores
- Se transforma a NDC del espacio de la pantalla usando el viewport.