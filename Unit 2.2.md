template
---
###
**Activity: **
```C
```
addition substraction, mutiplication and parentheses
plus +
minus -
times/multiplies *

---
###  Printing and computing with integ  
O tópico fala sobre a formatação de números inteiros utilizando um especificador de formato ``%d``. Há um formato específico para cada tipo de dados. Também é abordado sobre cálculos simples, como a soma, subtração, multiplicação e operações com parenteses. A divisão será vista depois, uma vez que é um caso especial em C.  
artigo: https://www.freecodecamp.org/news/format-specifiers-in-c/  
 
**Activity: realizar aritmética simples em C**  
```C
--> trecho a ser formatado
Dear Procrastinator,
You still have to wait for X days (Y minutes or Z seconds) before you can procrastinate!

--> trecho formatando
#include <stdio.h>
int main(void){ 
    int X = 25-23;
    int Y = 60 * 24 * X;
    int Z = 60*Y;
    printf("Dear Procrastinator,\nYou still have to wait for %d days (%d minutes or %d seconds) before you can procrastinate!",X,Y,Z);
    return 0;
}

```

---
### Using variables  
--> lembrar de sempre inicializar variáveis. Na ferramenta usada no codecast o valor de uma variável declarada é 0, caso não lhe seja atribuida valor inicial. Esse não é um comportamento comum em outras ferrmanetas. Caso não seja inicializada, aquele espaço será reservado, mas será atribuído a ele o que quer que estivesse naquele espaço antes.  

A atividade do tópico foi um questionário.  


---
### Declaring and naming variables  
Regras ao definir nomes de variáveis:  
- escolher nomes explícitos  
- não utilizar caracteres especiais(#,@), acentos e espaços entre os nomes. Ao invés de espaços, uma boa prática seria colocar letras maiúsculas no inicio de cada palavra ou um ``_``.   
- apesar de um nome poder ser composto por letras e números, deve somente começar com letras.  

A atividade do tópico foi um questionário.  


--- 
### Repeating instructions with variables    **Activity: imprimir a tabuada de 8**  
```C
#include <stdio.h>
    
    int main (void){
        int i,numMult,result;
        numMult=8;
        for(i=0;i<11;i++){
            result=numMult*i;
            printf("%dx%d = %d\n",i,numMult,result);
        } 
        return 0;
    }
```

---
### Reading user input  
- neste tópico aprendemos a pedir o input pelo terminal usando o ``scanf``.  
```C
---> exemplo de uso  
#include <stdio.h>
int main() {
    int age, month;//DECLARE
    printf("Whare is your age and your birth year?\n");
    scanf("%d%d",&age,&month);
    printf("You are %d years old\nand born in %d", age,month);//USE
    return 0;
}
```  
  
**Activity: ler um número e imprimir sua tabuada**  
```C
#include <stdio.h>
    
    int main (void){
        int i,numMult,result;
        scanf("%d",&numMult);
        
        for(i=0;i<11;i++){
            result=numMult*i;
            printf("%dx%d = %d\n",i,numMult,result);
        } 
        return 0;
    }
``` 

---
### Reading user input inside a loop  
**Activity: leia e processe múltiplos inteiros dentro de um loop**  
```C
#include <stdio.h>
int main(void){
    int i, robotsNumber,height, weight, enginesPower, resistanceRating;
    int result =0;
    
    scanf("%d",&robotsNumber); //scan para receber o número de robos pedidos
    for(i=0;i<robotsNumber;i++){
        scanf("%d%d%d%d", &height,&weight,&enginesPower,&resistanceRating);//recebendo os atributos dos robôs
        result=(enginesPower + resistanceRating) * (weight - height)+result;
    }
    printf("%d",result);
    return 0;
    
}
```     

---
🎯 retomando conhecimentos:  
-> aprendi a usar especificadores de formato, em especial o especifiador de inteiros, para imprimir inteiros.    
-> explicar o que é variável e distinguir a atividade de declaração e atribuição de uma variável.  
-> declarar, atribuir, re-atribuir e atualizar o valor de uma variável do tipo inteiro.  
-> usar variáveis dentro de loops para indicar/modificar intruções.  
-> ler um ou mais entradas de dados de usuário e usar esse dado ára determinar comportamentos de loops.  
  
