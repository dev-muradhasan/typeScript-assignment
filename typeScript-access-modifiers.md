# Access Modifiers in TypeScript OOP

## Introduction

Access Modifiers are used in TypeScript classes to control who can access properties and methods. TypeScript has four important modifiers: `public`, `private`, `protected`, and `readonly`. They help us control and protect data inside a class.

## 1. Public

The `public` modifier allows us to access a property or method from anywhere. It can be used inside and outside the class. It is the default modifier in TypeScript.

```ts
class Person {
    public name = "Murad";
}

const person = new Person();
console.log(person.name);
```

Output: `Murad`

## 2. Private

The `private` modifier allows us to use a property only inside its own class. We cannot access it directly from outside the class.

```ts
class Bank {
    private balance = 5000;

    getBalance() {
        return this.balance;
    }
}

const bank = new Bank();
console.log(bank.getBalance());
```

Output: `5000`

## 3. Protected

The `protected` modifier allows us to access a property inside its own class and its child classes. We cannot access it directly from outside.

```ts
class Animal {
    protected name = "Dog";
}

class Dog extends Animal {
    showName() {
        console.log(this.name);
    }
}
```

## 4. Readonly

The `readonly` modifier means we can set a value only once. After setting the value, we cannot change it.

```ts
class User {
    readonly id = 101;
}
```

## Conclusion

Access Modifiers help us control data access in TypeScript. They make our code easier to manage and protect important information. Each modifier has a different purpose, so we should use them according to our needs.