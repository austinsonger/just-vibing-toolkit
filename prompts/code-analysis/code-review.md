# Code Review Prompts

## Comprehensive Code Review

```
I need a thorough code review for this [LANGUAGE] [COMPONENT_TYPE] that [PURPOSE].

## Code to Review:
[YOUR_CODE_HERE]

## Review Focus:
Please analyze this code for:
- [ ] Code quality and readability
- [ ] Performance implications
- [ ] Security vulnerabilities
- [ ] Best practices adherence
- [ ] Potential bugs or edge cases
- [ ] Testing considerations
- [ ] Maintainability issues

## Specific Concerns:
[ANY_SPECIFIC_AREAS_OF_CONCERN]

## Context:
- Team size: [TEAM_SIZE]
- Project scale: [PROJECT_SCALE]
- Performance requirements: [PERFORMANCE_REQUIREMENTS]
- Security requirements: [SECURITY_REQUIREMENTS]

Please provide:
1. Overall assessment (1-5 stars)
2. Specific issues with line references
3. Suggested improvements with code examples
4. Positive highlights of good practices
```

## Security-Focused Review

```
Please conduct a security-focused code review of this [LANGUAGE] code:

[YOUR_CODE_HERE]

## Security Checklist:
- [ ] Input validation and sanitization
- [ ] Authentication and authorization
- [ ] Data encryption and protection
- [ ] SQL injection prevention
- [ ] XSS protection
- [ ] CSRF protection
- [ ] Secure error handling
- [ ] Logging security considerations

Focus on potential vulnerabilities and provide specific remediation steps.
```

## Performance Review

```
Please review this [LANGUAGE] code for performance issues:

[YOUR_CODE_HERE]

## Performance Context:
- Expected load: [LOAD_DESCRIPTION]
- Current performance: [CURRENT_METRICS]
- Target performance: [TARGET_METRICS]
- Hardware constraints: [HARDWARE_CONSTRAINTS]

## Analysis Needed:
- Time complexity analysis
- Space complexity analysis
- I/O optimization opportunities
- Caching possibilities
- Database query optimization
- Algorithm improvements

Provide specific optimization suggestions with before/after code examples.
```

## Refactoring Review

```
I want to refactor this [LANGUAGE] code to improve [SPECIFIC_GOALS].

## Current Code:
[YOUR_CODE_HERE]

## Refactoring Goals:
- [ ] Improve readability
- [ ] Reduce complexity
- [ ] Better separation of concerns
- [ ] Eliminate code duplication
- [ ] Improve testability
- [ ] [CUSTOM_GOALS]

## Constraints:
- Cannot change public API
- Must maintain backward compatibility
- Performance cannot degrade
- [ADDITIONAL_CONSTRAINTS]

Please suggest a refactoring plan with step-by-step approach and code examples.
```

## Architecture Review

```
Please review the architecture and design patterns in this [LANGUAGE] [SYSTEM_TYPE]:

[YOUR_CODE_HERE]

## Architecture Focus:
- [ ] Design pattern usage
- [ ] SOLID principles adherence
- [ ] Separation of concerns
- [ ] Dependency management
- [ ] Scalability considerations
- [ ] Maintainability
- [ ] Extensibility

## System Context:
- System type: [WEB_APP/API/SERVICE/ETC]
- Expected growth: [GROWTH_EXPECTATIONS]
- Team structure: [TEAM_STRUCTURE]
- Technology stack: [TECH_STACK]

Provide architectural improvement suggestions with design pattern recommendations.
```

## Junior Developer Review

```
This code was written by a junior developer. Please provide mentoring-focused feedback:

[YOUR_CODE_HERE]

## Teaching Focus:
- Explain best practices with reasoning
- Suggest learning resources
- Highlight good practices they used
- Provide gentle guidance on improvements
- Include code examples for better approaches

## Mentoring Goals:
- Build confidence
- Improve coding skills
- Develop good habits
- Understanding of principles
- Growth mindset

Please be encouraging while providing constructive feedback.
```

## Legacy Code Review

```
Please review this legacy [LANGUAGE] code for modernization:

[YOUR_CODE_HERE]

## Legacy Context:
- Original creation date: [DATE]
- Last major update: [DATE]
- Current issues: [KNOWN_ISSUES]
- Dependencies: [DEPENDENCY_LIST]

## Modernization Goals:
- [ ] Update to modern language features
- [ ] Improve error handling
- [ ] Add proper logging
- [ ] Improve documentation
- [ ] Add unit tests
- [ ] Security updates
- [ ] Performance improvements

Provide a modernization roadmap with priority levels and estimated effort.
```