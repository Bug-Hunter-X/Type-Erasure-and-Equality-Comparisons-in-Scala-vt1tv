# Type-Erasure and Equality Comparisons in Scala

This example highlights a subtle issue related to type erasure in Scala and how it impacts equality checks.  The `MyClass` uses a generic type `T`, and the `myMethod` compares values using `==`. This works fine for simple types like `Int` and `String`, but could lead to unexpected behavior for custom classes or those that require structural equality.

**Potential Problem:**
When the compiler erases the type parameter `T` at runtime, the comparison `value == other.value` relies on the default equality provided by the underlying type.

**Solution:**
For robust equality comparisons, consider using the `equals` method or defining a more sophisticated structural comparison logic that accommodates potential type differences.