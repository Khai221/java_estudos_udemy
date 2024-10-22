# java_estudos_udemy

## TIPOS DE DADOS
### Tipos Primitivos
São os tipos de dados básicos em Java, que armazenam valores simples e não são objetos. Existem 8 tipos primitivos:
1 - boolean: Pode armazenar dois valores, true ou false.
2 - byte: Armazena números inteiros de 8 bits com sinal. Intervalo: de -128 a 127.
3 - short: Armazena números inteiros de 16 bits com sinal. Intervalo: de -32.768 a 32.767.
4 - int: Armazena números inteiros de 32 bits com sinal. Intervalo: de -2^31 a 2^31-1 (aproximadamente de -2 bilhões a 2 bilhões).
5 - long: Armazena números inteiros de 64 bits com sinal. Intervalo: de -2^63 a 2^63-1.
6 - float: Armazena números de ponto flutuante (com casas decimais) de 32 bits. Usado para economizar memória em grandes arrays de números flutuantes. Exemplo: 3.4028235e38f (sufixo "f" indica float).
7 - double: Armazena números de ponto flutuante de 64 bits com maior precisão. Exemplo: 1.7976931348623157e308.
8 - char: Armazena um único caractere de 16 bits (Unicode), permitindo valores de '\u0000' até '\uffff' (ou seja, de 0 a 65.535). Exemplo: 'A'.
### Tipos de Referência
Estes tipos armazenam a referência a um objeto. Incluem classes, interfaces, arrays e tipos enumerados (enums). Exemplos de tipos de referência incluem:
1 - Classes: Exemplo: String, Integer, ArrayList.
2 - Arrays: Exemplo: int[], String[].
3 - Interfaces: Exemplo: List, Runnable.
4 - Enums: Conjuntos de constantes que representam valores fixos. Exemplo: enum Dia { SEGUNDA, TERCA, QUARTA }.
Os tipos primitivos não possuem métodos associados, enquanto os tipos de referência podem ter métodos e podem ser manipulados através de referências a objetos.

## EXIBINDO DADOS NA TELA
### Diferença entre print, println e printf
Em Java, os métodos print, println e printf são usados para exibir informações no console. Abaixo está uma explicação detalhada sobre a diferença entre esses métodos, com foco especial no uso do printf.
1 - print: O método print exibe o texto passado como argumento na saída padrão (console), mas não adiciona uma nova linha ao final da impressão. Isso significa que a próxima saída será exibida na mesma linha.
Exemplo:
System.out.print("Hello, ");
System.out.print("world!");

Saída:
Hello, world!

2 - println: O método println também exibe o texto passado como argumento, mas adiciona uma nova linha ao final. Isso significa que a próxima saída será exibida em uma nova linha.
Exemplo:
System.out.println("Hello, ");
System.out.println("world!");

Saída:
Hello, 
world!

3 - printf: O método printf permite formatar a saída com base em uma string de formato. Ele é útil quando você precisa exibir variáveis em um formato específico, como limitar casas decimais ou alinhar texto. Ele não adiciona automaticamente uma nova linha ao final (a menos que seja incluído o "%n" ou "\n" na string de formato).
Exemplo (Utilizando dos tipos de dados e a string formatada):
public static void main(String[] args) {
    String product1 = "Computer";
    String product2 = "Office desk";
      
    int age = 30;
    int code = 5290;
    char gender = 'F';
      
    double price1 = 2100.0;
    double price2 = 650.50;
    double measure = 53.234567;
      
    Uso do printf para exibir informações formatadas
    System.out.printf("Products: %s, which price is $ %.2f %n%s, which price is $ %.2f%n", product1, price1, product2, price2);
    System.out.printf("Record: %d years old, code %d and gender: %s%n", age, code, gender);
    System.out.printf("Measue with eight decimal places: %.8f%n", measure);
    System.out.printf("Rouded (three decimal places): %.3f%n", measure);
    System.out.printf("US decimal point: %.3f", measure);
}

O printf permite a inserção de variáveis no meio do texto, usando "placeholders" que são substituídos pelos valores das variáveis passadas como argumento. A seguir, os placeholders utilizados no exemplo e sua função:
%s: Usado para exibir Strings. exemplo: System.out.printf("Products: %s", product1);
%d: Usado para exibir números inteiros (inteiros decimais). exemplo: System.out.printf("Record: %d years old", age);
%f: Usado para exibir números de ponto flutuante (double ou float). exemplo: System.out.printf("which price is $ %.2f", price1);
%n: Usado para quebra de linha (uma forma mais segura de inserir nova linha em diferentes sistemas operacionais). exemplo: System.out.printf("%n%s", product2);

## ENTRADA DE DADOS
### Entrada de Dados em Java com a Classe Scanner
Em Java, a classe Scanner permite a leitura de dados inseridos pelo usuário no console. No exemplo a seguir, o programa solicita que o usuário insira uma string, um número inteiro e um número de ponto flutuante (double), e em seguida exibe esses valores.
public static void main(String[] args) {
    
    Locale.setDefault(Locale.US); // Configura o padrão de localização para usar o ponto (.) como separador decimal. (o sistema nao esta configurado para usar o . antes de fazer essa configuração pq o idioma do pc esta em português como ,)
    Scanner sc = new Scanner(System.in); // Cria um objeto Scanner para capturar entradas do teclado.
    
    String x;  // Declaração de variável para armazenar uma string
    int y;     // Declaração de variável para armazenar um número inteiro
    double z;  // Declaração de variável para armazenar um número de ponto flutuante
    
    // Lê os valores inseridos pelo usuário
    x = sc.next();          // Lê uma string
    y = sc.nextInt();       // Lê um número inteiro
    z = sc.nextDouble();    // Lê um número de ponto flutuante (double)
    
    // Exibe os dados digitados
    System.out.println("Dados digitados");
    System.out.printf("Valor string: %s, int: %d, double: %.2f", x, y, z);
    
    sc.close(); // Fecha o objeto Scanner para liberar os recursos
}
Principais Métodos next do Scanner
next()	        String (próximo token)	       String str = sc.next();
nextLine()	     String (linha inteira)	       String line = sc.nextLine();
nextInt()	       int	                         int number = sc.nextInt();
nextDouble()	   double	                       double value = sc.nextDouble();
nextFloat()	     float	                       float value = sc.nextFloat();
nextLong()	     long	                         long value = sc.nextLong();
nextShort()	     short	                       short value = sc.nextShort();
nextByte()	     byte	                         byte value = sc.nextByte();
nextBoolean()	   boolean	                     boolean value = sc.nextBoolean();
Observações Importantes:
Delimitadores: Por padrão, o Scanner usa espaços em branco (espaços, tabulações, quebras de linha) como delimitadores entre os tokens.
Erros: Se o usuário inserir um valor incompatível com o tipo esperado, uma exceção, como InputMismatchException, será lançada. Exemplo: inserir uma string quando o programa espera um número inteiro.












