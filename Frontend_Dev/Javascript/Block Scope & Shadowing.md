
---

## **1. Block Scope in JavaScript**

👉 **Block scope** means that a variable declared inside a block `{ ... }` can only be accessed **within that block** (and its inner blocks).

- A **block** in JS is anything inside `{ }` (like in `if`, `for`, `while`, or just `{}`).

```js
{
  let a = 10;
  const b = 20;
  var c = 30;
}

console.log(c); // ✅ Works (var is function-scoped, not block-scoped)
console.log(a); // ❌ Error (a is block-scoped)
console.log(b); // ❌ Error (b is block-scoped)
```

## **2. Shadowing in JavaScript**

👉 **Shadowing** happens when a variable declared in an **inner scope** has the same name as one in an **outer scope**. The inner variable **"shadows"** (overrides) the outer one **inside that scope**.

```js
function test() {
	let x = 10;
	{
		let x = 20; // shadows outer 'x'
	    console.log(x); // 20
	}
	  console.log(x); // 10
}

test();
```

Here:

- Inner `x` shadows the outer `x` only inside the block.

## **3. Illegal Shadowing**

- **`var` can shadow `let`/`const`** → ❌ Not allowed in the same scope.
    
- **`let`/`const` can shadow `var`** → ✅ Allowed inside a different block.
    

### Example (Illegal Shadowing):

```js
let a = 10;
{
  var a = 20; // ❌ Error: Identifier 'a' has already been declared
}
```

### Example (Legal Shadowing):

```js
var b = 30; 
{   
	let b = 40; // ✅ Allowed  
	 console.log(b); // 40 
} 
console.log(b); // 30
```

✅ **Summary:**

- **Block Scope** → `let` and `const` are block-scoped, `var` is function-scoped.
    
- **Shadowing** → Inner variable with the same name hides the outer one inside its block.
    
- **Illegal Shadowing** → You cannot shadow a block-scoped variable (`let`/`const`) with `var`.

