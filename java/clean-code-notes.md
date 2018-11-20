# Rules

1. See where the if conditions fall. Are they technical/logical or are they domain rules. Promote complicated conditions to a `isEligible` kind of function.
1. Boundary Logic, Controller Logic and Domain Logic.
1. Code flows should not be dependent on `catch` logic. Use if conditions instead. Don't use try/catch for alternate flows. Use them only for termination flows.
1. Focus on stuff with higher CC for testing/modernizing efforts.
1. Tests
   1. Unit Test - XUnit
   1. Integration Test - XUnit
   1. API Test - SOAP UI
   1. Automation Tests - Selenium
   1. Manual Test - Humans
1. The 3A Pattern
   1. Arrange - Prepare input
   1. Act - Call method
   1. Assert - Verify
1. XUnit patterns - Book
1. Extreme Programming Explained
1. Cucumber for BDD
1. Pyramid tests
   1. Unit tests
   1. Integration
   1. API
   1. Automation
   1. Manual
1. Ice Cream Cone
   1. Manual
   1. Automation
   1. API
   1. Integration
   1. Unit tests
1. Dev QA scenario - Utopia.
1. What Unit Tests Don't Do
   1. Talk to DB
   1. Network calls
   1. Touch the file system
   1. Need special things to run it.
1. Hexagonal Architecture - Pure domain layer. Everything else built around it.
1. Domain Driven Design
   1. Ubiquitous language - Common language
   1. A facade co-ordinates between the domain(logic heavy) and DAO layer.
1. Tower of Babylon
1. TDD - Test driven design.
   1. Make it fail.
   1. Make it work.
   1. Make it better.
