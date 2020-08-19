# 11. TESTING

It is a good rule to always ask yourself if **what you want** to test can be done using more lightweight test approaches such as unit tests or with a lower-level approach

Three steps - keep them short

* Set up the data
* Perform a discrete set of actions
* Evaluate the results

{% hint style="info" %}
If you keep short, no problem. If you have issues and problems with tests try "[how to overcome race conditions](https://www.selenium.dev/documentation/en/webdriver/waits/)" for later reading
{% endhint %}

By keeping your **tests short** and using the **web browser** **only** when you have absolutely **no** **alternative,** you can have many tests with _**minimal flake.**_

* A distinct advantage of Selenium tests is their inherent ability to test all components of the application, from backend to frontend, from a user’s perspective.

## [Types of testing](https://www.selenium.dev/documentation/en/introduction/types_of_testing/)

### Acceptance testing \(sub functional testing\)- _"Are we building the right product?"_

* Used to determine if a feature or system meets the customer expectations
* Selenium can simulate user expected behaviour

### Functional testing - _"Are we building the product right?"_

* determine if a feature or system functions properly without issues; all scenarios are covered and that the system does what’s supposed to do
* tests without errors, in a usable way \(correct redirections\), acessible and matching specs
* can be done directly with Selenium by simulating expected returns

### Performance testing - measure how well an application is performing

* Load Testing
  * how well the application works under different defined loads
* Stress testing - _**JMeter**_
  * how well the application works under stress

### Regression testing

* generally done after a change, fix or feature addition
* Ensure that the change has not broken any of the existing functionality, some already executed tests are executed again

### Test driven development \(TDD\)

* an iterative development methodology in which tests drive the design of a feature
* Each cycle starts by creating a set of unit tests that the feature should eventually pass \(they should fail their first time executed\)

### Behaviour-driven development \(BDD\) - unit testing

* an iterative development methodology based on the above TDD, in which the goal is to involve all the parties in the development of an application
* Each cycle starts by creating some specifications \(which should fail\). Then create the failing unit tests \(which should also fail\) and then do the development
* specification language: Gherkin
* A set of tools are currently available to write the specifications and match them with code functions, such as Cucumber or SpecFlow
* A set of tools are built on top of Selenium to make this process even faster by directly transforming the BDD specifications into executable code. Some of these are JBehave, Capybara and Robot Framework

