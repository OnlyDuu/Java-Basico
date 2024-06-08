## Java - Conceitos Básicos: 

### Tipos de Dados Primitivos
A linguagem Java não é totalmente Orientada a Objetos, e isto se deve principalmente aos atributos do tipo primitivo, pois são tipos de dados que não representam classes, mas sim valores básicos.<br>
Os tipos primitivos, assim como em várias outras linguagens tais como o C, existem para representar os tipos mais simples de dados, sendo eles dados numérico, booleano e caractere.<br>
Em Java, nós temos oito tipos primitivos:


<img src= src/tipos-primitivos.png>

Os tipos numéricos podem ser divididos em Integrais (byte, short, int, long, char) e Ponto Flutuante (float e double). Também temos o tipo boolean que aceita true ou false, tipo primitivo propriamente dito. É importante dizer que, apesar de uma variável do tipo char receber um caractere, essa variável também pode receber valores literais do tipo int e unicode.

---

### Operadores Aritméticos em Java
<img src=src/operadores.jpg>

---

### Operadores Lógicos
Os operadores lógicos aceitam apenas operando do tipo boolean.
#### Operadores E:
Símbolo && é chamado de E. Este operador retorna true somente se os dois operandos forem true.<br>
< operando1 > && < operando2 ><br>
Se o valor do operando1 for false, então o operador && não verifica o valor do operador2, pois sabe que o resultado já é false.

##### Tabela Verdade E:
<img src=src/tabela-verdade.png>

##### Exemplo:
    public class OperadorLogicoE {
        public static void main(String[] args) {
            boolean a = true;
            boolean b = false;
            boolean c = true;

            System.out.println(a && b);
            System.out.println(a && c);
        }
    }
Neste caso será impresso false, pois a variável a é true e a variável b é false, depois será impresso true, pois ambas variáveis a e c são true.

#### Operador OU: 
Símbolo || é chamado de OU. Este operado retorna true caso tenha pelo menos um operando com o valor true.<br>
< operando1 > || < operando2 ><br>
Se o valor do operando1 for true, então o operador || não verifica o valor do operando2, pois já sabe que o resultado é true.<br>

##### Tabela Verdade OU:
<img src=src/tabela-verdade-ou.png>

##### Exemplo: 
    public class OperadorLogicoOU {
        public static void main(String[] args) {
            boolean a = true;
            boolean b = false;
            boolean c = false;

            System.out.println(a || b);
            System.out.println(b || c);
        }
    }
Neste caso será impresso primeiro true, pois a variável a tem o valor true, depois será impresso false, pois as variáveis b e c são false.

#### Operador de negação:
Símbolo ! é chamado de negação. Este operador retorna true se o operando tem o valor false, e retorna false se o operando o valor true.<br>
! < operando ><br>
##### Tabela Verdade: 
Operando    -   Resultado<br>
false   -   true<br>
true    -   false
##### Exemplo:
    public class OperadorLogicoNegacao {
        public static void main(String[] args) {
            boolean a = true;
            boolean b = false;
            boolean c = false;

            System.out.println(!a);
            System.out.println(!(b || c));
         }
    }
Neste caso primeiro será impresso false, que é a negação de true, depois será impresso true, que é a negação do resultado de b || c que é false.