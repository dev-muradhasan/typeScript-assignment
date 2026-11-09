# Understanding Access Modifiers in TypeScript OOP

## Introduction

Access Modifiers are an important feature of Object-Oriented Programming (OOP) in TypeScript. They control how class properties and methods can be accessed. TypeScript provides four commonly used modifiers: `public`, `private`, `protected`, and `readonly`.

## 1. Public Modifier

The `public` modifier allows properties and methods to be accessed from anywhere, including outside the class. It is the default access modifier in TypeScript.

```ts
class Person {
    public name: string = "Murad";
}

const person = new Person();
console.log(person.name); // Murad
```

## 2. Private Modifier

The `private` modifier allows a property or method to be accessed only inside its own class. It cannot be accessed directly from outside the class or from a child class.

```ts
class BankAccount {
    private balance: number = 5000;

    getBalance() {
        return this.balance;
    }
}

const account = new BankAccount();
console.log(account.getBalance()); // 5000
```

## 3. Protected Modifier

The `protected` modifier allows access inside the same class and its child classes. However, it cannot be accessed directly from outside the class.

```ts
class Animal {
    protected name: string = "Dog";
}

class Dog extends Animal {
    showName() {
        console.log(this.name);
    }
}
```

## 4. Readonly Modifier

The `readonly` modifier allows a property to be assigned only during its declaration or inside the constructor. After initialization, its value cannot be changed.

```ts
class User {
    readonly id: number;

    constructor(id: number) {
        this.id = id;
    }
}

const user = new User(101);
console.log(user.id); // 101
```

## Conclusion

Access Modifiers help developers control data access, protect sensitive information, and organize classes. Using them properly makes TypeScript applications more secure, maintainable, and easier to understand.