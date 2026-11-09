# Combining Union and Intersection Types in TypeScript

## Introduction

TypeScript provides powerful features for defining flexible and reusable types. Two important features are Union Types (`|`) and Intersection Types (`&`). Union Types allow a value to have one of several possible types, while Intersection Types combine multiple types into a single type.

## Understanding Union Types

A Union Type allows a variable to accept more than one type. For example:

```ts
type ID = string | number;

let userId: ID;

userId = 101;
userId = "USER-101";
```

Here, `userId` can store either a string or a number. This is useful when an application supports different types of user IDs.

## Understanding Intersection Types

An Intersection Type combines multiple types. A value must contain all the properties required by those types.

```ts
type Person = {
    name: string;
};

type Employee = {
    employeeId: number;
};

type Staff = Person & Employee;

const staff: Staff = {
    name: "Murad",
    employeeId: 101
};
```

Here, `Staff` requires both `name` and `employeeId`.

## Combining Union and Intersection Types

We can combine both types to create more flexible data structures.

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

In this example, every account must have an `id` and `name`. Additionally, it must satisfy either the `Admin` type or the `Customer` type.

## Conclusion

Union and Intersection Types make TypeScript applications more flexible and maintainable. Combining them helps developers represent real-world data structures with clear and accurate type definitions.