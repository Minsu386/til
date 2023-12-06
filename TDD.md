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
![](Meta/Screen%20Shot%202023-12-05%20at%2011.04.10%20PM.png)

In this example, we use vanilla JavaScript to test if our `multiply` function behaves how we expect it to behave.

There are many other ways we could have written this code, but this is a basic example of how we may approach it on our own. In this small example, the "tests" we created manually are not intuitive to read, and it is hard to track where all the variables used are defined. Two engineers can implement the same tests with different styles, which makes reading specs like this a lot harder. And even if the `multiply` function is not working as expected, we may not realize it based on how these tests are designed. 

Before moving on and learning a better way to write tests, try to write tests similar to the tests above for the `reverseString` function we used in the last example.

Review the following video, which starts where we left off from the "Identifying Expectations" video in the previous section:
[Manual Testing Example](https://youtu.be/JSMGdDAxZJ4)


# Testing Frameworks
----

A testing framework consists of pre-written JavaScript code designed specifically for testing. The goal of a testing framework is to add structure, readability, and make testing easier.

Keep in mind some testing frameworks achieve the same goals, while others are designed for different types of tests and environments. Here is a list of a few popular testing frameworks:

- [Jasmine](https://jasmine.github.io/) - a great framework for learning testing, which we will use in Foundations     
- [Mocha](https://mochajs.org/)     
- [Jest Links to an external site.](https://facebook.github.io/jest/)- developed by Facebook and it is used with [React](https://reactjs.org/)     
- [Tape](https://github.com/substack/tape) - known in the community for being minimal and simple    

Testing frameworks use natural language constructs to express the desired behavior and outcome of a test. In the case of most commonly-used testing frameworks, which were developed by English speakers, using natural language constructs means using language that resembles English sentences. For example, here is one of the expectations we wrote for our multiply function:

"We expect multiply to be a function."

The following code is how the same expectation can be written using the Jasmine testing framework:

![](https://lh7-us.googleusercontent.com/W_aj4GE1dNr8hnGRRuZoDJxbIp34zMSPvxpzGi34IHmek1nPJymufbh046e1nnaCSJdCzMHq31cWLS1NS6XfCCSZBk-wuzP7R9fDymtZJuWsL2aYg_FH--yM2x-UuPNfdis4H3wGIStHdEBgcvn24g)

![](https://lh7-us.googleusercontent.com/sIqAJcp9CLFfNdQXuLvgreLkuAwMWC12x650dvuGxBmHF7SPVcWqyJpoeYJY5oI96oH73LwkAa10RgoE-127pBQnVG_K6MEtEKWTWQF39t3p9QwJf34eJZATMx1Fomuc6De950LvYU2KjMFMheUwSg)

![](https://lh7-us.googleusercontent.com/8MvumcdimnR3SO1WtVJqA-AH4b5w2V3HkxzKjH1nJxaj5Cvy8ErNlDhhSEXf03hYqosqjBl4Znd0glS0DOEVeOeAXJjmY9OIwNuI9kk-eKYH2rdIl-QqFvweVxi9_g_pq3h0_YuV1KFaltGsi3zBAg)


![](https://lh7-us.googleusercontent.com/0OTQxL_oL2XGqcj3WWqP8TquGeSb4bHBZXyZa5x8xbBAH0kRhrmoepvdauiv3mmLQft8ThKS-Ls9dIw8LJQAV9nQUH2Bjt2Cb7Uwo6zn_H1I8Lq9bfYpRxG562XRa62-gziIXbpMU0XTJ_-6WhwcsQ)

![](https://lh7-us.googleusercontent.com/pN0BfAxoGBV90W-pzSXUsB6ObDo4oGIPGQ8AUR3SeVMYM31GK76qwWMdnbyoYKI9hj1GtwqF9lZbXY8gbATSchrMOMSh8v1pGfu6B5lujBGl0WrLKJJ8ZzH5Ss85JCjqgHML_ydGhajiznU_Zhe8QA)Link to CodePen: [Jasmine Spec Runner Example](https://codepen.io/FullstackAcademy/pen/BYwQaP/)  You can use this CodePen to experiment with causing the test specs to fail in different ways.**

# Test Suites and Specs
----

A "unit test", also referred to as a spec, focuses on a small, meaningful chunk of code and determines if the code behaves as expected. If a spec fails, the output is displayed with red text. A passing spec has green text.

Jasmine uses the [it](https://jasmine.github.io/api/2.6/global.html#it) function to indicate a single unit test and contains the expectations we create for our test.

The following [Youtube VIDEO](https://www.youtube.com/watch?v=7M5tMII_aao) picks up where we left off from our "manual test specs" and demonstrates how to construct specs using the Jasmine Framework:

The following code is a full unit test that evaluates a portion of our multiply function:

![](https://lh7-us.googleusercontent.com/UsRe28EN2x8rNor3OllixmD_ENUNXFuowMRZr61WpElOEpksWEqyc9gGuvLn99UkPqrT-ikmLtn18Dho1i7hLPEG2Gj1cTkYAV_5zcIXOU_q2GDisOu3HP7R0NiIYuuEEjOnVCAL-wYC8P1h6tiS9A)

A new matcher was used: [toBeDefined](https://jasmine.github.io/api/3.0/matchers.html#toBeDefined) 

[Links to an external site.](https://jasmine.github.io/api/3.0/matchers.html#toBeDefined). It does exactly what you may expect. It will return true and "pass" the expectation if the variable (or function) multiply is defined, or it will return false and fail the test if multiply is undefined.

We passed the it function two arguments. Both of these arguments are described in the Jasmine documentation: [Jasmine > Global Methods > it](https://jasmine.github.io/api/2.6/global.html#it) The two arguments are:

- the description of the test spec (first argument, type: string)
    
- the function that executes the expectations (second argument, type:function)
    

In the example, we "expect" that multiply is defined and that it is a function. The initial string description passed to the it function is important, since it adds structure to our tests and makes it easier to locate and determine what is tested without reading the entire code base.

It is important to note that each spec needs expectations. Without expectations, there is nothing to test. Expectations accept a value generated from the code we are testing and compare it using a matcher. The matcher contains the value we expect our code to produce. This is the value we pre-determine when writing our expectation.

![](https://lh7-us.googleusercontent.com/CEyKrtOSbEFxe_UcZLc2J186sAMbf_RPVZWA1Jvj6mo5IoZCZ61DkFELrX144lXdXyhguuAtuxzPlXrZzCleksIgYzPJd4VGqpOhn1fnUWwGQOjSWofeZppjJdbaFnODpcsuxNT-T3HfAVRIrCXCgQ)

![](https://lh7-us.googleusercontent.com/K2QN8RCzfvxaTSYx8UC2eUoC0USiMq0dCfP31PD1dcn9tx1dzEKyI4HcLrJcQsXrUF-ybFm9iBuMYP8TK6WMfaulUXqFatf_GBMyDjYi5b5SKtEtiK7KF-08ugRLANtmVnrQk0yb5KVKApOZywt8xQ)

The reverseString function in the example below accepts a string argument and returns the string argument in reverse order. The test spec evaluates the return value of the reverseString function.

Challenge: Review the following code. How would you adjust the reverseString function so it matches the expectation in the test spec?

![](https://lh7-us.googleusercontent.com/OumPHdeY4SruWruQXs1nlOb3tkcRJpYJIWJufM3RfLskgh52VwSwC7vCqkPs8sGgIAXygtevgXRNDgYHfS-62a6McqoGsDoD8jge-2e56qIBPSN9zzGE7lAAxPJGpjKcloT_N9MVCv-uHoV7OjfCTw)


![](https://lh7-us.googleusercontent.com/u4G3Q8zOYojEB-bb2X-G8Yt7mYV7af2vQeN5x4ntyw0SwPJ1Q3e_hYPcpuY_l2lNdCZUnvvy1I4i3A-OVXEHXfztpWKOGNsU4cAfEn_PMXxsIMNRinSMPfoLVl9uZHS8_jykPkFB_HYRR-bIS0GmfA)

Link to exercise in CodePen: [reverse-exercise](https://codepen.io/FullstackAcademy/pen/XZegqq)

![](https://lh7-us.googleusercontent.com/uDhE4ZgKt88gvLyNgZ7zAMDyd_uH2nni0kKvz30yxaIOqFBi3C0p4QsikMKOlrY5OD5nPDra9lckiJXBF89AF0JvsXz67SF7PaIoIkPDDXihDxGhQX37zJsBeXr5_IIHaO-9pmWbGVJchuinVqC0zg)

Link to solution in CodePen: [reverse-solution](https://codepen.io/FullstackAcademy/pen/EQwvBV/)

**

![](https://lh7-us.googleusercontent.com/OVgtE-mX0YtvcmHskKEc9fMwY-_N53IVG4osXfmvesHeP8LdxyWXDdDeNyR-YILJrxo8pJhnpjKRM6RTpKmYU48dlBPB0p8W0w6Ud9NbYdb5qcDJEYW640pu-K361t0GVQnmGo0M7Jde-qU9OKHanQ)

![](https://lh7-us.googleusercontent.com/NwvIlzS0BNb02Xsy-Q4A3TpL_Jz2J-uxEwqVIWnzIrDDXPgSqFWB6qxUV9kd-TyaY9oL6GRgIZgRBBCzf6PglB5ss1K-jHOCLSfLDMRFTa7KYo0KYVUI_HTj5BJ1OuEfpX3mOB55cFkiJEa8LkXTUA)

  

![](https://lh7-us.googleusercontent.com/D1ea3bFh3X_IzKUuRaLI01UqYf1Dtkqj80tiC09fYZu34EtcHDnWpVumFURdapwXg5J79OJMa90d2ivUZ8sJGHmhdSz6iW9ymyCkrw9V6P7aa-Yu5EjrBSp1IAOLz3Uih4FFnDhcWUSLJpfgKHJnmQ)

Link to exercise in CodePen: [Multiply Test Specs](https://codepen.io/FullstackAcademy/pen/zREwxv) 

The test suite created for the multiply function, will make locating the multiply functions test specs easier in the future, especially as our code base grows. Furthermore, spec-runners, the code that runs our test specs, can have additional functionality that allows us to run specific tests or groups of tests. Creating units and suites makes it possible to specify which specs to run and focus on.

Challenge: Create the expectations for the remaining specs. Do not over think the expectations, you can use the previous examples and matchers to complete the specs.

![](https://lh7-us.googleusercontent.com/bEWDiSurNLo35KXuTcL-nicSEe3rfK5AT4ARB8PR9bpGGac62Xaiic3DY5NlY056Os1WS43z379o_lMVZl1l9UCE66EmTHrkGS-SBBxTWNdDq7dOSSfxtnHWikSCxAJ6c3L55RIqpfDTL-G3jNWTwA)

Link to solution in CodePen:  [multiply-solution](https://codepen.io/FullstackAcademy/pen/PQJKLQ/)**

