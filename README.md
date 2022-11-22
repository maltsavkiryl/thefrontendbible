# The Frontend Bible

This document contains guidelines of how frontend develop should be done. Masterfully crafted frontend’s are a pain in the ass to create because everything in the frontend is a feature. No problem because we will set some ground rules to help us develop easy to understand code, simple conventions, consistency, tips & tricks, design patterns, anti patterns, … 

### The frontend club
- Rule number one of the frontend club is that you have to use Typescript. No exceptions.
- Second rule of the frontend club is that you will use Typescript. Plain Javascript is. not. allowed. ever.
- Third rule of the frontend club is that everone who doesn't use Typescript is not allowed in the frontend club.

Please just fucking use typescript.

### Table of Contents
**[Naming conventions](naming-conventions.md)**<br>
**[Project structure](project-structure.md)**<br>
**[Clean components](clean-components.md)**<br>
**[Composables](composables.md)**<br>
**[Form validation](form-validation.md)**<br>
**[Design patterns](design-patterns.md)**<br>
**[Testing](testing.md)**<br>

### Components

We use the `<script setup lang='ts'>` to define components.

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

### Histoire TODO

- Why
- Docs
- Variants
- Examples

