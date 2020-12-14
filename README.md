# ASSEMBLER-DOC
Doc assembler
## Assembly Flags
- O
- S (Sing flag)
- Z (Zero flag)
- A
- P
- C (Carri flag)

## Operaciones lógicas
- AND
> AND destino, origen

> Ejemplo:

> AND AX, BX

> //Puede verse de la siguiente forma en lenguaje de alto nivel

> //AX = AX && BX

- OR
> OR destino, origen
- XOR
> XOR destino, origen
- NOT
> NOT destino
- NEG
> NEG destino (complemento A2)
- TEST
El operador TEST resta el operando1 del operando2 sin almacenar el resultado y alterando las banderas
> TEST operando1, operando2
Si se activa la ZF (Zero flag) quiere decir que los operandos son iguales, de lo contrario son diferentes
Si se activa la SF (Sign flag) quiere decir que hay un número negativo
- CMP

> CMP operando1, operando2
Es como una AND sin almacenar el resultado y alterando las banderas

## OPeraciones aritmeticas
### SUMA
- ADD: Suma, suma normal guarda el resultado en el destino, solo activa la bandera Carry
> ADD destino, fuente
- ADC: Suma con acarreeo, suma los dos operandos y suma 1 si la bandera Carry esta activa, suma números de más de 16 bits
> ADC destino, fuente
Para manejar números de 64 bits utilizar los dos neomonicos
- INC: Incremento, incrementa el operando destino en 1, hay que especificar el tamaño, maneja las bandera, pero no modifica el biet de Carry, como a++
> INC destino
### RESTA
- SUB: resta normal, destino menos fuente, 
> SUB destino, fuente
- SBB: resta con acarreo haciendo la negación
> SBB: destino, fuente
- DEC: decremento, no activa la bandera de Carry,  como a--
> DEC destino

### MULTIPLICACIÓN y DIVICIÓN
- MUL: multiplicación sin signo
> MUL fuente  flags {O, C
> MUL BH
Multiplica siempre bh * AH y lo guarda en AX (16 bits)
> MUL BX
Multiplica siembre BX * AX y lo almacena en dos registros (DX:AX)
- IMUL: multiplicación entera, con signo
> IMUL fuente  flags {O, C}
- DIV: división sin signo
> DIV fuente

> MOV destino, fuente// tomarla como igual
> MOV CX, AX // CX = AX
>AND CX, BX
>// CX = CX && BX
> PUSH CX // Metemos el resultado en CX
> //LImpiar registro CX = 0
> XOR CX, CX
> POP CX // Nos devuelbe el primer resultado que se realizo en CX
