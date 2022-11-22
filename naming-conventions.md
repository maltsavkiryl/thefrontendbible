# Naming conventions
You know what’s the most annoying thing in programming? Naming things. 🥲 So let’s get ourselves some standards and never think about it ever again.

### File names
A great way to quickly find things in your IDE is being searching directly by file name. A simple way to improve your experience is to suffix your components with their function.

| Type                       | Example              | 
|----------------------------|----------------------|
| **types**                  |`example.type.ts`     | 
| **services**               |`example.service.ts`  | 
| **stores**                 |`example.store.ts`    |
| **routes**                 |`example.routes.ts`   |
| **views**                  |`ExampleView.ts`      |

### File name casing

- **folders**: kebab-case eg. `my-example-folder`
- **.ts files**: camelCase eg. `exampleCenter.ts`
- **.vue files**: PascalCase eg. `MyComponent.vue`

### Object name casing

| Type                       | Casing               | Example                |
|----------------------------|----------------------|------------------------|
| **services**               | PascalCase           | `ExampleService`       |
| **stores**                 | use + PascalCase     | `useExampleStore`      |
| **composables**            | use + PascalCase     | `useExampleComposable` |
| **types**                  | PascalCase           | `ExampleType`          |
| **routes**                 | PascalCase           | `ExampleRoutes`        |
| **variable names**         | camelCase            | `exampleVariable`      |
| **function names**         | camelCase            | `exampleFunction`      |
| **constants**              | UPPERCASE_SNAKE_CASE | `MY_CONSTANT`          |
| **components in template** | PascalCase           | `<MyComponent />`      |
| **translation key**        | snake_case           | `my_key`               |
| **route paths**            | kebab-case           | `/example-route`       |


[Back to intro](README.md)
