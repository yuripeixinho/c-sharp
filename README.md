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
