# Design patterns


## SOLID Principles

### Single responsibility



### Open closed
> Modules should be open for extension but closed for modification

That means that if you want to extend a module's behavior, you won't need to modify the existing code of that module.

```Typescript
class Person {
  constructor(firstName, lastName, hobby, education, workplace, position) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.hobby = hobby;
    this.education = education;
    this.workplace = workplace;
    this.position = position;
  }
}

const personFilter = (persons: Person[], filterType: string): Person[] => {
  if(filterType === 'firstName'){
    return persons.filter(person => person.firstName === firstName);
  }

  if(filterType === 'lastName'){
    return persons.filter(person => person.lastName === lastName);
  }
  
  if(filterType === 'hobby'){
    return persons.filter(person => person.hobby === hobby);
  }
}
```

The problem with personFilter function is that if we want to filter by any other new property we have to change personFilter's code. Let's solve this problem by allowing the filter to accept any prop name and allow it to directly filter it.

```Typescript
const personFilter = (persons: Person[], propName: string): Person[] => {
  return array.filter(element => element[propName] === value)
}
```
  
  
  
 
