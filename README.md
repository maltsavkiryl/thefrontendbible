# The Frontend Bible

This document contains guidelines of how frontend develop should be done. Masterfully crafted frontend’s are a pain in the ass to create because everything in the frontend is a feature. No problem because we will set some ground rules to help us develop easy to understand code, simple conventions, consistency, tips & tricks, design patterns, anti patterns, … 

### The frontend club
- Rule number one of the frontend club is that you have to use Typescript. No exceptions.
- Second rule of the frontend club is that you will use Typescript. Plain Javascript is. not. allowed. ever.
- Third rule of the frontend club is that everone who doesn't use Typescript is not allowed in the frontend club.

Please just fucking use typescript.

### Naming conventions
You know what’s the most annoying thing in programming? Naming things. Period. So let’s get ourselves some standards going.

#### File names
A great way to quickly find things in your IDE is being searching directly by file name. A simple way to improve your experience is to suffix your components with their function.

| Type                       | Example              | 
|----------------------------|----------------------|
| **types**                  |`example.type.ts`     | 
| **services**               |`example.service.ts`  | 
| **stores**                 |`example.store.ts`    |
| **routes**                 |`example.routes.ts`   |
| **views**                  |`ExampleView.ts`      |

#### File name casing

- **folders**: kebab-case eg. `my-example-folder`
- **.ts files**: camelCase eg. `exampleCenter.ts`
- **.vue files**: PascalCase eg. `MyComponent.vue`

#### Object name casing

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

### Components

We use the `<script setup lang='ts'>` to define components.

### Structure

The project structure is a hybrid between type and module based. All the folders in the `src` contain shared code. (
services, stores, types, ...)
The module folder contains multiple folders grouped by "features" eg. **employees**. Each module is then split into
types.

```
- src
  - services (shared services)
    - example.service.ts
    - ...
  - components (shared components)
    - TheHeader.vue
    - TheFooter.vue
    - ...
  - icons
  - composables (shared composables)
    - saving.ts
    - ...
  - modules
    - accidents
        - components
            - AccidentList.vue
            - AccidentDetail.vue
            - ...
        - services
            - accident.service.ts
            - ...
        - composables
            - ...
        - ...
  - router
  - stores (shared stores)
  - types (shared types)
  - views (shared views)
    - Error404View.vue
    - ...
  - main.ts
```

### Shared components folder structure

```
- assets
- components
    - app
        - button
            - AppButton.vue
            - AppButton.story.ts
        - badge
            - AppBadge.vue
            - AppBadge.story.ts
        - card
            - AppCard.vue
            - AppCard.story.ts
            - title
                - AppCardTitle.vue
                - AppCardTitle.story.ts
    - form
        - select
            - FormSelect.vue
            - FormSelect.story.ts
        - multi-select
            - FormMultiSelect.vue
            - FormMultiSelect.story.ts
        - birthday-picker
            - FormBirthdayPicker.vue
            - FormBirthdayPicker.story.ts
    - calendars
        - planning
            - CalendarPlanning.vue
            - CalendarPlanning.story.ts
- composables
- ...
```

### Composable vs helpers

#### Composable

Composables are a piece of reusable logic that contain state and or use vue specific reactivity like refs, computed,
etc. A good example is the `saving.ts`
composable.

Composables always use the `use...` prefix in their function name. and are suffixed with `.composable.ts`.

```typescript
//Good example of a composable
import { ref } from "vue";

export const useSaving = () => {
  const savingRef = ref(false);

  const setSaving = (value: boolean): void => {
    savingRef.value = value;
  };

  const isSaving = (): boolean => savingRef.value;

  return {
    setSaving,
    isSaving,
  };
};
```

#### Utils/helpers

Utils are reusable pieces of logic that are not specific to vue and never contain any state. A good example is
the `dates.util.ts`. Each function is
exported as a const and does not share state with the other functions.

```typescript
//Good example of a helper function
import dayjs from "@/helpers/dayjs";

export const hasDate = (date: DateType | string): boolean => date !== "-";

export const formatDate = (date: DateType | string) => {
  return dayjs(date).format("DD/MM/YYYY");
};
```

### Smart vs Dumb components
Aka container components vs presentational components.

Why? TODO

- Smart components (container)
  - inject all of your stores, router, services, ... 
  - Contain heavy business logic
  - Contain little to no presentation logic in their template
- Dumb components (presentational)
  - Pure input & output (props & emits)
  - Never contain any injection of a router, store, service, ... 
  - Are focused on rendering data, handling user interaction and emitting events
  
### Wrapping libraries
When using a library for components, validation, etc. It's always really smart to create a wrapper around it. This will:
- Help you control and clean up the API so that only the necessary options are exposed.
- Give you the opportunity to cusomize them and add functionalty. 
- If you every decide to switch the library or are required to create your own custom implementation, you already have the API defined and every usage of that component doesn't have to change.

### Booleans
Always prefix your boolean variables with `is` or `has`.

### HTML tags

- <section>This is used as a wrapper for big pieces of code</section>
- <article>This is used as a wrapper for a single item in a section</article>
- h1, h2, h3,
- <p>This is used for text and paragraphs</p>
- <span>Text</span>
- <a href='www.usemeforlinks.please'>

### Props
TODO

### Emits
Use the Typescript constructor
Call your variable `emit`. Because it is a verb and action, not a list.

Example:
```Typescript
const emit = defineEmits<{(e: 'change', value: Person)}>();
```

### Solid principles & examples
#### Single responsiblity
#### Open closed
#### Liskov subsitition
#### Interface segregation
#### Dependency inversion

### Wrinting clean functions
- Max of 4 params
- No flags
- Max 10 lines
- Keep em pure if possible
- Single responsibility
- The longer the function name the better. 
- Functional 
- Extract duplicate code to private functions.
- 

### Code reviews
Knowledge sharing is the main priority.

### Testing
#### Unit test
#### Integration test
#### E2E test

