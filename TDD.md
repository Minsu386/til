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
/* Code to Test */
const add = (x, y) => {
  return x + y;
};
describe("add function", function() {
  it("is a function", function() {
    expect(add).toBeDefined();
    expect(typeof add).toBe("function");
  });
  
it("returns a number", function() {
  expect(typeof add(4, 5)).toBe("number");
  expect(typeof add(10, 20)).toBe("number");
});

  it("returns the sum of two numbers", function() {
    expect(add(20, 40)).toBe(60);
    expect(add(50, 50)).toBe(100);
  });
});
```

Image of the test suite running in CodePen:
![](Meta/Pasted%20image%2020231205225710.png)



# ID Expectations
----
[ID Expectations](https://youtu.be/88ilXhXDo6Y)

What do you expect the following function `multiply` does?

```
const multiply = (x,y) => {  return x * y;}multiply(5,10);
```

Let us analyze how we expect our `multiply` function to behave.

1. We expect `multiply` to return a number.
2. When we invoke `multiply (5,10)`, we expect the value 50 to be returned.
3. We expect `multiply` to be a function.
4. We expect the `multiply` function is called with number arguments and not strings. `multiply('5', '10')`.

Below is another example function. Read the code and make notes on what you expect it to do:

```
const reverseString = (str) => {  let reversedString = "";  for(let lastIndex = str.length -1; lastIndex >= 0; lastIndex--) {    reversedString += str[lastIndex];  }  return reversedString;}reverseString('StrangerThings');
```
<details> 
  <summary>Hint: Expectations for reversestring</summary>
- We expect `reverseString` to be a function.
- We expect `reverseString` to return a string.
- We expect `reverseString` ('StrangerThings') to return `'sgnihTregnartS'`.
- We expect `reverseString` is called with a **string**
</details>

When you write tests, you can use expectations as your guide for what to test. Next, we will put together our first "manual" unit test using the `multiply` function as an example.

# Manual Testing
-----

In the Identify Expectations section, we outlined expectations for a `multiply` function in simple English. How can we test our expectations of multiply using pure JavaScript? A comparison operator would be very useful for this task: [Expressions and Operators - JavaScript | MDNLinks to an external site.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#equality_operators).

Review the manual testing example code below:
