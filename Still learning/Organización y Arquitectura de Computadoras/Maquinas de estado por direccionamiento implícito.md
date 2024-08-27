---
up: "[[Organización y Arquitectura de Computadoras]]"
---
# Estructura
![[Pasted image 20240826191703.png|Diagrama de m[aquina de estado por direccionamiento implicito]]
Se aprovecha la **propiedad del contador de autoincrememntarse y hacer cargas en paralelo**

Las entradas entran al sistema por medio de un MUX llamado prueba.
![[Pasted image 20240826192223.png]]
![[Pasted image 20240826192253.png]]

# Ventajas
- Mayor ahorro de energía
- Se compone de (ROM, Contador, un multiplexor y 2 compuertas lógicas)
- Se pueden implementar varios sistemas al cambiar los contenidos de la memoria.
# Desventajas
- Solo una entrada por estado
- No salidas condicionales sin que se modifique
- estructura (n,n+1,P)

# Ejemplo
![[Pasted image 20240826192722.png|ASM Ejemplo]]
## Pasos a seguir:
- Enumerar las entradas incluyendo a Qaux

| Entrada | Binario |
| :-----: | :-----: |
|    X    |   00    |
|    Y    |   01    |
|    Z    |   10    |
|  Qaux   |   11    |

- Se dimensiona la memoria y se decide el encabezado
![[Pasted image 20240826193336.png]]

- La tabla queda asi:
![[Pasted image 20240826194200.png||400]]

| $P_3\;P_2\;P_1\;P_0$ | $K_1\;K_0$ | $V_3\;V_2\;V_1\;V_0$ | VF  | $S_3\;S_2\;S_1\;S_0$ |
| -------------------- | ---------- | -------------------- | --- | -------------------- |
| 0000                 | 11         | 0010                 | 0   | 0001                 |
| 0001                 | 00         | 0001                 | 1   | 0001                 |
| 0010                 | 00         | 0110                 | 1   | 0010                 |
| 0011                 | 10         | 1011                 | 0   | 1000                 |
| 0100                 | 01         | 1011                 | 0   | 0100                 |
| 0101                 | 10         | 0101                 | 1   | 0010                 |
| 0110                 | 11         | ****                 | 1   | 1100                 |
| 0111                 | 00         | 0111                 | 1   | 0001                 |
| 1000                 | 01         | 0001                 | 1   | 0000                 |
| 1001                 | 10         | 0000                 | 0   | 1100                 |
| 1010                 | 11         | 0010                 | 0   | 1100                 |
| 1011                 | 11         | 1000                 | 0   | 0010                 |
| 11**                 | 11         | 0000                 | 0   | 0000                 |
![[Pasted image 20240826195818.png]]
![[Pasted image 20240826195833.png]]
![[Pasted image 20240826195845.png]]
