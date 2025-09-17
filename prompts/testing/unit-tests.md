# Unit Test Generation Prompts

## Comprehensive Unit Test Suite

```
Please generate comprehensive unit tests for this [LANGUAGE] [CLASS/FUNCTION]:

## Code to Test:
[YOUR_CODE_HERE]

## Testing Requirements:
- Testing framework: [FRAMEWORK_NAME]
- Mock library: [MOCK_LIBRARY]
- Coverage target: [PERCENTAGE]%
- Test style: [BDD/TDD/CLASSICAL]

## Test Coverage Needed:
- [ ] Happy path scenarios
- [ ] Edge cases and boundary conditions
- [ ] Error handling and exceptions
- [ ] Input validation
- [ ] State changes (if applicable)
- [ ] Integration with dependencies
- [ ] Performance considerations

## Dependencies to Mock:
[LIST_DEPENDENCIES_TO_MOCK]

Please generate:
1. Test setup and teardown
2. Individual test methods with descriptive names
3. Mock configurations
4. Test data builders/factories
5. Assertions that verify behavior and state
```

## BDD-Style Test Generation

```
Generate BDD-style tests for this [LANGUAGE] [COMPONENT]:

[YOUR_CODE_HERE]

## BDD Scenarios:
Please create tests following the Given-When-Then format:

- **Given** [initial state/context]
- **When** [action/trigger]
- **Then** [expected outcome]

## User Stories:
[PROVIDE_USER_STORIES_OR_REQUIREMENTS]

## Test Framework:
[CUCUMBER/JEST/RSPEC/ETC]

Generate feature files and step definitions with clear, business-readable language.
```

## Test Data Generation

```
I need test data and fixtures for testing this [DOMAIN/FEATURE]:

## Data Requirements:
- Entity type: [ENTITY_TYPE]
- Data volume: [SMALL/MEDIUM/LARGE]
- Relationships: [DESCRIBE_RELATIONSHIPS]
- Constraints: [BUSINESS_RULES_OR_CONSTRAINTS]

## Test Scenarios:
- Valid data scenarios
- Invalid data scenarios
- Edge cases (empty, null, boundary values)
- Complex object graphs
- Temporal data (dates, times)

## Output Format:
- [ ] JSON fixtures
- [ ] Factory methods
- [ ] Builder pattern classes
- [ ] Database seed scripts
- [ ] Mock data generators

Generate realistic test data that covers all scenarios.
```

## Mock and Stub Generation

```
Please create mocks and stubs for testing this [LANGUAGE] component:

## Component Under Test:
[YOUR_CODE_HERE]

## Dependencies to Mock:
[LIST_EXTERNAL_DEPENDENCIES]

## Mock Requirements:
- Mock framework: [FRAMEWORK_NAME]
- Verification style: [STRICT/LENIENT]
- Mock scope: [UNIT/INTEGRATION]

## Mock Behaviors Needed:
- [ ] Return specific values
- [ ] Throw exceptions
- [ ] Verify method calls
- [ ] Simulate delays/timeouts
- [ ] State-based testing
- [ ] Sequence verification

Generate complete mock setup with verification examples.
```

## Property-Based Test Generation

```
Generate property-based tests for this [LANGUAGE] function:

[YOUR_CODE_HERE]

## Properties to Test:
- [ ] Function invariants
- [ ] Input/output relationships
- [ ] Associative properties
- [ ] Commutative properties
- [ ] Identity properties
- [ ] Inverse operations

## Property Testing Framework:
[QUICKCHECK/HYPOTHESIS/FAST-CHECK/ETC]

## Input Generators:
Please create generators for:
[DESCRIBE_INPUT_TYPES_AND_CONSTRAINTS]

Generate property tests that verify mathematical and logical properties.
```

## Integration Test Generation

```
Create integration tests for this [SYSTEM_COMPONENT]:

## System Under Test:
[YOUR_CODE_HERE]

## Integration Points:
- Database: [DATABASE_TYPE]
- External APIs: [LIST_APIS]
- File system: [FILE_OPERATIONS]
- Message queues: [QUEUE_SYSTEMS]
- Third-party services: [EXTERNAL_SERVICES]

## Test Environment:
- Containerization: [DOCKER/TESTCONTAINERS]
- Test database: [APPROACH]
- External service mocking: [WIREMOCK/ETC]

## Test Scenarios:
- [ ] Successful integrations
- [ ] Network failures
- [ ] Service unavailability
- [ ] Data consistency
- [ ] Transaction rollbacks
- [ ] Timeout handling

Generate complete integration test suite with environment setup.
```

## Performance Test Generation

```
Generate performance tests for this [LANGUAGE] [COMPONENT]:

[YOUR_CODE_HERE]

## Performance Requirements:
- Response time: [TARGET_TIME]
- Throughput: [REQUESTS_PER_SECOND]
- Memory usage: [MEMORY_LIMIT]
- Concurrent users: [CONCURRENCY_LEVEL]

## Performance Testing Tool:
[JMETER/K6/GATLING/BENCHMARK_FRAMEWORK]

## Test Scenarios:
- [ ] Load testing (normal traffic)
- [ ] Stress testing (peak traffic)
- [ ] Spike testing (sudden load increases)
- [ ] Volume testing (large data sets)
- [ ] Endurance testing (extended periods)

Generate performance test scripts with metrics collection and assertions.
```