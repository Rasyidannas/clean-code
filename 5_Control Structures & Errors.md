# Control Structures & Errors

## How to Keep Your Control Structure Clean?
1. Avoid Deep Nesting
   * Using Factory Functions and Polymorphism
   * Utilize Error
2. Prefer Positive Checks (if isEmpty vs isNotEmpty)
3. Use Guards & Fail Fast
   * Example:
       * `if(!email.includes(@))`
       * `if(!user.active)`
       * `if(!user.hasPurchases())`
