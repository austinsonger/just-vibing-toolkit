# Prompts 💬

A collection of reusable prompt templates for various coding scenarios. These prompts are designed to get better, more focused responses from AI coding assistants.

## Categories

### 🔍 Code Analysis
- [**Code Review Prompts**](code-analysis/code-review.md) - Comprehensive code review requests
- [**Bug Detection**](code-analysis/bug-detection.md) - Finding potential issues and bugs
- [**Performance Analysis**](code-analysis/performance-analysis.md) - Identifying performance bottlenecks
- [**Security Audit**](code-analysis/security-audit.md) - Security vulnerability assessment

### 🏗️ Architecture & Design
- [**System Design**](architecture/system-design.md) - High-level architecture planning
- [**API Design**](architecture/api-design.md) - REST and GraphQL API design
- [**Database Schema**](architecture/database-schema.md) - Database design and optimization
- [**Design Patterns**](architecture/design-patterns.md) - Applying appropriate patterns

### 💻 Code Generation
- [**Function Creation**](code-generation/function-creation.md) - Creating specific functions
- [**Class Design**](code-generation/class-design.md) - Object-oriented design
- [**Algorithm Implementation**](code-generation/algorithm-implementation.md) - Specific algorithms
- [**Boilerplate Code**](code-generation/boilerplate.md) - Common code structures

### 🧪 Testing
- [**Unit Test Generation**](testing/unit-tests.md) - Creating comprehensive unit tests
- [**Integration Tests**](testing/integration-tests.md) - Testing component interactions
- [**Test Data Creation**](testing/test-data.md) - Generating test datasets
- [**Mock Implementation**](testing/mocking.md) - Creating effective mocks

### 📝 Documentation
- [**Code Documentation**](documentation/code-documentation.md) - Inline comments and docstrings
- [**API Documentation**](documentation/api-documentation.md) - REST API documentation
- [**README Creation**](documentation/readme.md) - Project documentation
- [**Technical Writing**](documentation/technical-writing.md) - Technical specifications

### 🐛 Debugging
- [**Error Diagnosis**](debugging/error-diagnosis.md) - Understanding error messages
- [**Root Cause Analysis**](debugging/root-cause-analysis.md) - Finding underlying issues
- [**Performance Debugging**](debugging/performance-debugging.md) - Solving performance issues
- [**Memory Issues**](debugging/memory-issues.md) - Memory leaks and optimization

### 🚀 Optimization
- [**Code Optimization**](optimization/code-optimization.md) - Improving code efficiency
- [**Database Optimization**](optimization/database-optimization.md) - Query and schema optimization
- [**Algorithm Optimization**](optimization/algorithm-optimization.md) - Better algorithmic approaches
- [**Resource Usage**](optimization/resource-usage.md) - Memory and CPU optimization

## How to Use Prompts

1. **Choose the appropriate prompt** for your task
2. **Customize variables** in brackets `[like this]`
3. **Add context** specific to your situation
4. **Iterate** based on the initial response

## Prompt Template Format

```
## Context
[Background information about the task]

## Objective
[Clear goal of what you want to achieve]

## Requirements
- [Specific requirement 1]
- [Specific requirement 2]
- [Specific requirement 3]

## Input
[Your code, error message, or relevant information]

## Expected Output
[Description of what you expect to receive]
```

## Quick Start Examples

### Code Review
```
Please review this [language] code for [specific concerns]. 
Focus on [areas of concern] and provide specific suggestions for improvement.

[Your code here]
```

### Bug Fix
```
I'm encountering [error description] in my [language] application.
Here's the error message: [error message]
Here's the relevant code: [code snippet]

Please help me identify the root cause and suggest a fix.
```

### Performance Optimization
```
This [function/query/algorithm] is performing slowly with [context about data size/load].
Current performance: [metrics]
Target performance: [desired metrics]

[Your code here]

Please suggest optimizations.
```

## Best Practices

- **Be Specific**: Include exact error messages, requirements, and context
- **Provide Examples**: Show what you've tried or what good output looks like
- **Set Constraints**: Mention any limitations or requirements
- **Ask for Explanations**: Request reasoning behind suggestions
- **Iterate**: Use follow-up prompts to refine solutions