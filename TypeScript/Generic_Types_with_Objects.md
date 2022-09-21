# Generic Types with Objects

Sometimes a function is given an key-value pair to work on a certain (global) object or class property. In the most simple case where all object properties have the same type, this can be done as follows:

```typescript
interface Customer {
	name: string;
	email: string;
}
function editCustomer(key: keyof Customer, val: string) {
	//Do somethin with an instance of Customer that is defined outside the function
}
```

However, once the object to be manipulated has values with different types, TypeScript needs to infer the correct type of a value according to the given key. This can be solved by using Generic Types which extend the Objects type and keys as follows:

```typescript
interface ComplexCustomer {
	name: string;
	email: string;
	age: number;
	isVerified: boolean;
}
function editCustomer<
	K extends keyof ComplexCustomer,
	V extends ComplexCustomer[K]
>(key: K, val: V) {
	//Do somethin with an instance of Customer that is defined outside the function
}
```

Now, if the function is passed `"name"` as first argument, TypeScript can infer that `val` needs to be of type `string`.
