# The Frontend Bible

This document contains guidelines of how frontend development should be done. Masterfully crafted frontend’s are a pain in the ass to create because everything in the frontend is a feature. No problem because we will set some ground rules to help us develop easy to understand code, simple conventions, consistency, tips & tricks, design patterns, anti patterns, … 

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
**[Libraries](libraries.md)**<br>
**[Utils](utils.md)**<br>
**[Form validation](form-validation.md)**<br>
**[Design patterns](design-patterns.md)**<br>
**[Testing](testing.md)**<br>

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

