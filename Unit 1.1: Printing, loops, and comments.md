# Unit 1.1: Printing, loops, and comments  

 ### Correcting simple syntax errors  

**Activity: corrija erros de sintaxe simples**  
A atividade proposta pedia para que realizasse a correção de simples erros na escrita de um código. As mensagens de erro do compilador são deixadas junto com o trecho de código.  
```
	MENSAGENS DE ERRO  

/user-input:4:43: error: expected ';' after expression
    printf ("This is code with errors : ")
                                          ^
                                          ;
/user-input:5:11: error: expected ';' after expression
    printf "Fix them!";
          ^
          ;
/user-input:5:5: warning: expression result unused
    printf "Fix them!";
    ^~~~~~
/user-input:5:12: warning: expression result unused
    printf "Fix them!";
``` 

Em seguida temos o trecho do código errado e sua resolução:  
```C
--> trecho 

#include <stdio.h>

int main(void) {
    printf ("This is code with errors: ")
    printf "Fix them!";
    return 0;
}  


--> trecho resolvido  

#include <stdio.h>

int main(void) {
    printf ("This is code with errors: "); /*nesta linha havia ausência
    do ponto e vírgula ao final do código.*/
    printf ("Fix them!"); /*nesta linha faltavam os dois parênteses, tanto 
    de abertura quanto de fechamento.*/
    return 0;
}

```  

A resolução envolvia sinais simples, mas gerou 4 mensagens de erros. A resolução atendeu somente a necessidade da mensagem ``user-input:4:43``, sendo as indicações das outras não muito úteis para resolver o problema, como foi falado no codecast.  

---
### Printing text and new lines  

**Activity: imprimir texto em várias linhas**    
Esta atividade propôs a impressão de texto em mais de uma linha, utilizando a ``escape sequence`` ensinada no codecast.  
```C
--> linhas a serem impressas    
I already know how to:
- Print text to the screen.
- Start a new line.
- Fix errors.

--> código para a impressão  
#include <stdio.h>

int main(void) {
    printf("I already know how to:\n- Print text to the screen.\n- Start a new line.\n- Fix errors.");
    return 0;
}

> como opção para um código mais legível:   
#include <stdio.h>

int main(void) {
    printf("I already know how to:\n");
    printf("- Print text to the screen.\n");
    printf("- Start a new line.");
    printf("\n- Fix errors.");
    return 0;
}
```
  
---
### Printing multiple lines with one printf statement  

**Activity: imprimir múltiplas linhas**  
A atividade propõe que uma série de caracteres seja impresso em um único ``printf``, gerando um pequeno desenho.  
```C
--> caracteres para imprimir
	*****
	**|**
	*|.|*
	|...|
	.....

--> código imprimindo
#include <stdio.h>
int main(void){
    printf("*****\n**|**\n*|.|*\n|...|\n.....");
    return 0;
}
```  

---
### Printing quotation marks, escaping special characters  

**Activity: imprimindo caracteres especiais**  
A atividade propõe a prática na impressão de caracteres especiais, as ``"" - quotation marks - aspas`` em específico, utilizando somente um ``printf``  
```C
--> trecho para imprimir
Dennis Ritchie said:                                                        
"The only way to learn a new programming language is by writing programs in it."

--> código
#include <stdio.h>
int main(void){
    printf("Dennis Ritchie said:\n\"The only way to learn a new programming language is by writing programs in it.\"");
    return 0;
}
```  

---
### Repeating one instruction with a for loop 

**Activity: utilize um loop for para imprimir uma linha múltiplas vezes**    
A atividade propõe a repetição da mensagem ``C is fun!`` utilizando loops.
```C
# include <stdio.h>
int main(void){
    int i = 0;
    for(i=0;i<3;i++){
        printf("C is fun!\n");
    }
    return 0;
}
```  

---
### Repeating a block of instructions with a for loop  
   
**Activity: use múltiplos loops for**    
Essa atividade propõe o uso de mais de um loop para a repetição das mensagens ``C is fun!`` e ``We can do everything with it!``  
```C
#include <stdio.h>
int main(void){
    int i;
    for(i=0;i<3;i++){
        printf("C is fun!\n");
    }
    
    printf("\n");
    for(i=0;i<5;i++){
        printf("We can do everything with it!\n");
    }
    return 0;
}
```  
