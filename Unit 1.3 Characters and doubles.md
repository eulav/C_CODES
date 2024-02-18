---
###
**Activity: **
```C
```

---  
### Using characters  
Este tópico ensina-nos a utilizar a variável ``char``, junto com seu especificador de formato ``%c``.  

**Activity: imprima caracteres**  
Proposta: imprimir a seguinte frase:  ``Programming in C`` utilizando uma estrutura mostrada no exercício. 
```C
--> estrutura
rintf ("Programming %c%c %c\n", letter1, letter2, letter3);

--> código  
#include <stdio.h>
int main (void){
    char letter1 = 'i'; //lembrar sempre das aspas simples ao atribuir valor ao tipo char
    char letter2 = 'n';
    char letter3 = 'C';
    
    printf ("Programming %c%c %c\n", letter1, letter2, letter3);
    
    return 0;
}

```

---  
### Reading characters from the user input  
- Este tópico nos mostra como receber o caractere do usuário utilizando o ``scanf``. Entretanto, diferente de como acontece com os inteiros, ao utilizar scanf para ler dados tipo ``char``, não deve-se espaçá-los se isso não for pré-definido na parte entre aspas. Com o char, os espaços são considerados caracteres extras, causando outro comportamento.  

**Activity: leia caracteres**  
Proposta: um programa que leia um caractere e imprima um padrão de pirâmide com ele.  
```C
--> exemplo do padrão  
input: #
     ++++#++++
     +++###+++
     ++#####++
     +#######+
     #########

--> código (método ainda burro, escrevi depois de um start lendo a dica)
#include <stdio.h>
int main(void){
    int i;
    char patternChar;
    scanf("%c",&patternChar);
    
    printf("++++%c++++\n",patternChar);
    
    printf("+++");
    for (i=0;i<3;i++){
        printf("%c",patternChar);
}
        printf("+++\n");
        
    printf("++");
    for (i=0;i<5;i++){
        printf("%c",patternChar);
}
        printf("++\n");
        
    printf("+");
    for (i=0;i<7;i++){
        printf("%c",patternChar);
}
        printf("+\n");
        
    for (i =0; i<9;i++){
        printf("%c",patternChar);
     }
    return 0;
}

--> código adaptado do chat utilizando o aninhamento de for (pensei em algo assim, mas só consegui desenvolver o código de cima)
int main (void) { 
  char patternChar; //declara a variável char
  scanf ("%c", &patternChar); //recebe o valor e o atribui à  variàvel

  for (int i = 0; i < 5; i++){ //primeiro for, que define quantas linhas a pirâmide terá
  
	  for (int j = 0; j < 5 - i - 1; j++){ //este segundo for coloca os "+" ANTES do caractere
		  //utiliza uma nova variável (j), na segunda informação, subtrai do número geral de linhas da pirâmide o número referente à execução e depois subtrai por 1(sempre subtrai 1 do número anterior)
		  printf ("+");//informação que deve ser impressa repetida
		}
		
	  for (int j = 0; j < 2 * i + 1; j++){//imprime na mesma linha o caráctere de entrada
	  //utilizando mais uma nova variável de escopo, sob a regra de 2 multiplicado pelo número da execução somado a 1(que sempre adiciona mais dois caracteres ao número anterior)
		  printf ("%c", patternChar);//informação a ser impressa
		}
		
	  for (int j = 0; j < 5 - i - 1; j++){ //imprime os "+"'s do final, sob a mesma regra do primero for
		  printf ("+");
		}
		
	  printf ("\n");//pula uma linha
	}
  return 0;
}

```  

---  
### Using decimals    
Este tópico nos apresenta a variável de tipo decimal ``double``. É ensinado que, em C, por padrão, um número possui 6 casa decimais.
Aprendemos a delimitar o número de casas decimais uma impressão de decimal deve ter, dessa forma: ``%.2lf`` -> %lf é o especificador de formato para decimais.  
Ao trabalhar com decimais, a linguagem arrendonda o número para o mais próximo.  
Também é ensinado como utilizar um scanf para ler inteiro e decimal na mesma sentença. -> ``scanf("%d %lf",&age,&height);``  
**Activity: leia um número decimal**
Proposta: converter Km para Milha.    
```C
#include <stdio.h>
int main(void){
    
    double dKm, dMiles;
    
    scanf("%lf", &dKm);
    dMiles = dKm*0.621371;
    printf("%.6lf",dMiles);
    
    return 0;
    
}
```  

---  
### Dividing in C  
Existem dois comportamentos para a divisão em C, entre inteiros com um resultado inteiro, e entre números decimais.
A divisão é feita utilizando uma barra ``/``. Se for uma divisão entre 2 inteiros, para o resultado somente será considerado a parte inteira, e o mesmo aplica-se a divisão decimal. Deve-se estar sempre atento ao especificador de formato utilizado, pois ele deve estar de acordo com o dado do argumento.  
**Activity: divida números**   
Proposta: fazer um código que convertesse Graus Celsius to Fahrenheit.
```C
--> código que faz a Conversão 
#include <stdio.h>
int main (void){
    double celsiusTemp = 0;
    double fahrTemp = 0;
    
    scanf("%lf", &celsiusTemp);
    fahrTemp = celsiusTemp*9.0/5.0+32.0;
    
    printf("%.1lf",fahrTemp);
    return 0;
}

```  

---  
### Finding the remainder  
Neste tópico aprendemos a achar o módulo, comumente chamado de resto da divisão. Para isso, usamos o sinal de porcentagem ``%```, sinal recorrente também em outras linguagens.   
**Activity: Ache o resto na divisão inteira**  
```C
--> código 
#include <stdio.h> 
int main(void){
    int matches=0;
    int boxes=0;
    
    scanf("%d %d",&matches,&boxes);
    int fullBoxes = matches/boxes;
    int leftoverMatches = matches%boxes;
    
    printf("%d\n%d",fullBoxes,leftoverMatches);
    return 0;
}

```

---  
### Converting integers to decimals  
Em C, o processo de conversão é chamado de cast. Para isso, atibuímos o valor convertido à variável de tipo desejado, dessa forma: ``dOne = (double) iOne;`` -> dOne é a variável tipo double. Ao passar a variável int para dOne, colocamos o tipo entre parênteses, fazendo o cast/conversão.  Também é possível fazer casts com operações, como no exemplo a seguir: ``dOne = (double) iOne/iTwo;``.   
**Activity: converta inteiros para double**    
```C
--> código solução  
#include <stdio.h>
int main(void){
    int howManyGrades=0;
    int grades[4];
    
    scanf("%d",&howManyGrades);
    
    for (i=0;i<howManyGrades;i++){
        scanf("%d",&grades[i]);
        gradesSum += grades[i];
}
    double average = (double) gradesSum/howManyGrades;
    
    printf("%.2lf",average);
    
    return 0;
}
```
PS: muitos aprendizados com esse código, principalmente sobre variáveis de escopo e globais. Além de aprender a conferir bem os pequenos detalhes.  

---  
### Converting decimals to integers  
**Activity: converta double em inteiros**  
```C
#include <stdio.h>
int main (void){
    int currentPop=0;
    double percentGrowth=0;
    
    scanf("%d", &currentPop);
    scanf("%lf",&percentGrowth);
    percentGrowth = percentGrowth/100;
    
    
    int futurePop = (int)currentPop+(currentPop*percentGrowth);
    
    printf("%d",futurePop);
    
    return 0;
}
```  

---  
### Practicing division  
**Activity: divida decimais**  
```C
#include <stdio.h>
int main (void){
    double totalMoney,bookPrice;
    
    scanf("%lf",&totalMoney);
    scanf("%lf",&bookPrice);
    
    double totalPurchase = totalMoney/bookPrice;
    
    printf("%d",(int) totalPurchase);
    
    return 0;
    
}
```  

**Activity: divida decimais com arrendodamento**  
```C
#include <stdio.h>
int main (void){
    double cementNeeded;
    
    scanf("%lf", &cementNeeded);
    
    int pounds = 120;
    int totalBags = 1;
    
    while(pounds < cementNeeded){
        pounds+=120;
        totalBags+=1;
    }
    
    int totalCost = 45*totalBags;
    
    printf("%d",totalCost);
    return 0; 
}
```   

📌 Retomando conhecimentos: 
-> aprendi a distinguir variáveis tipo int, double e char.  
-> declarar e atribuir valor à variáveis tipo double e char.  
-> usar os especificadores corretos para imprimir e ler dados.  
-> compreender os comportamentos da divisão em C.
-> fazer a conversão(cast) e explicar sua importância.
-> criar programas em C que envolvem input de usuários, inteiros e número decimais.




