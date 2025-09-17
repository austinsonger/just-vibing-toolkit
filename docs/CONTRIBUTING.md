# Contributing to Just Vibing Toolkit 🤝

We welcome contributions from the community! Whether you're adding new prompts, templates, chatmodes, or improving documentation, your contributions help make AI-assisted development better for everyone.

## Ways to Contribute

### 🤖 Chatmodes


### 💬 Prompts


### 🛠️ Templates


### 🔄 Workflows


### 📝 Documentation


### 🐛 Bug Reports & Feature Requests


## Getting Started

### 1. Fork the Repository

Click the "Fork" button on the GitHub repository page to create your own copy.

### 2. Clone Your Fork

```bash
git clone https://github.com/austinsonger/just-vibing-toolkit.git
cd just-vibing-toolkit
```

### 3. Create a Branch

```bash
git checkout -b feature/your-contribution-name
```

## Contribution Guidelines
### Content Quality Standards
#### Chatmodes
- **Clear Instructions**: Provide specific, actionable guidance
- **Focused Scope**: Target specific use cases or domains
- **Examples**: Include practical usage examples
- **Consistent Format**: Follow the established template structure

#### Prompts
- **Effective Templates**: Test prompts and verify they produce good results
- **Clear Placeholders**: Use consistent placeholder naming (`[LANGUAGE]`, `[DESCRIPTION]`, etc.)
- **Context Guidance**: Explain when and how to use each prompt
- **Variations**: Provide variations for different scenarios

#### Templates
- **Complete Structure**: Include all necessary files and configurations
- **Documentation**: Provide setup instructions and usage guides
- **Best Practices**: Follow industry standards and conventions
- **Customization**: Use clear placeholders for customization

#### Documentation
- **Clear Writing**: Use simple, accessible language
- **Practical Examples**: Include working code examples
- **Step-by-Step**: Provide detailed instructions
- **Up-to-Date**: Ensure accuracy and relevance

### File Organization
```


```

### Naming Conventions
- **Files**: Use kebab-case (`my-new-template.md`)
- **Directories**: Use kebab-case (`code-generation/`)
- **Placeholders**: Use UPPER_CASE (`{{PROJECT_NAME}}`)
- **Variables**: Use bracket notation (`[LANGUAGE]`)

## Submission Process

### 1. Create Your Content
Follow the appropriate template for your contribution type:

#### For Chatmodes
```markdown
# [Mode Name] [Emoji]

## Chatmode Instructions

```
[Detailed instructions for the AI assistant]
```

## Usage Examples

### [Scenario 1]
```
[Example prompt and usage]
```

## Best Practices

- [Best practice 1]
- [Best practice 2]
```

#### For Prompts
```markdown
# [Prompt Category] Prompts

## [Specific Prompt Name]

```
[Template with clear placeholders]
```

**Use Case**: [When to use this prompt]
**Expected Output**: [What you should expect]
**Customization**: [How to adapt for different scenarios]
```

#### For Templates
```
template-name/
├── README.md (setup instructions)
├── src/ (source code)
├── tests/ (test files)
├── docs/ (documentation)
└── .env.example (configuration)
```

### 2. Test Your Content
Before submitting:
- ✅ Test chatmodes with real AI assistants
- ✅ Verify prompt templates produce good results
- ✅ Ensure templates work as documented
- ✅ Check all links and references
- ✅ Validate code examples

### 3. Update Documentation
- Add your contribution to relevant README.md files
- Update the main README.md if adding a new category
- Include appropriate cross-references
- Add examples to the examples section if applicable

### 4. Submit a Pull Request
1. **Commit your changes**:
```bash
git add .
git commit -m "Add [contribution type]: [brief description]"
git push origin feature/your-contribution-name
```

2. **Create Pull Request**:
- Go to the original repository
- Click "New Pull Request"
- Select your branch
- Fill out the PR template

### 5. Pull Request Template
```markdown
## Description
Brief description of your contribution.

## Type of Contribution
- [ ] New chatmode
- [ ] New prompt template
- [ ] New code template
- [ ] New workflow
- [ ] Documentation improvement
- [ ] Bug fix
- [ ] Other: ___________

## Testing
- [ ] Tested with AI assistant
- [ ] Verified examples work
- [ ] Checked documentation
- [ ] Updated relevant indexes

## Checklist
- [ ] Follows contribution guidelines
- [ ] Uses consistent formatting
- [ ] Includes appropriate examples
- [ ] Updates documentation
- [ ] Ready for review
```

## Quality Standards
### Content Review Criteria

**Accuracy**: Information is correct and up-to-date
**Completeness**: Covers the topic thoroughly
**Clarity**: Easy to understand and follow
**Consistency**: Matches existing style and format
**Usefulness**: Provides practical value
**Originality**: Not duplicating existing content

### Code Quality
- **Follows best practices** for the relevant language/framework
- **Includes error handling** and validation
- **Has appropriate comments** and documentation
- **Uses consistent formatting** and style
- **Includes security considerations**

## Community Guidelines
### Be Respectful
- Use inclusive language
- Respect different perspectives and experience levels
- Provide constructive feedback
- Help newcomers learn and contribute

### Be Collaborative
- Respond to questions and comments
- Provide helpful reviews
- Share knowledge and experiences
- Support other contributors

### Be Professional
- Keep discussions focused and relevant
- Use appropriate language and tone
- Respect project maintainers' decisions
- Follow the code of conduct

## Recognition
Contributors are recognized in several ways:

- **Contributors List**: Added to the main README.md
- **Changelog**: Mentioned in release notes
- **Showcase**: Featured examples and success stories
- **Badges**: Special recognition for significant contributions

## Getting Help
Need help with your contribution?

- **Discussions**: Join community discussions for questions
- **Issues**: Create an issue for guidance
- **Documentation**: Check existing guides and examples
- **Mentorship**: Ask for help from experienced contributors

## Development Setup
For local development and testing:

```bash
# Clone the repository
git clone https://github.com/austinsonger/just-vibing-toolkit.git
cd just-vibing-toolkit

# Install any dependencies (if applicable)
npm install  # or pip install -r requirements.txt

# Run local documentation server (if available)
npm run docs:dev
```
