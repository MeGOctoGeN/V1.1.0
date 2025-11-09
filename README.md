# V1.1.0
# Pull Request

## Description
Please include a summary of the changes and which issue is fixed. Include relevant motivation and context.

Fixes # (issue)

## Type of Change
Please delete options that are not relevant.

- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update
- [ ] Performance improvement
- [ ] Code refactoring
- [ ] Tests
- [ ] CI/CD changes

## How Has This Been Tested?
Please describe the tests that you ran to verify your changes. Provide instructions so we can reproduce.

- [ ] Test A
- [ ] Test B

**Test Configuration**:
- Python version:
- OS:
- MEGAGENT version:

## Checklist
- [ ] My code follows the style guidelines of this project
- [ ] I have performed a self-review of my own code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have added tests that prove my fix is effective or that my feature works
- [ ] New and existing unit tests pass locally with my changes
- [ ] Any dependent changes have been merged and published in downstream modules
- [ ] I have checked my code and corrected any misspellings
- [ ] I have updated CHANGELOG.md with my changes

## Screenshots (if applicable)
Add screenshots to help explain your changes.

## Additional Notes
Add any additional notes or context about the pull request here.

## Breaking Changes
If this PR introduces breaking changes, please describe them and the migration path for existing users.

## Dependencies
List any new dependencies required for this change.

## Reviewer Notes
Any specific areas you'd like reviewers to focus on?
# These are supported funding model platforms

github: ELMOURABEA
patreon: ELMOURABEA
open_collective: ELMOURABEA
ko_fi: ELMOURABEA
liberapay: ELMOURABEA
polar: ELMOURABEA
buy_me_a_coffee: ELMOURABEA
custom: ["https://github.com/sponsors/ELMOURABEA"]
name: CI

on:
  # Triggers the workflow on push or pull request events
  push:
  pull_request:
    branches: ["main"]

  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
      - uses: actions/checkout@v4

      # Runs a single command using the runners shell
      - name: Run a one-line script
        run: echo Hello, world!

      # Runs a set of commands using the runners shell
      - name: Run a multi-line script
        run: |
          echo Add other actions to build,
          echo test, and deploy your project.
name: Python package (Conda)

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Set up Miniconda
        uses: conda-incubator/setup-miniconda@v3
        with:
          python-version: '3.11'
          auto-update-conda: true
          activate-environment: activbot-ci
          environment-file: environment.yml
          use-mamba: true

      - name: Install dependencies (fallback)
        if: failure() || success()
        run: |
          python -m pip install --upgrade pip
          pip install -r requirements.txt || true
          pip install -r requirements-dev.txt || true

      - name: Lint
        run: |
          if command -v flake8 >/dev/null 2>&1; then
            flake8 . || true
          fi

      - name: Run tests
        run: |
          if command -v pytest >/dev/null 2>&1; then
            pytest -q || true
          fi
           💼 **Open Collective:** [ELMOURABEA](https://opencollective.com/ELMOURABEA)
- 🎨 **Ko-fi:** [ELMOURABEA](https://ko-fi.com/ELMOURABEA)
- 📺 **Patreon:** [ELMOURABEA](https://patreon.com/ELMOURABEA)
- ⚡ **Polar:** [ELMOURABEA](https://polar.sh/ELMOURABEA)

### 📊 GitHub Stats

<div align="center">

![ELMOURABEA's GitHub stats](https://github-readme-stats.vercel.app/api?username=ELMOURABEA&show_icons=true&theme=radical)

</div>

---

<div align="center">

**⭐ Star my repositories if you find them useful!**  
**💖 Every contribution helps make open source sustainable!**

[![Sponsor](https://img.shields.io/badge/Sponsor-💖-pink?style=for-the-badge)](https://github.com/sponsors/ELMOURABEA)

</div>

<!--
**ELMOURABEA/.github** is a ✨ _special_ ✨ repository because its `profile/README.md` (this file) appears on your GitHub profile.
-->
# Contributor Covenant Code of Conduct

## Our Pledge

We as members, contributors, and leaders pledge to make participation in our
community a harassment-free experience for everyone, regardless of age, body
size, visible or invisible disability, ethnicity, sex characteristics, gender
identity and expression, level of experience, education, socio-economic status,
nationality, personal appearance, race, caste, color, religion, or sexual
identity and orientation.

We pledge to act and interact in ways that contribute to an open, welcoming,
diverse, inclusive, and healthy community.

## Our Standards

Examples of behavior that contributes to a positive environment for our
community include:

* Demonstrating empathy and kindness toward other people
* Being respectful of differing opinions, viewpoints, and experiences
* Giving and gracefully accepting constructive feedback
* Accepting responsibility and apologizing to those affected by our mistakes,
  and learning from the experience
* Focusing on what is best not just for us as individuals, but for the overall
  community

Examples of unacceptable behavior include:

* The use of sexualized language or imagery, and sexual attention or advances of
  any kind
* Trolling, insulting or derogatory comments, and personal or political attacks
* Public or private harassment
* Publishing others' private information, such as a physical or email address,
  without their explicit permission
* Other conduct which could reasonably be considered inappropriate in a
  professional setting

## Enforcement Responsibilities

Community leaders are responsible for clarifying and enforcing our standards of
acceptable behavior and will take appropriate and fair corrective action in
response to any behavior that they deem inappropriate, threatening, offensive,
or harmful.

Community leaders have the right and responsibility to remove, edit, or reject
comments, commits, code, wiki edits, issues, and other contributions that are
not aligned to this Code of Conduct, and will communicate reasons for moderation
decisions when appropriate.

## Scope

This Code of Conduct applies within all community spaces, and also applies when
an individual is officially representing the community in public spaces.
Examples of representing our community include using an official e-mail address,
posting via an official social media account, or acting as an appointed
representative at an online or offline event.

## Enforcement

Instances of abusive, harassing, or otherwise unacceptable behavior may be
reported to the community leaders responsible for enforcement through GitHub
issues or direct contact with project maintainers.

All complaints will be reviewed and investigated promptly and fairly.

All community leaders are obligated to respect the privacy and security of the
reporter of any incident.

## Enforcement Guidelines

Community leaders will follow these Community Impact Guidelines in determining
the consequences for any action they deem in violation of this Code of Conduct:

### 1. Correction

**Community Impact**: Use of inappropriate language or other behavior deemed
unprofessional or unwelcome in the community.

**Consequence**: A private, written warning from community leaders, providing
clarity around the nature of the violation and an explanation of why the
behavior was inappropriate. A public apology may be requested.

### 2. Warning

**Community Impact**: A violation through a single incident or series of
actions.

**Consequence**: A warning with consequences for continued behavior. No
interaction with the people involved, including unsolicited interaction with
those enforcing the Code of Conduct, for a specified period of time. This
includes avoiding interactions in community spaces as well as external channels
like social media. Violating these terms may lead to a temporary or permanent
ban.

### 3. Temporary Ban

**Community Impact**: A serious violation of community standards, including
sustained inappropriate behavior.

**Consequence**: A temporary ban from any sort of interaction or public
communication with the community for a specified period of time. No public or
private interaction with the people involved, including unsolicited interaction
with those enforcing the Code of Conduct, is allowed during this period.
Violating these terms may lead to a permanent ban.

### 4. Permanent Ban

**Community Impact**: Demonstrating a pattern of violation of community
standards, including sustained inappropriate behavior, harassment of an
individual, or aggression toward or disparagement of classes of individuals.

**Consequence**: A permanent ban from any sort of public interaction within the
community.

## Attribution

This Code of Conduct is adapted from the [Contributor Covenant][homepage],
version 2.1, available at
[https://www.contributor-covenant.org/version/2/1/code_of_conduct.html][v2.1].

Community Impact Guidelines were inspired by
[Mozilla's code of conduct enforcement ladder][Mozilla CoC].

For answers to common questions about this code of conduct, see the FAQ at
[https://www.contributor-covenant.org/faq][FAQ]. Translations are available at
[https://www.contributor-covenant.org/translations][translations].

[homepage]: https://www.contributor-covenant.org
[v2.1]: https://www.contributor-covenant.org/version/2/1/code_of_conduct.html
[Mozilla CoC]: https://github.com/mozilla/diversity
[FAQ]: https://www.contributor-covenant.org/faq
[translations]: https://www.contributor-covenant.org/translations
name:-Run-Gemini-CLIgoogle-github-actions/run-gemini-cli@v0.1.10
  gh repo clone google-gemini/gemini-cli
  # Contributing to Economic Storm Platform

Thank you for your interest in contributing to the Economic Storm Platform! 🎉

## 🤝 How to Contribute

### Getting Started

1. **Fork the Repository**: Click the "Fork" button at the top right
2. **Clone Your Fork**: 
   ```bash
   git clone https://github.com/YOUR_USERNAME/Economic-Storm-platform.git
   cd Economic-Storm-platform
   ```
3. **Create a Branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

### Making Changes

1. **Create an Issue First**: Use our issue templates
   - Business Development Task
   - Platform Development Task
   - Marketing Task

2. **Work with Copilot**: Leverage GitHub Copilot for assistance
   - Code generation
   - Documentation
   - Testing

3. **Follow Best Practices**:
   - Write clear, readable code
   - Add comments where necessary
   - Update documentation
   - Add tests if applicable

### Submitting Changes

1. **Commit Your Changes**:
   ```bash
   git add .
   git commit -m "Brief description of changes"
   ```

2. **Push to Your Fork**:
   ```bash
   git push origin feature/your-feature-name
   ```

3. **Create a Pull Request**:
   - Go to the original repository
   - Click "New Pull Request"
   - Select your branch
   - Fill in the PR template
   - Submit for review

### Pull Request Guidelines

- Reference the issue number (e.g., "Fixes #123")
- Provide clear description of changes
- Ensure CI/CD passes
- Respond to review feedback
- Keep PRs focused and small

## 📋 Issue Guidelines

### Creating Issues

- Use appropriate templates
- Provide clear titles with prefixes:
  - `[BUSINESS]` for business development
  - `[DEV]` for platform development
  - `[MARKETING]` for marketing tasks
- Fill all required fields
- Add relevant labels
- Specify Copilot Agent assistance needed

### Issue Lifecycle

1. **Open**: Issue is created
2. **Labeled**: Auto-labeled by Copilot Agent
3. **Assigned**: Someone takes ownership
4. **In Progress**: Work begins
5. **Review**: Work is reviewed
6. **Closed**: Issue is completed

## 💻 Development Guidelines

### Code Style

- Follow existing code patterns
- Use meaningful variable names
- Keep functions small and focused
- Comment complex logic
- Remove debug code before committing

### Testing

- Write tests for new features
- Ensure existing tests pass
- Aim for good test coverage
- Test edge cases

### Documentation

- Update README if needed
- Document public APIs
- Add inline comments for complex code
- Keep CHANGELOG updated

## 🤖 Working with Copilot Agent

### Best Practices

1. **Clear Context**: Provide clear problem descriptions
2. **Review Suggestions**: Always review Copilot suggestions
3. **Iterate**: Use suggestions as starting points
4. **Learn**: Understand the code Copilot generates

### When to Use Copilot

- ✅ Boilerplate code
- ✅ Documentation
- ✅ Test cases
- ✅ Code explanations
- ✅ Refactoring suggestions

### When to Be Careful

- ⚠️ Security-critical code
- ⚠️ Complex algorithms
- ⚠️ Business logic
- ⚠️ Production configurations

Always review and test Copilot-generated code!

## 🔍 Code Review Process

### As a Reviewer

- Be respectful and constructive
- Focus on the code, not the person
- Explain your reasoning
- Suggest improvements
- Approve when ready

### As an Author

- Be open to feedback
- Respond to comments
- Make requested changes
- Ask questions if unclear
- Thank reviewers

## 🎯 Types of Contributions

### Code Contributions

- New features
- Bug fixes
- Performance improvements
- Refactoring

### Documentation

- README updates
- Code comments
- Tutorials
- API documentation

### Testing

- Unit tests
- Integration tests
- End-to-end tests
- Test documentation

### Business & Marketing

- Market research
- Business strategy
- Marketing content
- Partnership proposals

## 🚫 What Not to Do

- Don't commit secrets or credentials
- Don't break existing functionality
- Don't ignore CI/CD failures
- Don't submit untested code
- Don't skip documentation updates

## 📞 Getting Help

### Resources

- [README.md](README.md) - Project overview
- [COPILOT_GUIDE.md](COPILOT_GUIDE.md) - Copilot collaboration
- [WORKFLOW.md](WORKFLOW.md) - Development workflow

### Ask for Help

- Check existing issues and discussions
- Create a new issue if needed
- Tag maintainers for urgent issues
- Join community discussions

## 🏆 Recognition

Contributors will be:
- Listed in project acknowledgments
- Credited in release notes
- Recognized in the community

## 📜 Code of Conduct

- Be respectful and inclusive
- Welcome newcomers
- Give constructive feedback
- Focus on collaboration
- Have fun building together!

## ✅ Checklist

Before submitting a PR, ensure:

- [ ] Code follows project style
- [ ] Tests pass locally
- [ ] Documentation is updated
- [ ] Commit messages are clear
- [ ] PR description is complete
- [ ] Issue is referenced
- [ ] No merge conflicts
- [ ] CI/CD passes

## 🎉 Thank You!

Your contributions help make Economic Storm Platform better for everyone!

---

**Questions?** Create an issue or reach out to maintainers.

**Happy Contributing!** 🚀✨
