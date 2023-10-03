### Navegação

1. introdução 
    1. sintaxe 
    2. variável e constante
    3. tipos de dados
- Casting
- Entrada de Dados
- Condições Ternárias
- Estrutura de Repetição (Loops)
- Arrays
    - Métodos
    - Arrays Multidimensionais
- Métodos (Funções)
    - Named Argument
    - Method Overloading

## **Introdução**

Linguagem orientada a objetos criada pela Microsoft. Tem suas raízes da linguagem C.

C# tem um leque gigante de utilizações:

- Aplicações Mobile, Desktop, Web
- Web Services
- Websites
- Jogos
- Base de Dados
- VR

A maneira mais fácil de começar com C# é usando uma IDE.

## Sintaxe

Em síntese, nossa aplicação parecer ter uma estrutura inicial um pouco intimidadora. Mas é mais simples do que se parece.

```csharp
using System;

namespace HelloWorld
{
  class Program
  {
    static void Main(string[] args)
    {
      Console.WriteLine("Hello World!");    
    }
  }
}
```

## Variáveis e Constantes

Variáveis são contêineres para armazenar valores de dados. Esses dados que são definidos de acordo com a palavra chave.

- **`int`** Representa números inteiros.
- **`float`** e **`double`** Representam números de ponto flutuante (com diferentes precisões).
- **`char`**Representa um único caractere Unicode, por exemplo ‘a’ ou ‘B’
- **`bool`** Representa valores booleanos (verdadeiro ou falso).
- **`enum**` Define um conjunto de valores constantes nomeados.

---

### Declarando Variáveis

`tipo nomeDaVariavel = Valor;`

```csharp
int myNum = 5;
double myDoubleNum = 5.99D;
char myLetter = 'D';
bool myBool = true;
string myText = "Hello";

Também somos capazes de declarar mais de uma variável para o mesmo tipo, separando-os por vírgulas:
int x = 5, y = 6, z = 50;
Console.WriteLine(x + y + z);

Também é possível declarar o mesmo valor para várias variáveis em apenas uma linha:
int x, y, z;
x = y = z = 50;
Console.WriteLine(x + y + z);
```

---

### Declarando Constantes

Caso você não queria que o valor que você declarou não seja sobrescrito por outro valor, você pode adicionar a variável como uma constante, o que torna o valor inalterável e apenas para leitura.

**`const** int myNum = 15;`

```csharp
myNum = 20; // error
```

---

### Mostrando Variáveis

Agora que sabemos como declarar nossas variáveis, vamos mostrar para o usuário as informações que armazenamos? Utilizamos o comando `WriteLine()`

Para combinar textos e variável use o caractere `x`

```csharp
string name = "John";
Console.WriteLine("Hello " + name);
```

Para valores numéricos também somos capazes de fazer a mesma coisa.

```csharp
int x = 5;
int y = 6;
Console.WriteLine(x + y); // valor de x + y (11)
```

---

## Tipos de Dados

### **int** (inteiro)

- Tamanho: 4 bytes.
- Armazena números inteiros, positivos ou negativos, na faixa de -2,147,483,648 a 2,147,483,647.
- É amplamente utilizado para representar números inteiros comuns.

```csharp
int myNum = 100000;
Console.WriteLine(myNum);
```

---

### **float** (ponto flutuante)

- Tamanho: 4 bytes.
- Armazena números fracionários com uma precisão de aproximadamente 6 a 7 dígitos decimais.
- É adequado para representar valores com casas decimais, como números reais

```csharp
float myNum = 5.75F;
Console.WriteLine(myNum);
```

---

### **char** (caractere)

- Tamanho: 2 bytes.
- Armazena um único caractere Unicode, como letras, números ou símbolos.
- É usado para representar caracteres individuais e é cercado por aspas simples (' ').

```csharp
char myGrade = 'B';
Console.WriteLine(myGrade);
```

### **long** (inteiro longo)

- Tamanho: 8 bytes.
- Armazena números inteiros longos, na faixa muito ampla de -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807.
- Usado quando números inteiros com uma faixa maior são necessários.

```csharp
long myNum = 15000000000L;
Console.WriteLine(myNum);
```

---

### **double** (ponto flutuante de precisão dupla)

- Tamanho: 8 bytes.
- Armazena números fracionários com alta precisão, aproximadamente 15 dígitos decimais.
- É amplamente usado para cálculos científicos e financeiros.

```csharp
double myNum = 19.99D;
Console.WriteLine(myNum);
```

### **string** (cadeia de caracteres)

- Tamanho: Em geral, 2 bytes por caractere, mas pode variar.
- Armazena uma sequência de caracteres Unicode.
- É usado para representar texto, palavras, frases e é cercado por aspas duplas (" ").

```csharp
string greeting = "Hello World";
Console.WriteLine(greeting);
```

### **bool** (booleano)

- Tamanho: 1 bit (geralmente otimizado para ocupar 1 byte).
- Armazena valores lógicos, ou seja, verdadeiro (true) ou falso (false).
- Usado para tomar decisões condicionais em programas.

```csharp
bool isCSharpFun = true;
bool isFishTasty = false;
Console.WriteLine(isCSharpFun);   // Outputs True
Console.WriteLine(isFishTasty);   // Outputs False
```

---

## Casting

Caso você tenha operações que envolvem dois tipos diferentes de dados

### Conversão Implícita (Automática)

- A conversão implícita acontece quando a linguagem de programação automaticamente converte um valor de um tipo de dados menor para um tipo de dados maior, sem a necessidade de instruções explícitas (por exemplo, uma função ou operador).
- Geralmente, essa conversão envolve a transformação de um tipo de dados menor ou menos preciso em um tipo de dados maior ou mais preciso. Isso é considerado seguro, pois não há perda de informações durante a conversão.
- Aqui está a hierarquia em ordem crescente de tamanho e precisão: **`char`** -> **`int`** -> **`long`** -> **`float`** -> **`double`**.
- Por exemplo, você pode converter implicitamente um **`int`** em um **`double`** porque o **`double`** pode representar todos os valores que um **`int`** pode, além de frações decimais.

```csharp
int myInt = 9;
double myDouble = myInt;       // casting automártico: int para double

Console.WriteLine(myInt);      // Saída 9
Console.WriteLine(myDouble);   // Saída 9
```

### Conversão Explícita (Manual)

- A conversão explícita requer que o programador especifique explicitamente a conversão de um tipo de dados para outro. Isso também é conhecido como type casting.
- Geralmente, essa conversão envolve a transformação de um tipo de dados maior ou mais preciso em um tipo de dados menor ou menos preciso. Essa operação pode resultar em perda de informações, por isso é considerada potencialmente arriscada.
- A conversão explícita é normalmente realizada quando o programador tem confiança de que a conversão é válida e está disposto a aceitar a possível perda de dados.
- A hierarquia de tipos de dados para conversão explícita é o oposto da conversão implícita: **`double`** -> **`float`** -> **`long`** -> **`int`** -> **`char`**.

```csharp
double meuDouble = 5.1;
int meuInt = (int)meuDouble; // 5, Conversão explícita de double para int (perda da parte decimal)
```

## Entrada de Dados

Como você já deve saber, `Console.WriteLine()` é usado para a saída de dados.

## Entrada de Dados

Como você já deve saber, `Console.WriteLine()` é usado para a saída de dados. Agora, vamos aprender como usar o `Console.ReadLine()`.

- Lê a entrada padrão **************até a quebra de linha**************
- O método apenas retorna string. Então não é possível pegar informações de outros tipos de dados, como int, por exemplo. Para fazer isso como aprendemos anteriormente, temos que mudar o tipo de forma manual com o Casting.

```csharp
Console.WriteLine("Bem-vindo! Por favor, digite seu nome:");
string nome = Console.ReadLine();

string saudacao = $"Olá, {nome}! Bem-vindo à nossa casa virtual.";
Console.WriteLine(saudacao);
```

## Condicionais Ternárias

Há também uma abreviação if else, que é conhecida como operador ternário porque consiste em três operandos. Ele pode ser usado para substituir várias linhas de código por uma única linha. Muitas vezes é usado para substituir instruções if else simples:

```csharp
variable = (condition) ? expressionTrue :  expressionFalse;A
```

Ao invés de escrever toda essa linha de código:

```csharp

int time = 20;
if (time < 18) 
{
  Console.WriteLine("Good day.");
} 
else 
{
  Console.WriteLine("Good evening.");
} 
```

Podemos escrever somente:

```csharp
int time = 20;
string result = (time < 18) ? "Good day." : "Good evening.";
Console.WriteLine(result);
```

## Estrutura de Repetição

As estruturas de repetições no C# não são diferentes das demais lógicas das outras linguagens.

### While

```csharp
while (condicao) 
{
	// código
}
```

```csharp
int i = 0;

while (i < 10)
{
  Console.WriteLine(i);

  i++;
}
```

### Do While

O `Do While` é uma variante do loops while. A diferença, é que ele obrigatoriamente executa o código pelo menos uma vez antes de checar se a condição é verdadeira.

```csharp
do {

}
while (condicao);
```

```csharp
int i = 0;

do
{
	Console.WriteLine(i);
	i++;
} while (i < 10);
```

## For

Utilizado quando você sabe exatamente quantas vezes você quer fazer uma repetição em determinado bloco de código.

```csharp
for (declaracao 1; declaracao 2; declaracao 3) 
{
// bloco de código a ser executado
}
```

************************Declaração 1************************ é executado (uma vez) antes da execução do bloco de código

****************Declaração 2**************** define a condição para continuar executando o código

********Declaração 3******** é executado (toda vez) depois do código ser executado

```csharp
for (int i = 0; i < 5; i++) 
{
  Console.WriteLine(i);
}
```

Vale ressaltar que também existe a possibilidade colocar um loop dentro de um outro loop. 

```csharp
// Loop Externo
for (int i = 1; i <= 2; ++i) 
{
  Console.WriteLine("Externo: " + i);  // Executa 2 vezes

  // Loop Interno
  for (int j = 1; j <= 3; j++) 
  {
    Console.WriteLine(" Interno: " + j); // Executa 6 vezes (2 * 3)
  }
}
```

## Foreach

O `Foreach` por sua vez, é usado para iterar por um conjunto de coleções ou sequência de dados (**como arrays, listas, dicionários).** Sua vantagem é uma maneira mais simples e legível de percorrer uma coleção em comparação o `for` convencional.

```csharp
foreach (Tipo elemento in coleção)
{
    // Código a ser executado para cada elemento na coleção
}
```

```csharp
string[] cars = { "Volvo", "BMW", "Ford", "Mazda" };

foreach (string i in cars)
{
	Console.WriteLine(i);
}
```

## Arrays

Coleção de elementos do mesmo tipo, armazenado em posições consecutivas de memórias e sendo acessado por meio do índice.

Declarar um array em C#:

```csharp
tipo[] nomeDoArray;
int[] numeros;
```

Há várias formas de inicializar um Array:

```csharp
// Criar um array de quatro elementos e adicionar
// valores posteriormente
string[] carros = new string[4];

// Criar um array de quatro elementos e adicionar 
// valores imediatamente
string[] carros = new string[4] { "Volvo", "BMW", "Ford", "Mazda" };

// Criar um array de quatro elementos sem especificar o tamanho
string[] carros = new string[] { "Volvo", "BMW", "Ford", "Mazda" };

// Criar um array de quatro elementos, omitindo a palavra-chave
// "new" e sem especificar o tamanho
string[] carros = { "Volvo", "BMW", "Ford", "Mazda" };
```

Para acessar um elemento é acessando pelo índice:

```csharp
int terceiroElemento = numeros[2];
```

Atribuir um novo valor a um elemento específico do array:

```csharp
numeros[2] = 42;
```

### Sort

Esse método classifica os elementos em ordem crescente. Existem vários outros métodos disponíveis para trabalhar com os arrays, como por exemplo Sort, ou Min, Max e Sum ************(System.Linq)************.

```csharp
int[] numeros = { 5, 2, 8, 1, 9 };
Array.Sort(numeros);
```

## Arrays Multidimensionais

Estrutura de dados que permitem armazenar elementos em mais de uma dimensão. É interessante utilizar caso você queira armazenar dados tabulares, como tabela com linhas e colunas.

Para criar um array 2D, é necessário coloca-los em chaves e espera-los por vírgula `(,)` 

```csharp
int[,] numbers = { {1, 4, 2}, {3, 6, 8} };
```

Dessa forma, temos dois arrays distintos dentro de uma única variável. Eles são separados pela vírgula e podem ser elementos distintos, como informações de dois usuários diferentes por exemplo.

na tabela ficaria assim:

|  | COLUMN 0 | COLUMN 1 | COLUMN 2 |
| --- | --- | --- | --- |
| ROW 0 | 1 | 4 | 2 |
| ROW 1 | 3 | 6 | 8 |

### Acessando elementos de um array 2D

Para acessar, devemos especificar dois indexes ao invés de apenas um. O primeiro para detectar o array em si (row) e o segundo para a coluna

```csharp
int[,] numbers = { {1, 4, 2}, {3, 6, 8} };
Console.WriteLine(numbers[0, 2]);
```

### Mudando elementos de um array 2D

A lógica de acessar um Array é a mesma para modificar seus valores:

```csharp
int[,] numbers = { {1, 4, 2}, {3, 6, 8} };
numbers[0, 0] = 5;  // muda o valor de 1 para 5
Console.WriteLine(numbers[0, 0]);
```

## Métodos

Métodos são blocos de conteúdos que apenas rodam quando são chamados. É possível passar dados (parâmetros) dentro desses métodos. São usados para rodar certas ações que são conhecidas como funções. É importante usar métodos para definir um código apenas uma vez e reutilizado várias.

### Criar um método

O método é definido com seu nome seguido de parênteses `()` No C#, existem métodos predefinidos como `Main()`, mas você pode criar seus próprios métodos funções.

```csharp
class Program
{
  static void MeuMetodo() 
  {
    // code to be executed
  }
}
```

`MeuMetodo()` é o nome do método
`static` significa que o método pertence à classe do programa e não um objeto da classe do programa
`void`significa que o método não vai retornar um valor

Para executar um método em C#

Dentro do `Main()`chame o método `MeuMetodo();`

```csharp

static void MyMethod() 
{
  Console.WriteLine("I just got executed!");
}

static void Main(string[] args)
{
  MyMethod();
}

// Saída "Comando executado"
```

No C# os parâmetros funcionam da mesma forma de todas as demais linguagens e também é possível colocar um valor padrão no parâmetro.

### Retornar valor em um método

No C# é necessário colocar o tipo de valor que o método vai retornar, anteriormente vimos que usamos o `void` que indica que não deve retornar nenhum valor.

Métodos que tem algum tipo de retorno diferente de `void` são chamados de Métodos com valor de retorno. Nesses métodos você é obrigado a usar a instrução `return` para retornar um valor do tipo especificado.

```csharp
public int MetodoComValorDeRetorno()
{
    return 42; // Retorna um valor inteiro
}
```

Vamos fazer um exemplo que retorna a soma dos parâmetros no método

```csharp
static int MyMethod(int x, int y) 
{
  return x + y;
}

static void Main(string[] args)
{
  Console.WriteLine(MyMethod(5, 3));
}

// Saída 8 (5 + 3)
```

Agora vamos exemplificar de uma forma divertida? Imagine que você é um chef de cozinha em um restaurante e está criando uma receita para fazer panquecas deliciosas. Cada passo da receita é como um método em C#. Vamos criar um método chamado **`FazerPanquecas`** para tornar isso divertido:

**Passo 1: Decida o Nome do Seu Método**

Assim como você nomearia uma receita, dê um nome ao seu método. Vamos chamá-lo de **`FazerPanquecas`**.

```csharp
public void FazerPanquecas()
{
    // Aqui vamos fazer as panquecas com farinha e leite!
}
```

**Passo 2: Escolha os Ingredientes (Parâmetros)**

Em uma receita, você precisa de ingredientes, certo? No nosso método **`FazerPanquecas`**, precisamos de ingredientes, que são nossos parâmetros. Por exemplo, podemos ter **`farinha`** e **`leite`** como ingredientes para fazer a massa das panquecas. Esses são nossos parâmetros:

```csharp
public void FazerPanquecas(double farinha, double leite)
{
    // Aqui vamos fazer as panquecas com farinha e leite!
}
```

**Passo 3: Instruções da Receita (Código do Método)**

Agora, é hora de adicionar as instruções da receita (código do método). Você começa com uma panela quente e adiciona a massa. Da mesma forma, no nosso método, escrevemos o código para fazer panquecas usando os ingredientes (parâmetros):

```csharp
public void FazerPanquecas(double farinha, double leite)
{
    // Misturar farinha e leite para fazer a massa
    double massa = farinha + leite;

    // Cozinhar a massa em uma frigideira quente
    Console.WriteLine("Coloque a massa na frigideira quente!");

    // E assim por diante...
}
```

**Passo 4: Desfrute das Panquecas (Retorno do Método)**

Depois de seguir as instruções da receita, você obtém panquecas deliciosas. No método, podemos escolher retornar algo. Vamos retornar o sabor das panquecas:

```csharp
public static double FazerPanquecas(double farinha, double leite)
{
    // Misturar farinha e leite para fazer a massa
    double massa = farinha + leite;

    // Cozinhar a massa em uma frigideira quente
    Console.WriteLine("Coloque a massa na frigideira quente!");

    // As panquecas estão prontas!
    return massa;
}
```

**Passo 5: Sirva as Panquecas (Chamada do Método)**

Agora que criamos nosso método **`FazerPanquecas`**, podemos chamá-lo sempre que quisermos fazer panquecas:

```csharp
double sabor = FazerPanquecas(200, 300);
Console.WriteLine("Panquecas prontas: " + sabor);
```

E voilà, você acabou de criar seu método **`FazerPanquecas`** em C#! Agora, sempre que você quiser panquecas, é só chamar o método. A programação é como seguir uma receita divertida, e os métodos são como os passos da sua receita de código. Bom apetite! 🥞😄

### Named Arguments

Permite você chamar um método e especificar de forma explícita o nome dos parâmetros que você deseja passar.

```csharp
void Exemplo(int a, int b)
{
    // Código do método aqui
}

// Chama o método com argumentos nomeados
Exemplo(b: 10, a: 5);
```

Isso torna claro o valor que passamos no parâmetro sem necessariamente coloca-los em ordem.

### Método Overloading

É quando você cria vários métodos com o mesmo nome em uma classe, mas com diferentes **********tipos********** ou ****números**** de argumentos. Isso permite que você use o mesmo nome do método para fazer coisas diferentes dependendo do argumento que você usa ao chamar.

Aqui está um exemplo simples de sobrecarga de método:

```csharp
class Calculadora
{
    public int Somar(int a, int b)
    {
        return a + b;
    }

    public double Somar(double a, double b)
    {
        return a + b;
    }
}

Calculadora calculadora = new Calculadora();
// Chamar o método com inteiros
int resultadoInt = calculadora.Somar(5, 3);

// Chamar o método com doubles
double resultadoDouble = calculadora.Somar(3.5, 2.7); 
```

