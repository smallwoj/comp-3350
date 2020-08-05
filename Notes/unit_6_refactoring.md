# Unit 6: Refactoring
- Improving the design of existing code
- Done to fix code and design smells
- A continuous process
## Common Refactorings
1. Rename (variable, method, class, package)
   - Change the name of something to clarify and reflect its current use
   - `int result, toReturn`
     - Lost opportunity
     - `differenceInDays`
   - Reduces commenting
2. Move (instance var, method, class, package)
   - Something belongs closer to the place where it is used
   - `Utilities.convert()`
     - Move it to where its actually used
3. Remove
   - Ex. Any dead code
   - Ex. Double negative
     - `while(!itemNotFound)`
       - Replace with `while(itemFound)`
4. Replace
   - Ex. Replace a method with a method object
      ```java
      void complex()
      {
          int state1, state2, state3...
          ...
          //difficult stuff
          //lots of steps
      }
      ```
      Replace with
      ```java
      class Complex
      {
          private int state1, state2, state3, ...
          public void act()
          {
              //init state
              step1();
              step2();
              ...
          }
          public void step1()
          {
              ...
          }
          public void step2()
          {
              ...
          }
      }
      (new Complex()),act();
      ```
5. Extract (method, class, package)
   - Method `a()` does b,c,d
     - `a() {b(); c(); d();}`
   - Classes: Extract to superclass or contained object or interface (pull up)
6. Inline (variables, methods, classes)
   - Inverse of extraction
   - Ex. move a calculation closer to where it's used
        ```java
        if(something < _____)/* move __ to variable, then to other method, then move the method back to in the if*/
        {
            ...
        }
        ```
    - Classes: move something into a subclass ("push down")
7. Inheritance Reorganization
   - Create new superclass for pull up
     - Insert intermediary superclass
   - Reorganization of hierarchy
   - Replace implementation inheritance with a different relation
8. Introduce Design Patterns

