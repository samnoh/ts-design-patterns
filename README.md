# TypeScript Design Patterns

## TIL

### tsconfig.json

-   create `tsconfig.json` automatically

```bash
tsc --init --rootDir "./src" --outDir "./build"
```

### concurrently

-   Run multiple commands concurrently
-   [npm](https://www.npmjs.com/package/concurrently)

```bash
npm install --save-dev concurrently
```

-   `package.json`

```json
"scripts": {
    "start:run": "nodemon build/index.js",
    "start:tsc": "tsc -w",
    "start": "concurrently npm:start:*"
}
```

### Abstract Classes

-   Strongly couples classes together
-   Informs child classes what methods they should have

```TypeScript
abstract class Vehicle {
    abstract goTo(road: string): void
    abstract setOwner(name: string): void

    startEngine(): void {...}
}
```

```TypeScript
class Car extends Vehicle {
    constructor() {
        super();
        ...
    }
}
```
