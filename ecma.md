---
marp: true
theme: gaia
---

# ECMAScript e JavaScript

Isabela Moreira

![bg 60% left](https://cdn.worldvectorlogo.com/logos/es6.svg)

---

# O que é a ECMA? 

- Acrônimo para **Associação Européia dos Fabricantes de Computadores**;

- Orgão fundado em 1961 dedicado à padronização de sistemas de informação.

- Desde 1994 passou a se denominar **Ecma International** para refletir suas atividades internacionais.

---
# Qual a diferença entre ECMAScript e JavaScript?

- Javascript surge na metade da década de 90 desenvolvido pelo programador **Brendan Eich**, empregado da Netscape 

- Vista como promissora, foi assim nomeada a fim de que pudesse usufruir do sucesso que a linguagem Java estava desfrutando  

- Após a criação do Javascript, a Netscape o enviou para a ECMA Internacional que padronizou a linguagem e batizou esta versão de **ECMAScript**.

---
# ES6

Em 2015 houve o lançamento do ES6 e com isso, 
surgiram inovações como: 
- Funções **arrow**;
- Funções **map, filter e reduce**;
- Funções **some** e **every**;
- Função **find**;
- Comandos **const** e **let**, entre outros;
 
 ---


Mudança que esta versão trouxe:



 - **Default Parameters**;




 - **Template Strings**;




 - **Destructuring**;



---
# Default Parameters
Este recurso permite que parâmetros sejam definidos antecipadamente. Caso o desenvolvedor esqueça de escrever um parâmetro, não será retornado um erro de **undefined** pois os parametros estaram definidos por padrão. 

```javascript
    function say(message='Hi') {
    console.log(message);
    }

    say(); // 'Hi'
    say('Hello') // 'Hello'

```


---
# Template Strings
Elas possibilitam concatenações sem que se façam necessário o operador **+** e que se possa usar uma variável dentro de uma string.  

Na antiga sintaxe, esta função seria escrito :
```javascript
    const myFunction(name,age){
        return 'Hi' + name + '.Your age is '+ age + 'years old.'  
    }
    console.log(myFunction('Maria', 27))
```
---



Na sintaxe do ES6:
```javascript
    const myFunction = (name,age)=>{
        return `Hi ${name}. Your age is ${age} years old.`
    }
    console.log(myFunction('Maria', 27))

```


---
# Destructuring

A sintaxe Destructuring Assignment é uma expressão Javascript que permite extrair dados de arrays ou objetos em variáveis distintas.


---
Considere a função a seguir:
```javascript
function TodoStore(args){
  const helper = args.helper;
  const dataAccess = args.dataAccess;
  const userStore = args.userStore;
}

```
Com o recurso destructuring, ela pode ser escrita assim ...
```javascript
    function TodoStore(args){
   const { 
      helper, 
      dataAccess, 
      userStore } = args;
}
```

---

Ou ainda assim
```javascript
function TodoStore({ helper, dataAccess, userStore }){}
```
A chamada da função se dá desta forma:
```javascript
    TodoStore({ 
    helper: {}, 
    dataAccess: {}, 
    userStore: {} 
    });
```

---
# O que é *strict mode*?
- **"use strict"** define que código JavaScript deverá ser executado apenas em **"strict mode"**. Seu lançamento gerou
várias mudanças nas semânticas normais do JavaScript, eliminando alguns erros silenciosos do JavaScript que impedem otimização do código. Um exemplo de pŕaticas que mudaram é que não se pode usar  variáveis não-declaradas.

- Strict mode é declarado escrevendo "use strict" no início da função ou do script.
---
# O que é *Hoisting*?
**Hoisting** significa içamento em português.

- Quando compilado o código Javascript, todas as declarações de variáveis e funções são levadas ao topo do escopo local ou global. Essa elevação é chamada hoisting. 
- A mudança nas declarações de variável e função são colocadas na memória durante a fase de *compilação*, mas permanecem exatamente onde você as digitou no seu código.
---
- Uma vantagem em colocar declarações de função na memória antes de executar qualquer segmento de código é que ele permite que você use uma função antes de declará-la em seu código.
- Entretanto, uma coisa importante a notar é que a única coisa que é movida para o topo são as declarações de variáveis, não o valor real delas.
```javascript
console.log(num); 
var num;
num = 6;

// Retorna undefined

num = 6;
console.log(num); 
var num;

// retorna 6
```
---
#  Qual a diferença de `var`, `let` e `const`?
**var**  era a forma padrão de se declarar variáveis até o ES5, chamadas de variáveis de escopo de funções.

**const** é um novo recurso no ES6 para a declaração de variáveis. **const** é mais poderoso que **var**. Uma vez usada,a variável não pode ser reatribuida. É uma variável imutável exceto quando utilizadas com objetos.
**let** é uma forma de se declarar variáveis sendo possível reatribuílas posteriormente e assim, ganhar novo valor. 

---
![bg 70%](data:image/png;base64,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)

---
#  Qual a diferença entre `for`, `forEach` e `for.. of` ?
**for**: repetição até que a condição falsa seja atingida
```javascript
for ([expressão inicial]; [condição]; [incremento])  {          
       executa comando;
}
```
---
**forEach** executa uma função passada com parâmetro para cada elemento de uma array
```javascript
array.forEach(function)                 
```
**for.. of** percorre os valores de objetos iterativos (array, map, etc)
```javascript
let myArray = [2,3,4];
for(let value of myArray){
    console.log(value)
}
// 2,3,4
```       


---
# Referências 
- https://kenzie.com.br/blog/ecmascript-6/
- https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Template_literals
- https://www.freecodecamp.org/news/write-less-do-more-with-javascript-es6-5fd4a8e50ee2/
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment
- https://developer.mozilla.org/pt-BR/docs/Glossary/Hoisting
- https://imasters.com.br/front-end/diferenca-entre-for-of-e-for-in
- https://medium.com/@joaovictorpsantos/qual-a-diferen%C3%A7a-entre-for-in-for-of-e-foreach-no-javascript-7af6f6a56eea

