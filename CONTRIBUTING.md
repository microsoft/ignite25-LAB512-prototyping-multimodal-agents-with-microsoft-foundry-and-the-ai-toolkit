# Contributing to LAB512: Prototyping multimodal agents

Thank you for your interest in contributing to this Microsoft Ignite 2025 lab repository! This document provides guidelines for contributing to the project.

## 🔀 Branch Protection and Pull Request Workflow

This repository uses branch protection on the `main` branch. **All changes must be submitted via pull requests** - direct pushes to `main` are not allowed.

### Quick Start for Contributors

1. **Fork or clone** the repository
2. **Create a feature branch** from `main`:
   ```bash
   git checkout -b your-username/feature-name
   ```
3. **Make your changes** following the guidelines below
4. **Commit your changes** with clear, descriptive messages
5. **Push your branch** to the repository
6. **Create a pull request** to merge into `main`
7. **Wait for review** from code owners
8. **Address feedback** and ensure all checks pass
9. **Merge** after approval

For detailed workflow instructions, see [AGENTS.md](AGENTS.md#-branch-protection-and-pull-request-workflow).

## 📋 Contribution Guidelines

### Code Standards

- Follow existing code style and conventions
- Write clear, self-documenting code
- Add comments for complex logic
- Keep functions focused and modular

### Documentation

- Update relevant documentation when making changes
- Ensure all README files remain accurate
- Update lab instructions if workflow changes
- Keep documentation concise and clear

### Testing

- Test your changes thoroughly before submitting
- Verify lab instructions still work end-to-end
- Check that links and references are valid
- Ensure no broken dependencies

### Commit Messages

Write clear, descriptive commit messages:

```
Add validation for API key configuration

- Implement environment variable checks
- Add helpful error messages
- Update documentation with setup steps
```

Format:
- Use present tense ("Add feature" not "Added feature")
- First line is a summary (50 chars or less)
- Add detailed description after blank line if needed
- Reference issues with "Fixes #123" or "Relates to #123"

## 🔒 Security and Sensitive Data

**IMPORTANT**: Never commit sensitive information:
- ❌ API keys or tokens
- ❌ Credentials or passwords
- ❌ Personal access tokens
- ❌ Database connection strings
- ❌ Any private configuration values

Use placeholders and environment variables instead. See [AGENTS.md](AGENTS.md#-security-best-practices) for details.

## 👥 Code Review Process

All pull requests require:

- ✅ At least 1 approval from a code owner
- ✅ All conversations resolved
- ✅ All status checks passing
- ✅ Branch up-to-date with `main`

### Code Owners

The following users are designated code owners (see [`.github/CODEOWNERS`](.github/CODEOWNERS)):
- @carlotta94c
- @aprilgittens

Code owners will be automatically requested as reviewers on your pull request.

### Review Timeline

- Initial review: Within 2-3 business days
- Follow-up reviews: Within 1-2 business days
- Urgent fixes: Tag reviewers for faster response

## 🐛 Reporting Issues

When reporting issues, please include:

1. **Clear description** of the problem
2. **Steps to reproduce** the issue
3. **Expected behavior** vs actual behavior
4. **Environment details** (OS, versions, etc.)
5. **Screenshots** if applicable
6. **Error messages** with full stack traces

## 💡 Suggesting Enhancements

Enhancement suggestions are welcome! Please:

1. Check existing issues/PRs first to avoid duplicates
2. Describe the enhancement clearly
3. Explain the use case and benefits
4. Consider backward compatibility
5. Discuss implementation approach

## 🚫 What NOT to Change

Without explicit permission, do not modify:

- License files (`LICENSE`, `LICENSE-DOCS`)
- Code of Conduct (`CODE_OF_CONDUCT.md`)
- Security policy (`SECURITY.md`)
- GitHub workflow configurations (`.github/workflows/`)

## 📚 Additional Resources

- [Branch Protection Setup Guide](.github/BRANCH_PROTECTION.md)
- [AI Agent Guidelines](AGENTS.md)
- [Support Resources](SUPPORT.md)
- [Security Policy](SECURITY.md)
- [Code of Conduct](CODE_OF_CONDUCT.md)

## 📞 Getting Help

- **Discord**: [Microsoft Azure AI Foundry Community](https://aka.ms/AIFoundryDiscord-Ignite25)
- **Forum**: [Azure AI Foundry Developer Forum](https://aka.ms/AIFoundryForum-Ignite25)
- **Documentation**: [Microsoft Learn](https://aka.ms/LearnAtIgnite?ocid=ignite25_nextsteps_github_cnl)

## 📄 License

By contributing to this project, you agree that your contributions will be licensed under the same license as the project. See [LICENSE](LICENSE) for details.

You must also agree to the Contributor License Agreement (CLA). When you submit a pull request, a CLA bot will automatically check and guide you through the process if needed. See [Contributor License Agreements](https://cla.opensource.microsoft.com) for more information.

---

Thank you for contributing to Microsoft Ignite 2025! 🎉
