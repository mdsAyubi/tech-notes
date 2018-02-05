# Clean Code for Java

## Comments

1. Boy Scout Rule - Leave your code in a better state than you found it.
1. Static code analyzer(eg SONARQUBE).
1. Commented code - eliminate.
1. Meaningful labelling and comments for every commit.
1. Dead code - eliminate.
1. Obvious comments - eliminate.
1. Grammar and punctuation - write well.
1. Comments are failures to express the logic. Make sure they are needed when they are needed.
1. Specification pattern for complicated rules which need hard to understand `if` conditions.
1. Using `assert` in the code - for code in the same context, i.e calls which do not transcend boundaries.

## Error Handling

1. Arrow code - eliminate in favor of exceptions.
1. Usage of `boolean`, `null`, `int` for error handling - avoid.
1. Use exception handling for termination flows and not for alternate flows.
1. Usage of flags to signal error conditions should be avoided.
1. Replace exception with and `if` test. Typically in a boundary scenario where the library or something can throw some known exception based on what we sending.
1. Propagate exceptions upwards as much as possible.
1. Empty catch blocks - eliminate.
1. Log and rethrow in the catch block - avoid or eliminate. Better to let the calling code decide.
1. DRY - Don't duplicate code.
1. Nested try catch - promote them as method.

## Functions

1. Nesting - avoid.
1. Magic numbers or hard coded stuff.
1. Don't create huge constant classes. Decompose it.
1. Use properties file for constants.
1. Don't repeat yourself.
1. Avoid long methods. More than 6 lines is already long. Should fit in the iDE screen.
1. The name should tell everything.
1. Don't mix levels of abstraction.
1. Boolean parameters for functions - avoid.
1. Max two params for functions.
1. Avoid output parameters.
1. No flag parameters.
1. Reveal intent in the function name.
1. Test exception instead of normal code - alternate flow before the main flow.
1. Null pattern(objects which represent absence) to avoid unnecessary `null` checks.
1. Avoid null as parameters.
1. Use multiple returns judiciously. Only when it enhances readability.
1. Use early returns for alternate flows.
1. Cyclomatic complexity - No of branches < 10.
1. CQS - Command Query Segregation - A function should not be a command and query both.
    1. Query doesn't have side effects.
    1. A command changes the system state.

## Data Structures

1. Hide the boundary - Don't expose your data structures. Better to wrap in a class and use that with meaningful methods.
1. Encapsulate collections - Have more control on the APIs.
1. Use collection interfaces instead of concrete classes when passing collections around.
1. Remove null checks using optionals.

## Unit Test

1. Easy test - avoid.
1. Functions with CC of some number should have tests.
1. Write tests for bugs - then fix the code.
1. The 3A pattern
1. One assert per test - test one concept.
1. Use data driven tests when testing multiple values for a concept.
1. Test the scenarios. Not the methods.
1. Unit tests as documentation for the APIs.
1. One fixture per class.
1. 3A + Setup and Teardown.
1. Keep tests clean.
1. Good test
    1. Test as documentation
    1. Should look plain and vanilla.
    1. While/Switch/If/Do - Avoid logic in tests.
    1. Strive for BDD
    1. KISS - Keep it short and simple.
1. Don't test private methods.
1. Avoid duplicate code.
1. Don't expect generic exceptions.
1. Write tests before bug fix.
1. Don't write bug id in the test name.
1. Flat code.
1. Minimize un-testable code.

## Class

1. Static methods - avoid generally.
1. No class should depend on no class.
1. Boundary layer should be as thin as possible.
1. MVC, MVP, MVVM - Make use of these UI patterns.
1. Organize the code using the newspaper metaphor. Public first. Dependency should be top down.
1. Use constructor only when it is necessary.
1. DBC - Design By Contract
    1. Contract
        1. Precondition - Expectations from the caller. Don't change preconditions while overriding.
        1. Post condition - Expectations from the callee.
        1. Invariant - Things which remain constant.
    1. Logic
1. LSP - If it works for base, it should work for derived.
1. Down casting - Avoid. Useful sometimes in boundary layer.
1. If you have to downcast, wrap it and localize it at the source.
1. Type checking - Avoid. Localize at the source.
1. Interface segregation principle - if the code accepts and interface, it should be applicable to all the instances of the interface. Build specific interfaces. Which makes more sense.
