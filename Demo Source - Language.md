# Language

## Basic Types

``` javascript
var x: number = 5;
var y: number = 5;

var isLoaded: boolean = false;

var firstName: string = 'Joseph';
var lastName: string = 'Guadagno';

var pets: string[] = ['Sammie', 'Max', 'Jessie'];

var info: any = { address: '1 North Central', city: 'Phoenix', state: 'AZ', zipcode: '85248' };

window.onload = function () {
    var z = x + y;
    console.log('x + y = ' + z);
    console.log('isLoaded = ' + isLoaded);
    console.log('Pets List:');
    for (var i: number = 0; i < pets.length; i++) {
        console.log(pets[i]);
    }
    console.log('Info: ' + info.address + ' ' + info.city);
};
```

## Let / Const / Scoping

``` javascript
let firstName: string = 'Joe';
firstName = 5;
firstName = 'Oscar';
const eyeColor: string = 'Brown';
eyeColor = 'purple'

function f(shouldInitialize: boolean) {
    if (shouldInitialize) {
        var x = 10;
    }

    return x;
}

f(true);  // returns '10'
f(false); // returns 'undefined'
```

## Parameter Types

``` javascript
function add(x: number, y: number, msg: string) {
    console.log(msg + (x + y));
}

add(3, 2,'typed parameters (msg: string, x: number, y: number) = ');
```

## Optional/Default Parameters

``` javascript
// Optional
function add(x: number, y: number, msg?: string) {
    console.log(msg + (x + y));
}

add(3, 2, 'typed parameters (msg: string, x: number, y: number) = ');

// Default
function add(x: number, y: number, msg: string = "Result: ") {
    console.log(msg + (x + y));
}

add(3, 2, 'typed parameters (msg: string, x: number, y: number) = ');
// Note: With or without the string

// Rest
function add( msg = "Result: ", x: number, y: number, ...others: number[]) {
    console.log(msg + (x + y));
}

add('typed parameters (msg: string, x: number, y: number) = ', 3, 2, 5,6,7,8,8,);
```

## Aliases

``` javascript
type int = number;
type float = number;
type StringArray = string[];
type NumberArray = number[];

var x: int = 5;
var lat: float = 120.05;
var names: StringArray = ['Joe', 'Deidre'];
var ages: NumberArray = [35, 42, 83];
```

## Const Enums

``` javascript
enum NonConstLightState { On, Off, Dimmed };
const enum LightState { On, Off, Dimmed };

var nonConstLightState = NonConstLightState.On;
var LightState = LightState.Off;

console.log('');
console.log('NonConstLightState is ' + nonConstLightState);
console.log('LightState is ' + LightState);
```

## Classes

``` javascript
namespace DefiningClasses {
    class Person {
        private _firstName: string;
        private _middleName: string;
        private _lastName: string;
        private _dateOfBirth: Date;

        constructor (firstName: string, lastName: string, middleName?: string, dateOfBirth?: Date) {
            this._firstName = firstName;
            this._lastName = lastName;
            this._middleName = middleName;
            this._dateOfBirth = dateOfBirth;
        }

        public FullName(): string {
            if (this._middleName == null) {
                return this._firstName + " " + this._lastName;
            } else {
                return this._firstName + " " + this._middleName + " " + this._lastName;
            }
        }

        get firstName(): string {
            return this._firstName;
        }

        set firstName(newFirstName: string) {
            this._firstName = newFirstName;
        }
    }
}

var person = new Person("Joseph", "Guadagno");
console.log(person.FullName());
}
```

## Extending Classes

['Demo-Source-Extending-Classes]('Extending Classes')

## Interfaces

['Demo-Source-Interfaces]('Interfaces')

## Generics

``` javascript
//Normal way
var numbers: number[] = [];
var names: string[] = [];

//Generics way
var numbers = new Array<number>();
numbers.push(1);
numbers.push(2);

var names = new Array<string>();
names.push('Jane');
names.push('John');
```

## Arrow Functions

``` javascript
var Add = (a: number, b: number) => {
    return a + b;
}

console.log(Add(4, 5));
```