# AI Agent Guidelines

This file contains instructions and guidelines for AI agents working on this repository.

## 🔒 Security Best Practices

**Never commit sensitive information to this repository:**
- API keys, tokens, or credentials
- Personal access tokens (PATs)
- Database connection strings with passwords
- Environment-specific configuration values

**For MCP configuration files (`mcp.json`):**
- Use placeholder values like `"YOUR_API_KEY_HERE"` or `"${API_KEY}"`
- Reference environment variables for sensitive data
- Include documentation about required environment variables

## 📋 Repository Guidelines

### Purpose
This repository is one of several for Microsoft Ignite 2025 sessions and should:
- Provide a consistent structure for all Ignite content repositories
- Include proper documentation for the customer
- Support MkDocs documentation generation
- Enable Learn MCP (Model Context Protocol) server integration

### Consistent Experience
- Maintain the existing folder structure (`docs/`, `src/`, `lab/`, etc.)
- Don't remove placeholder folders unless explicitly instructed
- Keep the banner image and branding consistent
- Ensure all links use proper campaign codes when referencing Learn content
- SUPPORT.md should be updated with support information.
- All readme files in the repo should have updates
- All subfolder names under /docs should be reviewed for mkdocs compatibility
- Unused subfolders (e.g. that only have a README file in them) should be cleaned up before the repo is released.
- No large binary files like powerpoints or videos should be added to the repo.

### What NOT to modify without permission:
- License files (`LICENSE`, `CODE_OF_CONDUCT.md`)
- Security files (`SECURITY.md`)
- GitHub workflow files in `.github/` directory

## 🔀 Branch Protection and Pull Request Workflow

This repository uses branch protection on the `main` branch to ensure code quality and maintain a clear review process.

### Working with Protected Branches

**NEVER push directly to the `main` branch.** All changes must go through pull requests.

### Creating Feature Branches

When making changes, always create a feature branch using this naming convention:

```bash
# For new features
git checkout -b copilot/feature-description

# For bug fixes
git checkout -b copilot/fix-description

# For updates or improvements
git checkout -b copilot/update-description
```

### Pull Request Workflow

1. **Create your feature branch**:
   ```bash
   git checkout -b copilot/your-feature-name
   ```

2. **Make your changes and commit**:
   ```bash
   git add .
   git commit -m "Clear description of changes"
   ```

3. **Push your branch**:
   ```bash
   git push origin copilot/your-feature-name
   ```

4. **Create a Pull Request** with:
   - A clear, descriptive title
   - Detailed description of what was changed and why
   - References to related issues (e.g., "Fixes #123")
   - Any relevant screenshots or test results

5. **Wait for review**:
   - Code owners will be automatically requested as reviewers
   - Address any feedback or requested changes
   - Ensure all status checks pass

6. **Keep your branch up-to-date**:
   ```bash
   git fetch origin
   git rebase origin/main
   git push --force-with-lease origin copilot/your-feature-name
   ```

### Pull Request Requirements

When branch protection is enabled, pull requests must meet these requirements:

- ✅ At least 1 approval from a code owner
- ✅ All conversations must be resolved
- ✅ All required status checks must pass
- ✅ Branch must be up-to-date with `main`

### Code Review Guidelines

- Respond to review comments promptly
- Make requested changes in new commits (don't force-push during active review)
- Mark conversations as resolved when addressed
- Request re-review after making significant changes

### Additional Resources

For detailed branch protection configuration instructions, see [`.github/BRANCH_PROTECTION.md`](.github/BRANCH_PROTECTION.md)

