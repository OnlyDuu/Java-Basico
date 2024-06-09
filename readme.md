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

---

### Laços Númericos

#### Estruturas condicionais 
As estruturas condicionais possibilitam ao programa tomar decisões e alterar o seu fluxo de execução. Isso possibilita ao desenvolvedor o poder de controlar quais são as tarefas e trechos de código executados de acordo com diferentes situações, como os valores de variáveis.
<br>
As estruturas condicionais geralmente analisam expressões booleanas e, caso estas expressões sejam verdadeiras, um trecho do código é executado. No caso contrário, outro trecho do código é executado.

#### If/else: 
O if/else é uma estrutura de condição em que uma expressão booleana é analisada. Quando a condição que estiver dentro do if for verdadeira, ela é executada. Já o else é utilizado para definir o que é executado quando a condição analisada pelo if for falsa. Caso o if seja verdadeiro e, consequentemente executado, o else não é executado.
<br>
O if pode ser utilizado em conjunto com o else ou até mesmo sozinho, caso necessário.
<br>
Abaixo, temos um exemplo onde o if é utilizado em conjunto com o else.
<br>
   
    public class Exemplo {
	
        public static void main(String[] args) {
            int resposta = 10;
            if (resposta == 10) {
                // Se a variável for igual a 10, a frase abaixo será escrita
            System.out.println(“Você acertou!”);
            } else {
                // Caso contrário, a frase abaixo será escrita
            System.out.println(“Você errou!”);
            }
        }	
    }
Também podemos usar o if somente, não definindo um fluxo alternativo: 
<br>
    public class Exemplo {
	
        public static void main(String[] args) {
            int resposta = 10;
            if (resposta == 10) { 
                // Se a variável for igual a 10, a frase abaixo será escrita
                System.out.println(“Você acertou!”);
            }
            // Se a variável não for igual a 10, nenhuma frase será exibida
        }	
    }
Ainda é possível encadear múltiplas estruturas if/else caso necessário.
    public class Exemplo {
	
        public static void main(String[] args) {
            int resposta = 10;
            if (resposta == 10) { 
                System.out.println(“A resposta é exatamente 10!”);
            } else if (resposta > 10) {
                System.out.println(“A resposta é maior que 10!”);
            } else {
                System.out.println(“A resposta é menor que 10!”);
            }
        }	
    }
#### Switch/case: 
A estrutura condicional switch/case vem como alternativa em momentos em que temos que utilizar múltiplos ifs no código. Múltiplos if/else encadeados tendem a tornar o código muito extenso, pouco legível e com baixo índice de manutenção.<br>
O switch/case testa o valor contido em uma variável, realizando uma comparação com cada uma das opções. Cada uma dessas possíveis opções é delimitada pela instrução case.<br>
Podemos ter quantos casos de análise forem necessários e, quando um dos valores corresponder ao da variável, o código do case correspondente será executado. Caso a variável não corresponda a nenhum dos casos testados, o último bloco será executado, chamado de default (padrão).<br>
A análise de cada caso também precisa ter seu final delimitado. Essa delimitação é feita através da palavra break.
    public class Exemplo {
	
    public static void main(String[] args) {
        int mes = 2;
        switch (mes) {
            case 1:
                System.out.println(“O mês é janeiro”);
                break;
            case 2:
                System.out.println(“O mês é fevereiro”);
                break;
            case 3:
                System.out.println(“O mês é março”);
                break;
            case 4:
                System.out.println(“O mês é abril”);
                break;
            case 5:
                System.out.println(“O mês é maio”);
                break;
            case 6:
                System.out.println(“O mês é junho”);
                break;
            case 7:
                System.out.println(“O mês é julho”);
                break;
            case 8:
                System.out.println(“O mês é agosto”);
                break;
            case 9:
                System.out.println(“O mês é setembro”);
                break;
            case 10:
                System.out.println(“O mês é outubro”);
                break;
            case 11:
                System.out.println(“O mês é novembro”);
                break;
            case 12:
                System.out.println(“O mês é dezembro”);
                break;
            default:
                System.out.println(“Mês inválido”);
                break;
        }
    }
	
}
#### Estruturas de repetição
Estruturas de repetição, também conhecidas como loops (laços), são utilizadas para executar repetidamente uma instrução ou bloco de instrução enquanto determinada condição estiver sendo satisfeita.
<br>
As principais estruturas de repetição na maioria das linguagens são o for e o while.

##### For: 
O for é uma estrutura de repetição na qual seu ciclo será executado por um tempo ou condição pré-determinados e em uma quantidade de vezes que determinamos.

##### O for possui a seguinte estrutura
    for (<variável de controle>, <análise da variável de controle>, <incremento da variável de controle>) {
    // Código a ser executado
    }
Quando utilizamos o for, precisamos de uma variável para auxiliar a controlar a quantidade de repetições a serem executadas. Essa variável é chamada de variável de controle e é declarada no primeiro argumento do for.
<br>
O segundo argumento do for é utilizado para definir até quando o for será executado. Geralmente, trata-se de uma condição booleana em cima da variável de controle.

O terceiro argumento indica o quanto a variável de controle será modificada no final de cada execução dentro do for.
##### Veja o exemplo abaixo:
    public class Exemplo {
	
        public static void main(String[] args) {
            for (int i = 0; i <= 10; i++) {
                System.out.println(“A variável i agora vale “ + i);
            }
        }
    }
A execução desse código causaria a seguinte saída:
A variável i agora vale 0 A variável i agora vale 1 A variável i agora vale 2 A variável i agora vale 3 A variável i agora vale 4 A variável i agora vale 5 A variável i agora vale 6 A variável i agora vale 7 A variável i agora vale 8 A variável i agora vale 9 A variável i agora vale 10

Isso acontece porque:
* A variável de controle, que chamamos de “i”, tem seu valor inicial como 0;
* No segundo bloco, onde escrevemos “i <= 10”, estamos dizendo que o conteúdo do for será executado enquanto o valor de i for menor ou igual a 10;
* Com o terceiro bloco definido como “i++”, estamos dizendo que, no fim de cada execução do for, o conteúdo de “i” será incrementado em 1 unidade. Isso quer dizer que, no fim da primeira execução, i irá de 0 para 1; na segunda execução, irá de 1 para 2, e assim por diante;
* Com isso, o conteúdo do for será executado por 11 vezes, já que o i é iniciado em 0. A saída do código acima mostra que a mensagem foi escrita por 11 vezes, onde o “i” variou de 0 até 10.

Um ponto importante sobre o for é que, por causa da utilização da variável de controle, geralmente ele é utilizado quando sabemos exatamente quantas vezes queremos repetir a execução do trecho de código.

##### While 
O while também é uma estrutura de repetição, assim como o for. A diferença entre ambas é que, enquanto usamos o for quando geralmente conhecemos a quantidade de vezes que o trecho de código deverá ser repetido, nós utilizamos o while quando não sabemos exatamente quantas vezes o código será repetido.

###### O while possui a seguinte estrutura:
    while (<condição>) {
    // Trecho de código a ser repetido
    }

Perceba que a condição para interrupção da repetição do trecho dentro do while se dá através de uma condição booleana.<br>
Abaixo, temos um exemplo do while. Neste exemplo, é pedido ao usuário que tente adivinhar o número. Enquanto o usuário não acerta o número, é pedido para que o usuário digite o valor que ele acha que é o correto. Perceba que nós temos um trecho de código que é sempre repetido, que é o pedido do número para o usuário. Mas, não sabemos exatamente quando o usuário vai acertar este número, ou seja, não sabemos exatamente quantas vezes o trecho de código será repetido. Nessa situação, o while é a estrutura de repetição mais adequada.
##### Exemplo:
    import java.util.Scanner;

    public class Exemplo {
	
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int numero = -1;
        while (numero != 10) { 
        // enquanto a variável não for 10, o trecho de código será repetido
            System.out.println(“Digite um número: “);
            numero = in.nextInt();
            if (numero == 10) {
                System.out.println(“Você acertou!“);
            } else {
                System.out.println(“Você errou!");
                }
            }
        }							   
    }

---

### Vetores
#### O Que São Vetores?
Em Java, Vector é uma classe que implementa uma lista dinâmica de objetos. Semelhante a um array, pode armazenar elementos de qualquer tipo, incluindo instâncias de classes definidas pelo usuário. A principal vantagem dos vetores sobre os arrays tradicionais é sua capacidade de ajustar seu tamanho automaticamente quando elementos são adicionados ou removidos, oferecendo assim uma flexibilidade consideravelmente maior.
#### Como Utilizar Vetores: 
Declaração e Inicialização<br>
##### Um vetor em Java é instanciado da seguinte maneira:
    Vector<E> vetor = new Vector<>();
Aqui, E representa o tipo de elemento que o vetor armazenará. Se nenhum tipo for especificado, o vetor poderá conter objetos de qualquer tipo.

Exemplo Prático: Dias da Semana
Declaração e Inicialização
##### Vamos iniciar declarando um vetor para armazenar os dias da semana:
    Vector<String> diasDaSemana = new Vector<>();
Aqui, especificamos String como o tipo de elemento do vetor, pois os dias da semana são representados por texto.<br>
Adicionando Elementos<br>
##### Para adicionar os dias da semana ao vetor, utilizamos o método add():
    diasDaSemana.add("Segunda-feira");
    diasDaSemana.add("Terça-feira");
    diasDaSemana.add("Quarta-feira");
    diasDaSemana.add("Quinta-feira");
    diasDaSemana.add("Sexta-feira");
    diasDaSemana.add("Sábado");
    diasDaSemana.add("Domingo");

Acesso aos Elementos<br>
##### Para acessar um elemento específico, por exemplo, para obter o terceiro dia da semana, usamos get():
    String terceiroDia = diasDaSemana.get(2); 
* Lembre-se, a indexação começa do 0

Remoção de Elementos<br>
##### Caso queira remover um dia específico, como "Sábado", por exemplo, podemos fazer tanto pelo índice quanto pelo conteúdo:
    // Remoção por conteúdo
    diasDaSemana.remove("Sábado");
    // Remoção por índice, se "Sábado" for o sexto elemento
    diasDaSemana.remove(5); 
Tamanho do Vetor<br>
##### Para verificar quantos dias estão atualmente armazenados no vetor:
    int quantidadeDeDias = diasDaSemana.size();
Melhores Práticas e Considerações<br>
Uso de Generics: 
A utilização de Generics, como visto no exemplo (Vector< String >), assegura que apenas strings sejam adicionadas ao vetor, oferecendo uma camada adicional de segurança de tipo.

---

### Funções
Em Java, as funções são conhecidas como métodos. Eles são blocos de código que realizam uma tarefa específica e podem ser chamados repetidamente. Neste artigo, iremos explorar o conceito, benefícios e como usar funções (ou métodos) em Java.

#### Conceitos Básicos
* Função (Método): Um bloco de código que executa uma tarefa específica.
* Parâmetros: São valores que você pode passar para um método.
* Tipo de Retorno: Indica o tipo de valor que o método vai retornar. 
* Corpo do Método: Onde as instruções são definidas.

#### Benefícios das Funções
* Reutilização de Código: Evita a repetição de código.
* Modularidade: Facilita a leitura e manutenção do código.
* Organização: Separa o código em blocos lógicos.

#### Exemplo Prático
##### Vamos observar o exemplo abaixo que ilustra a utilização de funções em Java:

    public class Funcoes {
    public void Run() {
        dadosPessoais();
        dadosPessoais();
        dadosPessoais();
    }

    public void dadosPessoais() {
        System.out.println("Nome: Nelson Silva");
        System.out.println("Idade: 28");
        System.out.println("Nacionalidade: Portuguesa");
    }
    }

    /*
    Nome: Nelson Silva
    Idade: 28
    Nacionalidade: Portuguesa
    Nome: Nelson Silva
    Idade: 28
    Nacionalidade: Portuguesa
    Nome: Nelson Silva
    Idade: 28
    Nacionalidade: Portuguesa
    */
###### Explorando o Exemplo
No exemplo acima: 
* A função dadosPessoais imprime informações pessoais.
* A função Run invoca a função dadosPessoais três vezes.

##### Tipos de Funções 
* Funções Sem Retorno (void): Não retornam valor.
* Funções com Retorno: Devolvem um valor.
* Funções com Parâmetros: Recebem valores para processar.
* Funções Recursivas: Chamam a si mesmas.

###### Boas Práticas
* Nomeação: Use nomes descritivos e siga as convenções de nomenclatura.
* Tamanho: Mantenha suas funções pequenas e focadas.
* Evite Efeitos Colaterais: Uma função deve fazer uma coisa e fazer bem feito.
* Documentação: Comente seu código e documente suas funções.

##### Conclusão
As funções (ou métodos) são fundamentais na programação Java, permitindo modularidade, reutilização e organização no código. Dominar este conceito é essencial para qualquer desenvolvedor Java.