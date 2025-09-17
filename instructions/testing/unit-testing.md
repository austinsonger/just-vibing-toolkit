# Unit Testing Instructions

## Objective
Write effective unit tests that provide confidence in code correctness, serve as documentation, and enable safe refactoring.

## Context
Use when writing unit tests for new code or when improving test coverage for existing code.

## Guidelines

### 1. Test Structure (AAA Pattern)
- **Arrange**: Set up test data and conditions
- **Act**: Execute the function/method being tested
- **Assert**: Verify the expected outcome

### 2. Test Characteristics
- **Independent**: Tests should not depend on each other
- **Repeatable**: Same results every time they run
- **Fast**: Should execute quickly for rapid feedback
- **Clear**: Easy to understand what's being tested
- **Thorough**: Cover normal cases, edge cases, and error conditions

### 3. What to Test
- **Public Interface**: Focus on public methods and functions
- **Business Logic**: Core functionality and rules
- **Edge Cases**: Boundary conditions and limits
- **Error Conditions**: How code handles invalid inputs
- **Integration Points**: Interactions with dependencies

### 4. Test Organization
- **One Concept per Test**: Each test should verify one specific behavior
- **Descriptive Names**: Test names should explain what they verify
- **Logical Grouping**: Group related tests together
- **Setup/Teardown**: Use proper test fixtures

## Unit Test Template

```javascript
describe('UserService', () => {
  let userService;
  let mockDatabase;

  beforeEach(() => {
    // Arrange - Set up test dependencies
    mockDatabase = {
      findUser: jest.fn(),
      saveUser: jest.fn()
    };
    userService = new UserService(mockDatabase);
  });

  describe('createUser', () => {
    it('should create user with valid data', async () => {
      // Arrange
      const userData = { name: 'John Doe', email: 'john@example.com' };
      const expectedUser = { id: 1, ...userData };
      mockDatabase.saveUser.mockResolvedValue(expectedUser);

      // Act
      const result = await userService.createUser(userData);

      // Assert
      expect(result).toEqual(expectedUser);
      expect(mockDatabase.saveUser).toHaveBeenCalledWith(userData);
    });

    it('should throw error for invalid email', async () => {
      // Arrange
      const invalidUserData = { name: 'John', email: 'invalid-email' };

      // Act & Assert
      await expect(userService.createUser(invalidUserData))
        .rejects.toThrow('Invalid email format');
    });
  });
});
```

## Testing Checklist

- [ ] Test covers happy path scenarios
- [ ] Test covers edge cases and boundary conditions
- [ ] Test covers error/exception scenarios
- [ ] Test is independent and isolated
- [ ] Test has descriptive, clear name
- [ ] Test follows AAA pattern
- [ ] Dependencies are properly mocked
- [ ] Assertions are specific and meaningful
- [ ] Test setup and teardown are handled correctly

## Best Practices

### Test Naming Conventions
- `should_[expected behavior]_when_[condition]`
- `given_[context]_when_[action]_then_[outcome]`
- Use descriptive names that explain the test purpose

### Mocking Guidelines
- **Mock External Dependencies**: Databases, APIs, file systems
- **Don't Mock What You Own**: Avoid mocking your own classes
- **Verify Interactions**: Check that mocks are called correctly
- **Reset Mocks**: Clean state between tests

### Common Test Types
- **State Testing**: Verify object state after operations
- **Behavior Testing**: Verify interactions with dependencies
- **Property Testing**: Verify invariants and properties
- **Parameterized Testing**: Test multiple inputs efficiently

## Common Pitfalls

❌ **Testing Implementation Details**: Testing how something works instead of what it does
❌ **Overmocking**: Mocking everything, including your own code
❌ **Large Test Methods**: Testing too many things in one test
❌ **Unclear Test Names**: Names that don't explain what's being tested
❌ **Fragile Tests**: Tests that break with minor refactoring
❌ **No Edge Case Testing**: Only testing the happy path
❌ **Test Data Builders**: Not using factories or builders for complex test data

## Code Coverage Guidelines

- **Aim for High Coverage**: 80%+ is generally good
- **Quality over Quantity**: Meaningful tests matter more than raw coverage
- **Cover Critical Paths**: Focus on important business logic
- **Don't Game the System**: Don't write tests just to increase coverage numbers