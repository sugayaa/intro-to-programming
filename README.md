# intro-to-programming

Vou usar o C++ ao invés de C por ser mais alto nível. Por alto nível entenda que o código faz algumas coisas de forma automática, sem que você tenha que se preocupar com alguns detalhes.

Bom, de ante-mão é necessário saber que vamos escrever o código em texto, e após isso, "compilar" o arquivo texto criado, compilar é o ato de transformar o nosso código texto em executável. Há vários detalhes que estou deixando de fora, mas vamos lá.

Vamos criar nosso primeiro código.

```C
#include<iostream>

int main(){

    return 0;
}
```

Em essência esse é o corpo mínimo de um código em C++. Ali dentro das chaves há o texto _return 0_ mas ele não é estritamente necessário. É apenas um jeito do programa falar para o sistema operacional que ele terminou de executar sem nenhum erro.

### O que é aquela linha estranha no começo ? 

É um comando especial para incluir comandos prontos. Em especial iostream é a responsável por incluir os comandas de entrada e saída no programa. Entenda entrada e saída como: entrada, inserir alguma informação no programa usando o teclado, e saída como, mostrar alguma informação na tela.

### O que é entrada e saída ?

É a maneira de comunicação que temos com o programa, entrada é quando fornecemos alguma informação a ele, queremos passar um número, um texto, entre outros. E a saída é como o programa se comunica com a gente, nos dá uma resposta, vai ser responsável por escrever no nosso monitor.

### O que é esse int main() e por que essas chaves ao redor ?

Int main é a função principal de todo programa em C ou C++. Toda vez que o programa for executado, a _função_ int main será o ponto inicial, mesmo que haja código escrito antes dela, assim que iniciado o programa, a execução começará na função int main.

As chaves delimitam um escopo, um trecho. Então tudo que estiver entre aquelas duas chaves será executado em ordem quando o programa iniciar.

P.S.: É importante ressaltar a ordem que o programa é executado, sempre de cima para baixo, uma instrução após a outra, a menos que explicitamente indicado para seguir outro fluxo, com outros comandos que vamos ver mais para frente.


## Mas onde escrevo esse código ? Como compilo ? 

## Tratar sobre IDE's

Nosso programa não fez nada certo?

Simplesmente porque não falamos para ele fazer nada, vê como nosso código até agora só tem o return? return 0 só serve para indicar que nosso programa executou sem erros.

Vamos tratar de entrada e saída agora.

Os operadores de entrada e saída do C++ são:

* cin
* cout

Conhecidos como _consolein_, _consoleout_.
Seguindo a tradição de todo programa e programador, vamos dar o nosso Olá para o mundo.

Modifique seu código para o seguinte:

```C
#include<iostream>
using namespace std;

int main(){
    cout << "Hello World!" << endl;
    return 0;
}
```

Pouca diferença, mas o que é esse namespace std, e como funciona o cout?

O cin e o cout (endl também) pertencem a uma classe de comandos chamada std, de standard, caso não definissemos esse namespace a todo momento que desejássemos escrever, cin ou cout, teríamos de escrever desta forma:

```C
std::cin
std::cout
```

Ok, cin e cout agora, usamos o cout no nosso exemplo, então vamos começar por ele:

```C
cout << "Hello" ;
```

O que está acontecendo? 
Estamos escrevendo o texto "Hello" em nosso monitor. Bacana, mas há outras coisas importantes a saber, o cout usa o separador _<<_ para delimitar texto de números ou variáveis. Ainda não cheguei em variáveis, mas vamos estar lá em breve.

```C
cout << "Este é o numero três (" << 3 << ")" << endl;
```
Sugiro que deem uma brincada para treinar e verificar as dificuldades nessas separações.

E podemos fazer isso quantas vezes desejarmos. Só precisamos lembrar que precisamos separar texto de outras coisas. No entanto o cout, como o cin, sempre terá esse separador no começo, esse é necessário sempre.

Antes de aprendermos sobre o cin, vamos aprender sobre variáveis.

## Variáveis

Variáveis são um pedaço de memória para o programador guardar informação. Essa informação só será mantida enquanto o programa estiver rodando. Na memória RAM para os interessados por hardware. Diferente de escrever num arquivo em um HD ou SSD por exemplo.

Tão importante como sua definição, é seu tipo. Existem diferentes tipos de variáveis e eles que vão definir o que deverá ser guardado em cada uma. Para usarmos uma variável em nosso programa precisamos escrever o tipo e seu nome, que servirá de identificador para quando quisermos recuperar o que guardamos. Algo assim:

```C
int minha_primeira_variavel;
```

Assim definimos uma variável que tem como tipo inteiro e seu identificador é minha_primeira_variavel. Os identificadores não podem começar com números e elas não podem ter caracteres especiais.
Lembre-se sempre que uma variável em C/C++ precisa ser declarada antes de ser usada. Declarar é o nome que damos a essa associação tipo com identificador.

Os tipos mais comuns em C++ são:

* int - inteiro - [−2,147,483,647, +2,147,483,647]
* long long int - inteiro com 64 bits - [−9,223,372,036,854,775,807, +9,223,372,036,854,775,807]
* double - valor decimal ex.: 3.1415926535897932384626433
* char - caractere - "a", "b", "c"
* string - texto ex.: "Olá Mundo!"

Variáveis são como caixinhas guardando um valor para ser usado mais tarde, e caixinhas essas que podem ter seus valores acessados e alterados.

Para brincar:

```C
#include<iostream>
using namespace std;

int main(){
    int tres = 3;
    cout << "Este é o numero três (" << tres << ")" << endl;
}
```

Alcançamos o mesmo resultado do último código desta vez usando uma variável.
E a parte bacana das variáveis é que elas não precisam ter o mesmo valor o programa inteiro, e nem precisamos saber o valor dela em específico no momento que estamos escrevendo.

```C
#include<iostream>
using namespace std;

int main(){
    int resultado = 3+4-8+4-48+178-39+8+8-478+302-147;
    cout << "Este não é o numero três (" << resultado << ")" << endl;
}
```


### Atribuição

Podemos atribuir valor a uma variável assim que a declaramos, exemplo:

```C
int contador = 0;
```

Ou depois, exemplo:

```C
int contador;
contador = 0;
```

Essa operação denotada com o símbolo de igual é chamada de atribuição e estamos definindo que o pedaço de memória identificado por aquele nome terá o valor a direita. No caso a variável memória identificada pelo nome contador, receberá o valor 0.
P.S.: É um ponto importante a destacar que tudo que está a direita do operador de atribuição será resolvido antes da atribuição.

Exemplos:
```C
int inicial = 3 + 2;
```

O programa executará a conta _3+2_ que resultará em _5_ então ele guardará 5 em inicial, e não a conta.

Ou ainda, um exemplo mais difícil.

```C
int inicial = 5;
inicial = inicial + 2;
```

Qual o valor de inicial após a execução das duas linhas? Esse tipo de código é possível? Usar uma variável para definir o valor dela mesma?

Lembre da regra da resolução da direita primeiro. Qual valor inicial tinha antes de entrar naquela linha? 5? Então o programa resolverá primeiro, 5+2, e depois atribuirá o resultado, 7, dentro de inicial.

Então a resposta é: inicial conterá o valor 7.

## Entrada de Dados

### cin

O cin serve para ler valores que o usuário do programa fornecer. Mas não faria sentido ler algo, se não fossemos guardar, por isso passamos por variáveis antes. Diferente do cout, ele usa _>>_, ao invés de _<<_, eu gosto de pensar como, se cin estamos lendo, estamos jogando valores para dentro do programa, então apontamos para dentro _>>_, como cout estamos levando valores do programa para fora então usamos _<<_, apontando para fora. Mas também não há problema em trocar, o compilador vai reclamar caso algo estranho aconteça.

Mão na massa:

```C
#include<iostream>
using namespace std;

int main(){
    float valor_decimal;
    cin >> valor_decimal;
    cout << "Valor decimal fornecido é: " << valor_decimal << endl;

    return 0;
}
```

P.S.: Nas linguagens de programação em geral usamos valores decimais como nos EUA, o caracter _._ é usado como a vírgula aqui no Brasil. E a vírgula(_,_) simplesmente não é usada como maneira de delimitar valores decimais.

## Alterando o fluxo do programa

### Condicionais: _if_ e _else_

Quando programamos em _C++_, o código inteiro é executado de forma sequencial, começando na porção _main()_, toda a instrução é executada uma após a outra até o _return_, consequência disso é que ainda não é possível realizar decisões ou repetir instruções, _"como assim?"_ você pode me perguntar, vamos lá.

Todas as decisões que podemos tomar, são antes do código começar a ser executado, enquanto escrevemos, suponhamos que eu queira fazer um programa que leia um valor inteiro e imprima na tela se o valor é negativo ou positivo, parece simples não? Como podemos fazer isso com o que vimos até agora?

Para esse exato propósito existem as instruções condicionais. Trazendo para a linguagem natural, podemos escrevê-las como:

<pre><code><b>se</b> uma condição for verdadeira:
	realizamos uma instrução.
<b>caso contrário</b>:
	realizamos outra.
</code></pre>

A parte do _caso contrário_ pode ser suprimida, dessa forma podemos ter apenas o _caso_.

<pre><code><b>se</b> uma condição for verdadeira:
	realizamos uma instrução.
...prosseguimos com o resto do código...
</code></pre>

 Apesar do código estar escrito em sequência uma porção do código pode ser pulado, sem que sua execução ocorra. Vou mostrar um exemplo já escrevendo o código em C++.
 
```C
#include<iostream>
using namespace std;

int main(){
    int numero = 10;
    
    if (numero == 10){
    	cout << "O valor de numero é 10" << endl;
    }

    return 0;
}
```

Ao executarmos nosso programa a saída, texto impresso na tela, será:

<pre><code>
O valor de numero é 10
</code></pre>

Agora experimente mudar a linha,

```C
	int numero = 10;
```

para, 

```C
	int numero = 9;
```

Não aconteceu nada certo? 
Essa é a função dos concidicionais, fazer um seletor, que dirá se aquela ou outra porção de código deve ser executada.
Vamos testar outros exemplos agora:

```C
#include<iostream>
using namespace std;

int main(){
    int numero = 9;
    
    if (numero == 10){
    	cout << "O valor de numero é 10" << endl;
    }else{
    	cout << "Esse número não é 10" << endl;
    }

    return 0;
}
```

E aí, captou?
"Tá, beleza, entendi, mas por que o ==, ao invés do =, como isso funciona?"
Então vamos partir para os comparadores.

### Comparadores
Comparadores são usados para obtermos valores verdade, apesar da expressão meio estranha é apenas, Verdadeiro ou Falso. Por exemplo, 3 é menor do que 4? 

Em essência é isso que estamos fazendo, essa expressão no caso é verdadeira, mas e caso escrevéssemos 3 maior que 4, isso é verdade?
Acho que não. Logo, quando escrevermos algo assim no nosso código, a expressão será trocado pra falso.

No entanto escrever expressões com dois valores constantes assim, 3 e 4, não faz muito sentido. Usualmente utilizamos esses comparadores com variáveis, exemplo,

```C
#include<iostream>

int main(){
	int numero;
	cin >> numero;
	if (numero == 10){
		cout << "O valor digitado foi 10" << endl;
	}else{
		cout << "O valor digitado não foi 10" << endl;
	}
	
	return 0;
}
```

Você deve ter percebido que usamos o sinal = (igual), uma vez para realizarmos atribuições anteriormente. Quando usamos == (igual igual), estamos fazendo uma comparação.
Outras comparações,

Grafia  | Significado           |
---     | ---                   |
<       | menor que             |
>       | maior que             |
<=      | menor ou igual que    |
>=      | maior ou igual que    |
==      | igual a               |
!=      | diferente de          |
!       | negação               |

O símbolo de negação é o menos comum, mas muito poderoso, podemos juntá-lo com muita coisa. Não há motivo para, mas podemos fazer algo assim:

```C
!(numero > 10)
```

Se o número não for maior que 10, toda essa expressão será transformada em verdadeiro.

**Bugando o cérebro**: perceba que,

```C
(!(numero > 10))
```

é a mesma coisa que:

```C
(numero <= 10)
```
