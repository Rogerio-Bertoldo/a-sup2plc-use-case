```
FUNCTION_BLOCK R_TRIG
VAR_INPUT
    CLK : BOOL;
END_VAR

VAR_OUTPUT
    Q : BOOL;   
END_VAR


VAR
    LAST_VALUE : BOOL;                // Variavel utilizada para guardar o ultimo valor da variavel de entrada
END_VAR

VAR_TEMP
    EDGE : BOOL;                      // Variavel temporaria utilizada para calcular a borda de subida    
END_VAR


BEGIN
    EDGE:= CLK AND NOT LAST_VALUE;    // Compara o valor atual da entrada com seu ultimo valor lido
    LAST_VALUE:=CLK;                  // Armazena valor da variavel de entrada para proximo calculo
    Q := EDGE;                        // Retorna resultado
END_FUNCTION_BLOCK
```
