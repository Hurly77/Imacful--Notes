### Next.js Testing Best Practices

​	While there are a lot of packages and libraries to test JavaScript code, Next.js recommends a combination of [Facebook’s `jest`](https://jestjs.io/) test framework, [CircleCI](https://circleci.com) or [GitHub](https://github.com) for automation and integration, and [Cypress](https://www.cypress.io/) for E2E (end-to-end) tests.

​	For file and folder structure, the convention is to place tests in a folder placed in the root directory named `__test__`. Inside the test folder add test configuration files and subdirectories to add separation for the different kinds of tests.

```
root/
..etc
--/__test__
---/unit
---/integration
---/..etc
..etc
```

Use jest mock functions as little as possible, if you feel like there need to be a lot of them try using an integration testing pattern instead of a unit testing pattern.

​	Next.js separates the frontend and backend into individual components and combines (builds) them at run time. Because of that, some developers believe that there should be a higher emphasis on integration testing to ensure the app is working properly when this happens. It’s also common to have light unit tests that are narrow in scope and don’t rely on the the two parts coming together. With that information, it’s common to see some anti-patterns of TDD (test-driven development) like an inverse testing pyramid or the “testing cone”:

![The Evolution of the Testing Pyramid | James Willett](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSxDeeLWJGcG30AtLwggx00dBWQQnCj1DAHrQ&usqp=CAU)

Or the “testing trophy” pattern popularized by [Kent C. Dodds](https://kentcdodds.com/):

![Static vs Unit vs Integration vs E2E Testing for Frontend Apps](https://kentcdodds.com/static/c331ec0658e3d2927db08b6e4946e266/e3189/confidence-coefficient.png)

​	While this approach may seem counter intuitive to the principles of TDD we must understand that the best practices vary for every framework, library, language, etc.. If the application being built requires a higher emphasis on integration over unit testing that doesn’t mean we can’t adhere to TDD principles. You should strive for clear, effective, and many tests with simple unit testing and high impact integration testing. 

​	It’s important to know how your application will be built to be able to test effectively. With Next.js, if you want to test backend logic from a fronted perspective (and vise versa) you need to make sure the appropriate steps and testing pattern are used to follow that flow.





Resources: 

[Jest](https://jestjs.io/)

[Circle CI](https://circleci.com)

[GitHub](https://github.com)

[Circle CI - blog - Next Testing](https://circleci.com/blog/next-testing/)

[Cypress](https://www.cypress.io/)

[GitHub - Next.js - Jest Example](https://github.com/vercel/next.js/tree/canary/examples/with-jest)

[Kent C. Dodds - website](https://kentcdodds.com/)

[Testing JavaScript](https://testingjavascript.com/)

[Kent C. Dodds - blog - Unit VS Integration](https://kentcdodds.com/blog/unit-vs-integration-vs-e2e-tests)

[Log Rocket - blog - Testing](https://blog.logrocket.com/testing-and-error-handling-patterns-in-next-js/)

