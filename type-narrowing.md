```markdown
# What is Type Narrowing in TypeScript?

### Introduction
In TypeScript, we often pass different types of values into a single function using union types, like `string | number`. But when we do that, TypeScript does not know which type it is at runtime. Type narrowing is simply the way we check the type using normal `if` conditions so TypeScript understands what data we are dealing with.

### How We Narrow Types
We mostly use simple JavaScript checks like `typeof`, `instanceof`, and the `in` operator. Once we check inside an `if` block, TypeScript automatically unlocks the correct methods for that specific type.

```typescript
// 1. Using typeof for basic types
function showInfo(data: string | number) {
  if (typeof data === "string") {
    console.log(data.toUpperCase()); // safe to use string methods
  } else {
    console.log(data * 2); // safe to do math
  }
}

// 2. Using in operator for objects
type Cat = { meow: () => void };
type Dog = { bark: () => void };

function makeNoise(pet: Cat | Dog) {
  if ("meow" in pet) {
    pet.meow();
  } else {
    pet.bark();
  }
}