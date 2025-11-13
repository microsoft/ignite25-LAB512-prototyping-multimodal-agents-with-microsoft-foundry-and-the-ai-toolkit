# 🔒 Branch Protection Configuration Guide

This document provides step-by-step instructions for configuring branch protection rules on the `main` branch of this repository.

## 📋 Prerequisites

- Repository administrator access
- Familiarity with GitHub repository settings
- Understanding of pull request workflows

## 🎯 Configuration Steps

### Step 1: Navigate to Branch Protection Settings

1. Go to the repository on GitHub: `https://github.com/microsoft/ignite25-LAB512-prototyping-multimodal-agents-with-azure-ai-foundry-and-the-ai-toolkit`
2. Click on **Settings** (top navigation bar)
3. In the left sidebar, click **Branches** under "Code and automation"
4. Under "Branch protection rules", click **Add rule** or **Add classic branch protection rule**

### Step 2: Configure Basic Settings

1. **Branch name pattern**: Enter `main`
2. This will apply the protection rules specifically to the main branch

### Step 3: Configure Pull Request Requirements

Enable the following settings:

#### ✅ Require a pull request before merging
- [x] Check this option
- **Required approvals**: Set to `1` (minimum)
- [x] **Dismiss stale pull request approvals when new commits are pushed**
  - This ensures that when new changes are pushed, previous approvals are invalidated
- [x] **Require review from Code Owners**
  - This uses the `.github/CODEOWNERS` file to automatically request reviews from designated owners
  - Note: This repository includes a CODEOWNERS file with designated reviewers

#### ✅ Require status checks to pass before merging
- [x] Check this option
- [x] **Require branches to be up to date before merging**
  - This ensures branches must be updated with the latest main branch before merging

**Available Status Checks:**
- If GitHub Actions workflows exist that run on pull requests, they will appear in the list
- Select any CI/CD checks that should be required (e.g., "Add issue to project")

### Step 4: Configure Additional Protections

#### ✅ Require conversation resolution before merging
- [x] Recommended: All PR conversations must be resolved before merging

#### ✅ Restrict who can push to matching branches
- Configure if you want to restrict who can push directly (even with admin override)
- For most projects, leaving this unchecked and relying on PR reviews is sufficient

#### ✅ Do not allow bypassing the above settings
- [x] **Include administrators**
  - Recommended: Even repository administrators must follow these rules
  - This ensures consistency and accountability across all contributors

#### ✅ Rules applied to everyone including administrators
- [x] **Allow deletions**: Leave **UNCHECKED** (disabled)
  - This prevents accidental deletion of the protected branch
- [ ] **Allow force pushes**: Leave **UNCHECKED** (disabled)
  - This prevents history rewriting on the protected branch

### Step 5: Save the Configuration

1. Scroll to the bottom of the page
2. Click **Create** (for new rules) or **Save changes** (for updates)
3. Confirm the branch protection rule is now listed under "Branch protection rules"

## ✅ Verification Steps

After configuration, verify the protection is working:

### Test 1: Attempt Direct Push (Should Fail)
```bash
# This should be blocked
git checkout main
git commit --allow-empty -m "Test direct push"
git push origin main
# Expected: Remote will reject the push
```

### Test 2: Pull Request Workflow (Should Succeed)
```bash
# Create a feature branch
git checkout -b test-branch-protection
echo "test" > test.txt
git add test.txt
git commit -m "Test branch protection"
git push origin test-branch-protection

# Then create a PR on GitHub
# The PR should require:
# - At least 1 approval
# - Status checks to pass (if configured)
# - Branch to be up-to-date
```

### Test 3: Verify Code Owner Review Request
1. Create a PR that modifies files owned in CODEOWNERS
2. Verify that the code owners are automatically requested as reviewers
3. Verify that a review from a code owner is required before merging

### Test 4: Verify Branch Up-to-Date Requirement
1. Create two PRs from different branches
2. Merge the first PR
3. Attempt to merge the second PR without updating it
4. Verify that you're required to update the branch first

## 🔍 Troubleshooting

### Issue: Status checks not appearing
- Ensure your GitHub Actions workflows are configured to run on `pull_request` events
- Status checks only appear after they've run at least once on a pull request

### Issue: Code owners not being requested
- Verify the `.github/CODEOWNERS` file exists and is on the main branch
- Check that the GitHub usernames in CODEOWNERS are correct and valid
- Ensure users have read access to the repository

### Issue: Administrators can still push directly
- Verify "Include administrators" is checked in the branch protection settings
- Some GitHub plans may have limitations on this feature

## 📚 Additional Resources

- [GitHub Branch Protection Documentation](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)
- [Managing a branch protection rule](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/managing-a-branch-protection-rule)
- [About code owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners)
- [About required status checks](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/collaborating-on-repositories-with-code-quality-features/about-status-checks)

## 🤖 For AI Agents and Copilot

If you are an AI agent working on this repository after branch protection is enabled:

1. **Never attempt to push directly to main**
2. **Always create a feature branch** using the naming convention:
   - `copilot/feature-name` for new features
   - `copilot/fix-name` for bug fixes
   - `copilot/update-name` for updates

3. **Always create pull requests** with:
   - Clear, descriptive titles
   - Detailed descriptions of changes
   - References to related issues

4. **Follow the workflow**:
   ```bash
   git checkout -b copilot/your-feature-name
   # Make changes
   git add .
   git commit -m "Description of changes"
   git push origin copilot/your-feature-name
   # Then create a PR through GitHub
   ```

5. **Wait for reviews and checks** before attempting to merge

## 🔄 Updating Protection Rules

Branch protection rules should be reviewed and updated periodically:

- When adding new CI/CD workflows that should be required
- When team membership changes affect code ownership
- When security requirements change
- At least once per quarter to ensure they remain appropriate

---

**Last Updated**: 2025-11-11  
**Maintained By**: Repository Administrators (@carlotta94c, @aprilgittens)
