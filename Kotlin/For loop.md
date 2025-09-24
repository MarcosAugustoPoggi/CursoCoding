### 1. **Basic Iteration Over a Collection**
- **Syntax**: `for (element in collection) {...}`

```kotlin
val numbers = listOf(1, 2, 3, 4, 5)  
for (number in numbers) {  
    println(number)  
}
```

```console
1
2
3
4
5
```

`for` iterates through anything that provides an iterator. This means that it:

- has a member or an extension function `iterator()` that returns `Iterator<>`, which:
    
    - has a member or an extension function `next()`
        
    - has a member or an extension function `hasNext()` that returns `Boolean`.


### 2. **Iteration with Indices**
- **Syntax**: `for (index in collection.indices) {...}`
```kotlin
val words = arrayOf("Kotlin", "is", "awesome")  
for (index in words.indices) {  
    println("Word at index $index is ${words[index]}")  
}
```

```console
Word at index 0 is Kotlin
Word at index 1 is is
Word at index 2 is awesome
```

### 3. **Iterating with `withIndex()`**
- **Syntax**: `for ((index, value) in collection.withIndex()) {...}`

```kotlin
val wordsAlt = listOf("Kotlin", "is", "great")  
for ((index, word) in wordsAlt.withIndex()) {  
    println("Word at index $index is $word")  
}
```

```console
Word at index 0 is Kotlin
Word at index 1 is is
Word at index 2 is great
```

### 4. **Iterating Over a Range**
- **Syntax**: `for (i in start..end) {...}`

```kotlin
for (i in 1..5) {  
    println(i)  
}
```

```console
1
2
3
4
5
```

### 5. **Iterating with a Step**
- **Syntax**: `for (i in start..end step stepSize) {...}`

```kotlin
for (i in 1..10 step 2) {  
    println(i)  
}
```

```console
1
3
5
7
9
```

### 6. **Iterating in Reverse**
- **Syntax**: `for (i in end downTo start) {...}`
-
```kotlin
for (i in 5 downTo 1) {  
    println(i)  
}
```

```
5
4
3
2
1
```

### 7. **Iterating Over a Map**
- **Syntax**: `for ((key, value) in map) {...}`

```kotlin
val map = mapOf(1 to "one", 2 to "two")  
for ((key, value) in map) {  
    println("$key = $value")  
}
```

```console
1 = one
2 = two
```

### 8. **Iterating Over Characters in a String**
- **Syntax**: `for (char in string) {...}`

```kotlin
val text = "Hello"  
for (char in text) {  
    println(char)  
}
```

```console
H
e
l
l
o
```

### 9. **Filtering Elements While Iterating**
- **Syntax**: `for (element in collection.filter { ... }) {...}`

```kotlin
val numbersAlt = listOf(1, 2, 3, 4, 5)  
for (number in numbersAlt.filter { it % 2 == 0 }) {  
    println(number)  
}
```

```console
2
4
```

### 10. **Breaking or Continuing the Loop**
- **`break`**: Exit the loop entirely.
- **`continue`**: Skip the rest of the current iteration and continue with the next one.

```kotlin
for (i in 1..10) {  
    if (i == 5) break  
    if (i % 2 == 0) continue  
    println(i)  
}
```

```console
1
3
```

### 11. **Nested Loops**
- **Syntax**: `for (element1 in collection1) { for (element2 in collection2) {...} }`

```kotlin
val matrix = listOf(listOf(1, 2), listOf(3, 4))  
for (row in matrix) {  
    for (item in row) {  
        println(item)  
    }  
}
```

```console
1
2
3
4
```

### 12. **Labelled Loops**
- **Syntax**: `loopLabel@ for (...) {...}`
-
```kotlin
outer@ for (i in 1..5) {  
    for (j in 1..5) {  
        if (j == 3) break@outer  
        println("i = $i, j = $j")  
    }  
}
```

```console
i = 1, j = 1
i = 1, j = 2
```