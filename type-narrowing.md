# Type Narrowing in TypeScript: `typeof`, `instanceof`, and `in` operator

## Introduction

Type narrowing is the process of moving from a broad type to a more specific type after checking a value. It helps TypeScript to understand which operations are safe in a particular branch of code. This is especially useful when we work with union types.

## Detailed Explanation

The `typeof` operator checks JavaScript primitive types. TypeScript uses the result to narrow a union.

```typescript
function format(value: string | number): string {
  if (typeof value === "string") {
    return value.toUpperCase();
  }
  return value.toFixed(2);
}
```

The `instanceof` operator checks whether an object was created from a particular class or constructor. TypeScript can then allow class-specific methods.

```typescript
class Dog {
  bark() { return "Woof!"; }
}

class Cat {
  meow() { return("Meow!"); }
}

function animalSounds(animal: Dog | Cat): string {
  if (animal instanceof Dog) {
    return animal.bark();
  }
  return animal.meow();
}
```

The `in` operator checks whether a property exists on an object or not. in operator checks for the existence of a property on an object. It is useful for narrowing down object types that share a union without needing a class instance.

```typescript
type Admin = { name: string; permissions: string[] };
type Guest = { name: string; visitCode: string };

function executeTask(user: Admin | Guest): string {
  if ("permissions" in user) {
    return user.permissions.join(", ");
  }
  return user.visitCode;
}
```

## Conclusion

From the above examples we can understand that type narrowing makes union types practical and safe. So, we should use `typeof` for primitive checks, `instanceof` for class instances, and `in` for checking object properties. These checks help us a more precise type in TypeScript infer  without unnecessary type assertions.
