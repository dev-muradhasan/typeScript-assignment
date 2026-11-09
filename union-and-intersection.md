# Combining Union and Intersection Types in TypeScript

## Introduction

TypeScript has many useful features. Union Types and Intersection Types are two of them. They help us create flexible types. Union Types use the `|` symbol, and Intersection Types use the `&` symbol.

## 1. Union Type

A Union Type allows a variable to have more than one possible type. We use the `|` symbol to create a Union Type.

```ts
type ID = string | number;

let userId: ID;

userId = 101;
userId = "USER-101";
```

Here, `userId` can store either a number or a string. This is useful when we need to use different types of values.

## 2. Intersection Type

An Intersection Type combines two or more types into one type. We use the `&` symbol.

```ts
type Person = {
    name: string;
};

type Employee = {
    salary: number;
};

type Staff = Person & Employee;

const staff: Staff = {
    name: "Murad",
    salary: 30000
};
```

Here, `Staff` needs both `name` and `salary` properties.

## 3. Combining Union and Intersection Types

We can use Union and Intersection Types together.

```ts
type Admin = {
    role: "admin";
    permissions: string[];
};

type Customer = {
    role: "customer";
    purchaseCount: number;
};

type User = {
    id: string | number;
    name: string;
};

type Account = User & (Admin | Customer);
```

Here, every account needs an `id` and `name`. It must also be either an Admin or a Customer.

## Conclusion

Union Types allow different types of values, while Intersection Types combine multiple types. We can use both together to create useful and flexible types in TypeScript. They help us write clean and organized code.