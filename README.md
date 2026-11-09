# Repository Overview

This repository contains practical TypeScript utility functions, object-oriented implementations, and conceptual markdown guides focusing on core TypeScript topics like type narrowing and type definition choices.

---

## 📂 Repository Structure & Components

### 1. `solutions.ts`
A collection of TypeScript utilities, classes, and asynchronous workflows demonstrating type definitions, generics, class inheritance, and access modifiers.

#### 🔧 Core Functions
* **`multiplyValue(value, multiplier?)`**: Multiplies a given number by an optional multiplier. If no multiplier is provided, it defaults to `2` using the nullish coalescing (`??`) operator.
* **`processInput(value)`**: Demonstrates type checking for a union type (`string | number | boolean`). It cleans strings, scales numbers by 10, and maps booleans to an status string ("Active"/"Inactive").
* **`formatCoordinate(coordinate)`**: Takes a read-only tuple (`readonly [number, number, string]`) containing latitude, longitude, and a location name, and returns a formatted string template.
* **`concatenateArrays(...arrays)`**: A generic utility function (`<T>`) that takes multiple arrays of type `T` and flattens them into a single unified array.
* **`getPopularCourses(courses, minStudents)`**: Filters an array of `Course` objects, returning only the published courses that meet or exceed the minimum student enrollment threshold.
* **`pluckValues(items, key)`**: A generic utility that extracts an array of values corresponding to a specific key (`K extends keyof T`) from an array of objects.
* **`validateAgeAsync(age)`**: An asynchronous function returning a `Promise<string>`. It rejects immediately with an `Error` instance if the age is under 18, or resolves with "Access Granted" after a 1-second (1000ms) delay.

#### 🏛️ Object-Oriented System (Classes)
* **`Employee`**: A base class utilizing access modifiers (`protected name` and `private baseSalary`) along with a `getDetails()` method to securely present employee information.
* **`Manager`**: A subclass that inherits from `Employee` using `super()`, introducing a private `department` property and providing customized role reporting via `getRoleInfo()`.

---

### 2. Conceptual Guides

* **[Type Aliases vs. Interface](https://github.com/imuimuimran/next-level-B8A1/blob/main/type-vs-interface.md)** (`type-vs-interface.md`)  
  A deep-dive guide contrasting `type` and `interface` declarations. It highlights how interfaces support declaration merging and class enforcement, while type aliases excel with unions, intersections, primitives, and complex tuples.
  
* **[Type Narrowing Guide](https://github.com/imuimuimran/next-level-B8A1/blob/main/type-narrowing.md)** (`type-narrowing.md`)  
  An explanatory guide on refining broad union types into specific types safely. It demonstrates how to leverage JavaScript operators (`typeof` for primitives, `instanceof` for class instances, and `in` for property checks) to satisfy the TypeScript compiler.

---

## 🔗 Quick Links

* [View Type vs. Interface Guide on GitHub](https://github.com/imuimuimran/next-level-B8A1/blob/main/type-vs-interface.md)
* [View Type Narrowing Guide on GitHub](https://github.com/imuimuimran/next-level-B8A1/blob/main/type-narrowing.md)

