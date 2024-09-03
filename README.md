# teste-tecnico-target-sistemas

1) Dado a sequência de Fibonacci, onde se inicia por 0 e 1 e o próximo valor sempre será a soma dos 2 valores anteriores (exemplo: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...), escreva um programa na linguagem que desejar onde, informado um número, ele calcule a sequência de Fibonacci e retorne uma mensagem avisando se o número informado pertence ou não a sequência.

IMPORTANTE: Esse número pode ser informado através de qualquer entrada de sua preferência ou pode ser previamente definido no código;

Resposta:

``` java
package org.example;

import java.util.Scanner;

public class FibonacciChecker {

    public static void main(String[] args) {
        // Scanner para ler a entrada do usuário
        Scanner scanner = new Scanner(System.in);
        System.out.print("Informe um número para verificar se pertence à sequência de Fibonacci: ");
        int numero = scanner.nextInt();

        // Variáveis iniciais da sequência de Fibonacci
        int a = 0;
        int b = 1;

        // Caso especial para 0 e 1
        if (numero == a || numero == b) {
            System.out.println("O número " + numero + " pertence à sequência de Fibonacci.");
            return;
        }

        // Variável que armazenará o próximo número da sequência
        int c = a + b;

        // Gerar a sequência até que c seja maior ou igual ao número informado
        while (c <= numero) {
            if (c == numero) {
                System.out.println("O número " + numero + " pertence à sequência de Fibonacci.");
                return;
            }

            // Atualizar a sequência
            a = b;
            b = c;
            c = a + b;
        }

        // Se o loop terminar, significa que o número não foi encontrado na sequência
        System.out.println("O número " + numero + " não pertence à sequência de Fibonacci.");
    }
}

```

2) Escreva um programa que verifique, em uma string, a existência da letra ‘a’, seja maiúscula ou minúscula, além de informar a quantidade de vezes em que ela ocorre.

IMPORTANTE: Essa string pode ser informada através de qualquer entrada de sua preferência ou pode ser previamente definida no código;


``` java

import java.util.Scanner;

public class LetraAChecker {

    public static void main(String[] args) {
        // Scanner para ler a entrada do usuário
        Scanner scanner = new Scanner(System.in);
        System.out.print("Informe uma string para verificar a existência da letra 'a': ");
        String inputString = scanner.nextLine();
        
        // Variável para contar as ocorrências da letra 'a' ou 'A'
        int count = 0;
        
        // Percorrer a string e contar as ocorrências
        for (int i = 0; i < inputString.length(); i++) {
            char currentChar = inputString.charAt(i);
            if (currentChar == 'a' || currentChar == 'A') {
                count++;
            }
        }
        
        // Verificar se a letra 'a' apareceu na string
        if (count > 0) {
            System.out.println("A letra 'a' aparece " + count + " vez(es) na string.");
        } else {
            System.out.println("A letra 'a' não aparece na string.");
        }
    }
}

```

3) Observe o trecho de código abaixo: int INDICE = 12, SOMA = 0, K = 1; enquanto K < INDICE faça { K = K + 1; SOMA = SOMA + K; } imprimir(SOMA);

Ao final do processamento, qual será o valor da variável SOMA?

``` Java

int INDICE = 12, SOMA = 0, K = 1;
while (K < INDICE) {
    K = K + 1;
    SOMA = SOMA + K;
}
System.out.println(SOMA);

```

4) Descubra a lógica e complete o próximo elemento:
a) 1, 3, 5, 7, ___
b) 2, 4, 8, 16, 32, 64, ____
c) 0, 1, 4, 9, 16, 25, 36, ____
d) 4, 16, 36, 64, ____
e) 1, 1, 2, 3, 5, 8, ____
f) 2,10, 12, 16, 17, 18, 19, ____

a) 1, 3, 5, 7, ___

A lógica é simples: a sequência é formada por números ímpares consecutivos. Portanto, o próximo elemento é:

9
b) 2, 4, 8, 16, 32, 64, ____

A lógica é uma sequência de potências de 2. Cada elemento é o dobro do anterior. Portanto, o próximo elemento é:

128
c) 0, 1, 4, 9, 16, 25, 36, ____

A lógica é uma sequência de quadrados perfeitos. Cada elemento é o quadrado de um número inteiro consecutivo. Portanto, o próximo elemento é:

49
d) 4, 16, 36, 64, ____

A lógica é uma sequência de quadrados perfeitos, mas com um fator de 4. Cada elemento é o quadrado de um número inteiro consecutivo multiplicado por 4. Portanto, o próximo elemento é:

100
e) 1, 1, 2, 3, 5, 8, ____

A lógica é a sequência de Fibonacci. Cada elemento é a soma dos dois elementos anteriores. Portanto, o próximo elemento é:

13
f) 2, 10, 12, 16, 17, 18, 19, ____

Essa sequência é um pouco mais difícil. A lógica é uma sequência de números que aumentam de 2 em 2, mas com alguns saltos. Se analisarmos a sequência, podemos ver que os saltos ocorrem a cada 3 elementos. Portanto, o próximo elemento é:

20
Mas, se considerarmos que a sequência pode ter uma lógica mais complexa, podemos tentar encontrar outra explicação. Uma possível explicação é que a sequência é formada por números que são a soma de 2 e um número primo. Nesse caso, o próximo elemento seria:

22 (2 + 20, onde 20 é um número primo)
No entanto, é importante notar que essa sequência pode ter várias explicações possíveis, e a resposta correta depende do contexto em que a sequência foi apresentada.


5) Você está em uma sala com três interruptores, cada um conectado a uma lâmpada em salas diferentes. Você não pode ver as lâmpadas da sala em que está, mas pode ligar e desligar os interruptores quantas vezes quiser. Seu objetivo é descobrir qual interruptor controla qual lâmpada. Como você faria para descobrir, usando apenas duas idas até uma das salas das lâmpadas, qual interruptor controla cada lâmpada?  

**Primeira ida até a sala das lâmpadas:**

1. Ligue o interruptor 1 por 5 minutos.
2. Desligue o interruptor 1 e ligue o interruptor 2.
3. Vá até a sala das lâmpadas.

**O que você deve observar:**

* Se uma lâmpada estiver acesa, é a lâmpada controlada pelo interruptor 2.
* Se uma lâmpada estiver quente (mas apagada), é a lâmpada controlada pelo interruptor 1.
* Se uma lâmpada estiver fria e apagada, é a lâmpada controlada pelo interruptor 3.

**Segunda ida até a sala das lâmpadas:**

1. Desligue o interruptor 2.
2. Ligue o interruptor 3.
3. Vá até a sala das lâmpadas.

**O que você deve observar:**

* Se a lâmpada que estava acesa na primeira ida agora estiver apagada, é a lâmpada controlada pelo interruptor 2.
* Se a lâmpada que estava quente na primeira ida agora estiver acesa, é a lâmpada controlada pelo interruptor 1.
* Se a lâmpada que estava fria e apagada na primeira ida agora estiver acesa, é a lâmpada controlada pelo interruptor 3.

Com essas duas idas até a sala das lâmpadas, você pode descobrir qual interruptor controla cada lâmpada.


