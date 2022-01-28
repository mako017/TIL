# Singleton Class

A singleton class makes sure that throughout the runtime only one instance of the class exists. This is achieved by making the constructor private and writing a static public method that calls the constructor if no instance exists or else returns the existing instance.

In the [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-0.html#private-and-protected-constructors) the following example is given.

```typescript
class Singleton {
	private static instance: Singleton;
	private constructor() {}
	static getInstance() {
		if (!Singleton.instance) {
			Singleton.instance = new Singleton();
		}
		return Singleton.instance;
	}
}
```

### Note

- In JavaScript runtime, the constructor won't be hidden. Thus, the singleton pattern can be broken.
- While some claim this to be an anti-pattern, the alternative of using namespaces is discouraged by ESLint
