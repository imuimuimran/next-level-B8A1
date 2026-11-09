# Type aliases vs. Interface in TypeScript: Core Differences and When to Choose Each

## Introduction

TypeScript provides both `type` aliases and `interface` declarations to describe the shape of data. They often look interchangeable, especially when defining object properties, but they have important differences. The core difference is interfaces are open to expansion via declaration merging, whereas type aliases are closed and cannot be changed after definition. Understanding those differences helps us to choose a clear and maintainable design.

## Detailed Explanation

An `interface` is primarily designed to describe object shapes and class contracts. Interfaces can be extended with `extends`, and declarations with the same name are automatically merged.

```typescript
interface Person {
  name: string;
}

interface Person {
  age: number;
}

const user: Person = { name: "Mir", age: 25 };
```

A `type` alias can describe an object too, but it can also represent unions, intersections, primitives, tuples, and other types.

```typescript
type Status = "active" | "inactive";

type Person = {
  name: string;
  age: number;
};

type Employee = Person & { department: string };
```

Unlike interfaces, type aliases cannot be reopened through declaration merging. Both can be extended or combined in different ways: interfaces commonly use `extends`, while types often use intersection (`&`).

## Conclusion

We have to use `interface` by default as well as when describing object structures that may be extended or augmented, especially public object-oriented APIs. On the other hand we should use `type` aliases when we need unions, tuples, primitives, or more complex type expressions. 
