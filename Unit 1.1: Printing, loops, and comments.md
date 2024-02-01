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

---
### Simple looping errors  

Algumas particularidades da linguagem C foram descobertas destrinchando alguns erros de loop. Quando há a abertura e fechamento das chaves do ``main (void)``, e o loop está escrito corretamente lá dentro, não há um erro denunciando pelo compilador, pois o loop, de certa forma, funcionará. 
O que acontece é que sem as chaves delimitando o loop, ele repetirá apenas a primeira instrução no número determinado de vezes, desconsiderando as outras intruções para a repetição. Isso gera um erro de coomportamento, e não de sintaxe. Segue exemplo abaixo:  

```C
#include <stdio.h>
int main(void) {
    int i;
    for(i = 0; i < 3 ; i++ ) {
        printf("Hello ");
        printf("world!\n");
    }
    return 0;
}
	retorna: "Hello World Hello World Hello World"

#include <stdio.h>
int main(void) {
    int i;
    for(i = 0; i < 3 ; i++ ) 
        printf("Hello ");
        printf("world!\n");
    
    return 0;
}
	retorna: "Hello Hello Hello World"
```  

**Activity: correct simple errors in loops with missing braces**  
Proposta: correção de código incompleto.
```C

--> resultado esperado
+-----------------------+                                                       
| o | X | o | X | o | X |                                                       
| X | o | X | o | X | o |                                                       
| o | X | o | X | o | X |                                                       
| X | o | X | o | X | o |                                                       
| o | X | o | X | o | X |                                                       
| X | o | X | o | X | o |                                                       
+-----------------------+ 

--> Trecho original: 
#include <stdio.h>

int main(void) {

    int i;

    printf("+");
    for (i = 0; i < 23; i++)
        printf("-");
    printf("+\n");

    for (i = 0; i < 3; i++)
        printf("| o | X | o | X | o | X |");
        printf("\n");
        printf("| X | o | X | o | X | o |");
        printf("\n");

    printf("+");
    for (i = 0; i < 23; i++)
        printf("-");
    printf("+");

    return(0);
}

--> Trecho corrigido: 
#include <stdio.h>

int main(void) {
    int i;
    printf("+"); // imprime o + do início da linha
    for (i = 0; i < 23; i++){
        printf("-"); // imprime a linha superior
    }
    printf("+\n"); // imprime o + do fim da linha
    for (i = 0; i < 3; i++){
        printf("| o | X | o | X | o | X |");
        printf("\n");
        printf("| X | o | X | o | X | o |");
        printf("\n");
    }
    printf("+"); // imprime o + do início da linha
    for (i = 0; i < 23; i++){
        printf("-"); // imprime a linha inferior
    }
    printf("+\n"); // imprime o + do fim da linha
    return(0);
}

```

---
### Commenting your code  

**Activity: add comments to existing code**  
Proposta: adequar o código às regras do trabalho, sãe elas: ``Programs cannot use for-loops with more than 10 repetitions`` e ``Programs are not allowed to say 'goodbye!'.``  
```C
#include <stdio.h>

int main(void) {
    int i;
    printf ("Welcome, humans!\n");
    printf ("I am Buttons, your robot instructor! \n");
    printf ("Today we are going to learn how to love robots :) \n");
    printf ("Repeat after me: \n");
    for (i = 0; i < 3; i ++)
        printf ("I love Buttons!\n");
    printf ("Still not convinced? \n");
    printf ("In that case, let me explain some more ... \n");
    /*for (i = 0; i < 200; i++) {
        printf ("We come in peace and kindness! \n");
        printf ("A robot cannot hurt a human being or ");
        printf ("allow a human being to be hurt. ");
    }*/
    printf ("This is the end of today's lesson! ");
    printf ("Thank you for your cooperation, and");
    //printf ("goodbye!");    
    return(0);
}
```

---
### Structure of a simple C program  

```C
--> estrutura de um programa em C simples
// preprocessor directive 
#include <stdio.h>

// main function
int main(void) {
    // variable declarations
    int i = 0;
    
    // executable statements
    for(i = 0; i < 3 ; i++) {
        printf("Blah");
        printf("Bleh");
        printf("Blih "); 
    }
    
    // return statement
    return 0;
}
```

**Activity: put lines in the correct order**  
Proposta: Organizar o código na ordem correta.  

```C
--> Código original
    printf("I ");
    for(i = 0; i < 3 ; i++) {
        printf("love ");
    }
    return(0);
    printf("programming!");
    #include <stdio.h>
}
int main(void){
    int i;

--> Código corrigido (deixando de delimitar o loop for)
    // preprocessor directive 
    #include <stdio.h>
    
    // main function
    int main(void){
    // variable declarations
    int i;    
    // executable statements
    printf("I ");
    for(i = 0; i < 3 ; i++) 
        printf("love ");
        printf("programming!");
    
    // return statement
    return(0);

(delimitando o loop for)
    // preprocessor directive 
    #include <stdio.h>
    
    // main function
    int main(void){
    // variable declarations
    int i;    
    // executable statements
    printf("I ");
    for(i = 0; i < 3 ; i++){
        printf("love ");
    } 
        printf("programming!");
    
    // return statement
    return(0);
}
```

---
Retomando conhecimentos: 😎  

-> modificar o programa "Hello World" para criar um programa que imprime texto e caracteres especiais;  
-> criar programas C que utilizam um ou mais loops para repetir uma ou mais instruções em um determinado número de vezes;  
-> explicar o programa com comentários;  
-> usar comentários de diferentes formas;  
-> identificar e rotular partes do programa, como função principa;  
