# Code Review Instructions

## Objective
Conduct thorough, constructive code reviews that improve code quality, share knowledge, and maintain team standards.

## Context
Use these instructions when reviewing pull requests or when asking an AI assistant to help review code.

## Guidelines

### 1. Code Quality Assessment
- **Readability**: Is the code easy to understand and follow?
- **Maintainability**: Can the code be easily modified in the future?
- **Consistency**: Does it follow team/project coding standards?
- **Simplicity**: Is the solution appropriately simple (not over-engineered)?

### 2. Functionality Review
- **Correctness**: Does the code do what it's supposed to do?
- **Edge Cases**: Are boundary conditions and error cases handled?
- **Performance**: Are there obvious performance issues?
- **Security**: Are there potential security vulnerabilities?

### 3. Design and Architecture
- **Design Patterns**: Are appropriate patterns used correctly?
- **Separation of Concerns**: Is functionality properly separated?
- **Dependencies**: Are dependencies managed appropriately?
- **Extensibility**: Is the code designed for future changes?

### 4. Testing
- **Test Coverage**: Are there appropriate tests for the changes?
- **Test Quality**: Are tests meaningful and well-written?
- **Test Types**: Are unit, integration, and e2e tests considered?

## Review Checklist

- [ ] Code compiles and runs without errors
- [ ] All tests pass
- [ ] Code follows style guidelines
- [ ] Functions/methods are reasonably sized
- [ ] Variables and functions have meaningful names
- [ ] Comments explain "why" not "what"
- [ ] Error handling is appropriate
- [ ] No obvious security vulnerabilities
- [ ] Performance considerations are addressed
- [ ] Documentation is updated if needed

## Best Practices

### Giving Feedback
- **Be Constructive**: Focus on the code, not the person
- **Be Specific**: Point out exact issues and suggest improvements
- **Prioritize**: Distinguish between must-fix and nice-to-have
- **Explain Why**: Help the author understand the reasoning
- **Acknowledge Good Code**: Praise well-written sections

### Common Review Comments
- "Consider extracting this into a separate function for better readability"
- "This could be vulnerable to SQL injection - consider using parameterized queries"
- "The variable name 'data' is too generic - could you make it more descriptive?"
- "This function is doing too many things - consider splitting it up"
- "Great use of the Strategy pattern here!"

## Common Pitfalls

❌ **Nitpicking**: Focusing on minor style issues instead of substantial problems
❌ **Not Running the Code**: Reviewing without actually testing the changes
❌ **Being Vague**: Comments like "this looks wrong" without explanation
❌ **Blocking on Preferences**: Holding up PRs for personal preferences vs standards
❌ **Ignoring Tests**: Not reviewing test quality and coverage

## Example Review Process

```
1. Read the PR description and understand the context
2. Review the overall approach and design
3. Examine the code changes line by line
4. Check for test coverage and quality
5. Consider security and performance implications
6. Verify documentation updates
7. Provide specific, actionable feedback
8. Approve when ready or request changes with clear guidance
```