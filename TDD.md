# What is TDD
----

Test-Driven Development (TDD) is a software development process that follows a simple iterative cycle.

Test-Driven Development Cycle:

1. Write one test, called a test specification or test spec.
2. Run all of the existing tests. The test spec from step 1 should fail.
3. Write code that will pass your tests.
4. Run your tests. All tests should pass.
5. Refactor and clean up your code when necessary.
6. Repeat.

Here is a graphic that illustrates the Test-Driven development cycle:
![](Meta/Pasted%20image%2020231205225359.png)


### Benefits of TDD

1. **Focus**
    - Break your code into individual sections instead of trying to solve "the big picture" all at once.
1. **Self-Documenting**
    - Tests can serve as documentation for code. If you are unsure how to use a function, class, or library and there isn't official written documentation, you can check the corresponding test specs to learn how it is used. For example, you could check if a function accepts arguments and, if so, how they are used. Or you could check what type of value a function returns.
2. **Fewer Bugs**
    - Your program is constantly tested. With every new feature, new tests are are run.  This will eliminate bugs, and the possibility of introducing bugs or breaking existing code, when you add a new feature.
3. **Structured Code**
    - Since test specs are created before you write your code, you "use" your code before it is created. Using your code ahead of time will provide you the perspective of someone using the software you built, which can help you write more usable code.
4. **Functionally Correct**
    - You can demonstrate that your program does what it is supposed to do based on the results of your test specs.

### Example of a Test Suite

Take a moment to review the code and image below, which are is preview of a test suite we will use throughout this section. You do not need to understand this code yet. We will review the code throughout the sections on TDD and Reading Specs. At the end, you will have a better understanding of it.

Function and test spec code:

```JavaScript
/* Code to Test */const add = (x, y) => {  return x + y;};describe("add function", function() {  it("is a function", function() {expect(add).toBeDefined();expect(typeof add).toBe("function");  });  it("returns a number", function() {expect(typeof add(4, 5)).toBe("number");expect(typeof add(10, 20)).toBe("number");  });  it("returns the sum of two numbers", function() {expect(add(20, 40)).toBe(60);expect(add(50, 50)).toBe(100);  });});
```

Image of the test suite running in CodePen:

![A screenshot of a CodePen environment with the screen divided into two halves. The left half of the screen shows a section labeled J-S, which contains the same code as the code block immediately proceeding this image. The right half of the screen shows a section labeled Result, which shows a graphical interface for the running test specs. The Result screen displays the logo for Jasmine (a testing tool) and an Options button. Below there are three green dots and a green bar containing the text, "3 specs, 0 failures, randomized with seed 57316. Finished in 0.034s." Beneath the green bar is the text, "add function". Following that are three indented lines of text: "is a function", "returns the sum of two numbers", "returns a number". These 4 lines of text on the right side of the screen match the strings that are the first arguments of the 'describe' and 'it' blocks from the test code on the left side of the screen.](https://fullstack.instructure.com/courses/523/files/235479/preview)