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


[Back to intro](README.md)
