Generics são para tipos o que valores são para argumentos de função — eles são uma maneira de dizer aos nossos componentes (funções, classes ou interfaces) o tipo que queremos usar quando executarmos esse pedaço de código, da mesma forma como dizemos a uma função quais valores usar como argumentos quando nós a executamos. [Fonte](https://oieduardorabelo.medium.com/typescript-entendendo-generics-por-completo-40a372aeea5)

Os genéricos nos permitem escrever uma função que pode assumir qualquer tipo e transformar nossa função com base nesse tipo. Outra maneira de pensar em genéricos é que eles transformam uma função com base no tipo de dados que você passa para ela.

```ts
function identity <T>(value: T) {  
	return value;  
}  
  
console.log(identity<Number>(1)) // 1
```

### Genéricos para Classes e Interfaces
Interfaces e classes funcionam exatamente da mesma maneira. No caso deles, colocamos os tipos logo após o nome da nossa interface ou nome da classe.

```ts
interface GenericInterface<U> {  
	value: U  
	getIdentity: () => U  
}  
  
class IdentityClass<T> implements GenericInterface<T> {  
	value: T  
	
	constructor(value: T) {  
		this.value = value  
	}  
	
	getIdentity () : T {  
		return this.value  
	}  
}  
  
const myNumberClass = new IdentityClass<Number>(1)  
console.log(myNumberClass.getIdentity()) // 1  
  
const myStringClass = new IdentityClass<string>("Hello!")  
console.log(myStringClass.getIdentity()) // Hello!
```

### Caso de uso prático: além dos tipos primitivos
O poder real dos genéricos vem quando temos tipos ou classes personalizadas que formam uma árvore de herança.

Considere o exemplo clássico de herança de um carro. Nós temos uma classe base `Car` que é usada como base para `Truck` e `Vespa`. Em seguida, escrevemos uma função de utilidade `washCar` que recebe uma instância genérica `Car` e depois a retorna.

```ts
class Car {  
	label: string = 'Generic Car'; 
	numWheels: Number = 4;
	horn() {  
		return "beep beep!";
	}  
}  
  
class Truck extends Car {  
	label = 'Truck';
	numWheels = 18;
}  
  
class Vespa extends Car {  
	label = 'Vespa';
	numWheels = 2;
}  
  
function washCar <T extends Car> (car: T) {  
	console.log(`Received a ${car.label} in the car wash.`);
	console.log(`Cleaning all ${car.numWheels} tires.`);
	console.log('Beeping horn -', car.horn());
	console.log('Returning your car now');
}  
  
const myVespa = new Vespa();  
washCar<Vespa>(myVespa);
  
const myTruck = new Truck();  
washCar<Truck>(myTruck);

// ### Output:
//Received a Vespa in the car wash.  
//Cleaning all 2 tires.  
//Beeping horn - beep beep!  
//Returning your car now  
//Received a Truck in the car wash.  
//Cleaning all 18 tires.  
//Beeping horn - beep beep!  
//Returning your car now
```
