# Writing components for dummies

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

### Props
TODO

### Emits
Use the Typescript constructor
Call your variable `emit`. Because it is a verb and action, not a list.

Example:
```Typescript
const emit = defineEmits<{(e: 'change', value: Person)}>();
```


### HTML tags

- `<section>This is used as a wrapper for big pieces of code</section>`
- `<article>This is used as a wrapper for a single item in a section</article>`
- h1, h2, h3,
- `<p>This is used for text and paragraphs</p>`
- `<span>Text</span>`
- `<a href='www.usemeforlinks.please'>`

### Histoire 

TODO

- Why
- Docs
- Variants
- Examples


[Back to intro](README.md)
