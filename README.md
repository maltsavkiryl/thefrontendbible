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



