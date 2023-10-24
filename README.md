# Dia 1 de Estudos

### Como criar uma variável em JavaScript

Você pode criar variáveis em JavaScript da seguinte maneira:

```javascript
let firstName = 'Vinicius';
let lastName = 'Buarque';
let fullName = firstName + ' ' + lastName;
let email = 'viniciusbuarque17@gmail.com';
let age = 23;
let dateOfBirth = '31/05/2000';

console.log('Primeiro nome: ' + firstName);
console.log('Segundo nome: ' + lastName);
console.log('Nome completo: ' + fullName);
console.log('Email: ' + email);
console.log('Idade: ' + age);
console.log('Data de nascimento: ' + dateOfBirth);
```

### Tipos de variaveis em JavaScript

Variável `const` não pode ser alterada, pois ela precisa ser constante, um valor que não pode ser alterado.

```javascript
const itemPrice = 30;
```

Se caso eu tentar modificar o valor da minha variavel const irá me retornar um erro:

```javascript
itemPrice = 40;
console.log('Preço do item: ' + itemPrice);

console: Uncaught TypeError: Assignment to constant variable
```

Variavel `let` é uma variavel que pode ser alterada, diferente da const.

```javascript
let itemPrice = 30;
itemPrice = 20;
console.log('Preço do item: ' + itemPrice);

console: 'Preço do item:' 20
```

Variavel `var` é uma variavel que pode ser alterada, diferente da const.

```javascript
var itemPrice = 30;
itemPrice = 20; 
console.log('Preço do item: ' + itemPrice);

console: 'Preço do item:' 20
```

### Resumo das variaveis

Variável `var`

- **Escopo de Função:** As variáveis declaradas com var têm escopo de função, o que significa que elas são visíveis em toda a função em que são declaradas, independentemente de onde dentro da função são definidas.

- **Hoisting:** Variáveis var são "içadas" (hoisted), o que significa que são movidas para o topo do escopo da função durante a fase de compilação. Isso significa que você pode acessar uma variável var antes de declará-la no código, mas seu valor será undefined.

- **Reatribuição:** Variáveis var podem ser reatribuídas em qualquer lugar no escopo da função em que foram declaradas.

Variável `let`

- **Bloco de Escopo:** As variáveis declaradas com let têm escopo de bloco, o que significa que são visíveis apenas dentro do bloco de código em que são declaradas. Blocos de código são delimitados por chaves {}.

- **Hoisting:** Assim como as variáveis var, as variáveis let também são içadas, mas diferentemente das variáveis var, elas não são inicializadas com undefined. Tentar acessar uma variável let antes de declará-la resultará em um erro de "temporal dead zone".

- **Reatribuição:** Variáveis let podem ser reatribuídas dentro de seu escopo.

Variável ```const```
- **Bloco de Escopo:** Assim como as variáveis let, as variáveis const também têm escopo de bloco e são visíveis apenas dentro do bloco em que são declaradas.

- **Hoisting:** Variáveis const também são içadas, mas, como as variáveis let, não são inicializadas com undefined.

- **Imutabilidade:** Variáveis const não podem ser reatribuídas após a atribuição inicial. No entanto, o valor para o qual elas foram atribuídas pode ser mutável, por exemplo, se você atribuir um objeto a uma variável const, ainda poderá modificar as propriedades desse objeto.

- `var` tem escopo de função, é içada e pode ser reatribuída;

- `let` tem escopo de bloco, é içada e pode ser reatribuída;

- `const` tem escopo de bloco, é içada e não pode ser reatribuída, mas seu valor pode ser mutável em casos de objetos.

> OBS: A recomendação atual é usar let e const em vez de var, a menos que haja um motivo específico para usar var.

### Devo ou não devo utilizar o ponto e virgula no final de cada linha de código?

- **ASI**: *Automatic Semicolon Insertion* (Inserção automatica de ponto e virgula)

- O javascript insere automaticamente o ponto e virgula no final de cada linha de código. Porém é uma boa pratica sempre colocar o ponto e virgula no final de cada linha de código.


### Tipos de dados em JavaScript

- **Primitivo**: String, Number, Boolean, Undefined, Null, Symbol e BigInt;

```javascript
let firstName = 'Vinicius'; //-> string
let age = 23; //-> number
let isApproved = true; //-> boolean
let lastName; //-> undefined
let selectedColor = null; //-> null
```

Javascript é uma linguagem de programação dinamica, ou seja, não precisamos definir o tipo de dado que a variavel irá receber, o proprio javascript irá definir o tipo de dado que a variavel irá receber.

```javascript
let firstName = 'Vinicius';
```

Se fosse estatico teriamos que definir o tipo de dado que a variavel irá receber.

```javascript
let string firstName = 'Vinicius';
```

### Como eu posso saber o tipo de dado que a minha variavel está recebendo? podemos utilizar o typeof para saber o tipo de dado que a nossa variavel está recebendo.

```javascript
console.log(typeof firstName); //-> string
console.log(typeof age); //-> number
console.log(typeof isApproved); //-> boolean
console.log(typeof lastName); //-> undefined
console.log(typeof selectedColor); //-> null
```

- **Referência**: Object, Array, Function

**Objeto** -> seria um grupo de informação referente a uma coisa só, por exemplo, um objeto carro, um objeto caneta, um objeto pessoa, etc.

```javascript	
let pen = {
    itemName: 'Pen',
    itemPrice: 3,
    itemAvailable: true,
    itemColor: 'Blue'
}

console.log(pen);

console: 
{
    itemName: "Pen",
    itemPrice: 3,
    itemAvailable: true,
    itemColor: "Blue"
}
```

**Array** -> é um agrupamento de dados organizados por indices (index), por exemplo, um array de cores, um array de numeros, etc.

```javascript
let colors = ['Blue', 'Green', 'Yellow', 'Red'];
console.log(colors);

console: ["Blue", "Green", "Yellow", "Red"]
```

Dentro de uma array os valores são organizados por indices ou chamados index, no caso o index se inicia em 0 e vai até o ultimo valor da array.

```javascript
console.log(colors[0]); //-> Blue
console.log(colors[1]); //-> Green
console.log(colors[2]); //-> Yellow
console.log(colors[3]); //-> Red
```

**Function** -> É um grupo de tarefas na qual eu posso criar e reutilizar em qualquer parte do meu código.

```javascript
function saleStatus() {
    console.log('Sale approved');
}
```
Para executar a função eu preciso chamar ela, ou seja, eu preciso invocar ela.

```javascript
saleStatus();
```

Podemos deixar a função mais dinamica, ou seja, podemos passar parametros para a função.

```javascript
function saleStatus(itemName, total) {
    console.log('Sale approved: ' + itemName + ' | ' + 'Total amount: ' + total);
}

saleStatus('Pen', 30);

console: Sale approved: Pen | Total amount: 30
```

**saleStatus(itemName)** -> ``itemName`` é um parametro da minha função, ou seja, é um valor que eu posso passar para a minha função.

**saleStatus('Pen')** -> ``'Pen'`` é um argumento da minha função, ou seja, é um valor que eu passo para o parametro da minha função.

## Função com calculo

```javascript
function percentage10(price) {
     return price - (price * 10 / 100)
}

 console.log(percentage10(30))
```

> OBS: Para eu poder retornar algo que minha função esta fazendo eu preciso utilizar o return, pois o return é o que vai me retornar o valor que eu quero, no qual o return armazena o valor para depois eu poder utilizar ele.

## Final do dia 1 de estudos

# Dia 2 de Estudos

> Em breve