
---
### 📌 Overview

`String` in Java is **immutable**, meaning once created, it cannot be changed.  
Most methods **return a new string** instead of modifying the original.

---

### 🧩 1. Creation & Basic Info

```java
String s = "hello"; String str = new String("hello");
```

|Method|Description|Example|Output|
|---|---|---|---|
|`length()`|Returns number of characters|`"hello".length()`|`5`|
|`charAt(int index)`|Returns character at given index (0-based)|`"hello".charAt(1)`|`'e'`|
|`isEmpty()`|Checks if string is empty|`"".isEmpty()`|`true`|
|`isBlank()`|Checks if string is empty or whitespace|`" ".isBlank()`|`true`|

---

### 🔡 2. Comparison & Equality

|Method|Description|Example|Output|
|---|---|---|---|
|`equals(String str)`|Checks content equality (case-sensitive)|`"abc".equals("ABC")`|`false`|
|`equalsIgnoreCase(String str)`|Ignores case while comparing|`"abc".equalsIgnoreCase("ABC")`|`true`|
|`compareTo(String str)`|Lexicographically compares|`"apple".compareTo("banana")`|`<0`|
|`compareToIgnoreCase(String str)`|Case-insensitive compare|`"A".compareToIgnoreCase("a")`|`0`|

---

### ✂️ 3. Substring & Extraction

|Method|Description|Example|Output|
|---|---|---|---|
|`substring(int begin)`|Returns substring from `begin`|`"abcdef".substring(2)`|`"cdef"`|
|`substring(int begin, int end)`|Returns substring `[begin, end)`|`"abcdef".substring(1,4)`|`"bcd"`|

🧠 _Common in:_

- Sliding Window problems
    
- Substring Search 

---

### 🔍 4. Searching

|Method|Description|Example|Output|
|---|---|---|---|
|`contains(CharSequence s)`|Checks if substring exists|`"abcd".contains("bc")`|`true`|
|`indexOf(String s)`|First index of substring|`"abcabc".indexOf("bc")`|`1`|
|`lastIndexOf(String s)`|Last index of substring|`"abcabc".lastIndexOf("bc")`|`4`|
|`startsWith(String prefix)`|Checks prefix|`"hello".startsWith("he")`|`true`|
|`endsWith(String suffix)`|Checks suffix|`"hello".endsWith("lo")`|`true`|

---

### 🔁 5. Modification & Transformation

|Method|Description|Example|Output|
|---|---|---|---|
|`toUpperCase()`|Converts to uppercase|`"abc".toUpperCase()`|`"ABC"`|
|`toLowerCase()`|Converts to lowercase|`"ABC".toLowerCase()`|`"abc"`|
|`trim()`|Removes leading/trailing spaces|`" hi ".trim()`|`"hi"`|
|`replace(char old, char new)`|Replaces characters|`"aba".replace('a','x')`|`"xbx"`|
|`replaceAll(String regex, String repl)`|Regex-based replacement|`"a1b2".replaceAll("\\d","")`|`"ab"`|

🧠 _Common in:_

- String normalization
    
- Anagram problems
    
- Token cleaning

---

### 🧮 6. Splitting & Joining

|Method|Description|Example|Output|
|---|---|---|---|
|`split(String regex)`|Splits string into array|`"a,b,c".split(",")`|`["a","b","c"]`|
|`String.join(delimiter, elements...)`|Joins array into string|`String.join("-", "a","b")`|`"a-b"`|

🧠 _Common in:_

- Parsing CSVs
    
- Tokenizing input strings

---

### 🔄 7. Conversion & Utilities

|Method|Description|Example|Output|
|---|---|---|---|
|`toCharArray()`|Converts to `char[]`|`"abc".toCharArray()`|`['a','b','c']`|
|`String.valueOf(int)`|Converts value to String|`String.valueOf(123)`|`"123"`|
|`concat(String s)`|Concatenates strings|`"hi".concat(" there")`|`"hi there"`|

🧠 _Common in:_

- Palindrome check
    
- Character counting


---

### 🧰 8. StringBuilder (For Mutable Strings)

Use when repeatedly modifying strings in loops.

```java
StringBuilder sb = new StringBuilder("hello"); 
sb.append(" world"); 
sb.reverse(); 
System.out.println(sb.toString());
```

|Method|Description|
|---|---|
|`append()`|Adds text efficiently|
|`insert(int index, String str)`|Inserts text|
|`delete(int start, int end)`|Deletes a range|
|`reverse()`|Reverses string|
|`toString()`|Converts back to `String`|

🧠 _Why use:_  
String concatenation in loops = costly (creates new strings).  
`StringBuilder` = efficient mutable buffer.

---

### ⚙️ 9. Common Patterns in DSA

|Pattern|Example Problem|
|---|---|
|Reverse a string|Use `StringBuilder` or two-pointer swap|
|Check palindrome|Compare `s.charAt(i)` vs `s.charAt(n-1-i)`|
|Anagram check|Count chars using array or map|
|Substring problems|Use `substring()` + `indexOf()`|
|Longest unique substring|Sliding window + `charAt()`|