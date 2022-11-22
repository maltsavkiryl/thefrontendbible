# Clean code 🥰

### Comments
No. Only when doing something really weird and you want to let other people know exactly why you did that weird thing in the first place.

### Commented code
No. No exception. Git knows everything or just write it again later.

### Functions
Writing proper functions can be a difficult task for some. Follow these guidelines to keep em' clean.

- A maximum of 4 parameters
  - You probably need to pass an object if you need more than 4 params.
- No flag parameters.
  - Split the function into 2 different functions and create a parent function that calls the correct one.
- Max 10-15 lines
  - You are doing to much stuff otherwise.
- Keep em pure
  - Return the result.
  - No side effects.
- Single responsibility
  - Obviously. Only one reason to change.
- The longer the function name the better.
  - The name should tell exactly what the function does.
- Extract duplicate code to private functions.
  - Avoid code duplication. Re-use small snippets.

[Back to intro](README.md)
