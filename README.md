# TypeScript Filter Persons Project

This project provides a `filterPersons` function that filters users based on their type (`user` or `admin`). The function ensures strong TypeScript typing to correctly return either `User[]` or `Admin[]`, depending on the filtering criteria.

## Features
- Filters users (`User`) or administrators (`Admin`) from a list of persons.
- Uses **TypeScript function overloading** for precise return types.
- Allows filtering by any **partial** criteria except the `type` field.
- Ensures strong TypeScript typing and safety.


## Installation
Ensure you have **Node.js** and **TypeScript** installed on your system.


### 2. Install Dependencies
```sh
npm install
```

### 3. Install TypeScript and ts-node (if not installed globally)
```sh
npm install -g typescript ts-node
```


## Functionality
### `filterPersons` Function
The function filters users (`User`) or admins (`Admin`) based on given criteria.

#### **Function Signature**
```ts
function filterPersons(
    persons: Person[],
    personType: 'user',
    criteria: Partial<Omit<User, 'type'>>
): User[];

function filterPersons(
    persons: Person[],
    personType: 'admin',
    criteria: Partial<Omit<Admin, 'type'>>
): Admin[];
```

#### **Example Usage**
```ts
const usersOfAge23 = filterPersons(persons, 'user', { age: 23 });
const adminsOfAge23 = filterPersons(persons, 'admin', { age: 23 });
```

### Sample Output
```
Users of age 23:
 - Kate Müller, 23, Astronaut
 - Wilson, 23, Ball

Admins of age 23:
 - Agent Smith, 23, Anti-virus engineer
```

## TypeScript Types
### **User Interface**
```ts
interface User {
    type: 'user';
    name: string;
    age: number;
    occupation: string;
}
```

### **Admin Interface**
```ts
interface Admin {
    type: 'admin';
    name: string;
    age: number;
    role: string;
}
```

### **Person Type (Union of User and Admin)**
```ts
type Person = User | Admin;
```

## License
This project is licensed under the **MIT License**.

