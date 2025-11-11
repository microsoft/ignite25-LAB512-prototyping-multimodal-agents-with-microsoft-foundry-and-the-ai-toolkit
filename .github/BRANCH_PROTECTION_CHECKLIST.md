# Branch Protection Setup Checklist

This checklist helps repository administrators verify that branch protection has been properly configured.

## 🎯 Pre-Configuration

- [ ] Verify you have administrator access to the repository
- [ ] Review existing workflows and understand which should be required status checks
- [ ] Confirm code owners are correctly identified in `.github/CODEOWNERS`
- [ ] Review the full configuration guide in `.github/BRANCH_PROTECTION.md`

## ⚙️ Configuration Steps

### Basic Setup
- [ ] Navigate to Repository Settings → Branches
- [ ] Click "Add rule" or "Add classic branch protection rule"
- [ ] Set branch name pattern to `main`

### Pull Request Requirements
- [ ] Enable "Require a pull request before merging"
- [ ] Set required approvals to minimum of `1`
- [ ] Enable "Dismiss stale pull request approvals when new commits are pushed"
- [ ] Enable "Require review from Code Owners"

### Status Checks
- [ ] Enable "Require status checks to pass before merging"
- [ ] Enable "Require branches to be up to date before merging"
- [ ] Select required status checks from available workflows

### Additional Protections
- [ ] Enable "Require conversation resolution before merging" (recommended)
- [ ] Enable "Include administrators" (recommended)
- [ ] Ensure "Allow deletions" is DISABLED
- [ ] Ensure "Allow force pushes" is DISABLED

### Finalize
- [ ] Click "Create" or "Save changes"
- [ ] Verify the rule appears in the "Branch protection rules" list

## ✅ Post-Configuration Verification

### Test 1: Direct Push Prevention
- [ ] Attempt to push directly to main (should be rejected)
- [ ] Verify error message indicates branch is protected

### Test 2: Pull Request Workflow
- [ ] Create a test feature branch
- [ ] Make a small change and push the branch
- [ ] Create a pull request
- [ ] Verify code owners are automatically requested as reviewers
- [ ] Verify status checks are triggered (if applicable)

### Test 3: Review Requirements
- [ ] Verify PR cannot be merged without approval
- [ ] Get approval from a code owner
- [ ] Verify PR can now be merged (if checks pass)

### Test 4: Branch Update Requirements
- [ ] Create two PRs from different branches
- [ ] Merge the first PR
- [ ] Verify the second PR shows as "out of date"
- [ ] Update the second PR's branch
- [ ] Verify merge becomes available

### Test 5: Administrator Enforcement
- [ ] As an administrator, attempt to push directly to main
- [ ] Verify even administrators are blocked (if "Include administrators" is enabled)

## 📋 Documentation

- [ ] Ensure `.github/CODEOWNERS` file is present and up-to-date
- [ ] Ensure `.github/BRANCH_PROTECTION.md` is available for reference
- [ ] Update `AGENTS.md` with branch protection workflow guidance
- [ ] Notify team members about the new workflow requirements

## 🔄 Ongoing Maintenance

Schedule periodic reviews:
- [ ] Review code owners quarterly
- [ ] Update required status checks when workflows change
- [ ] Review protection settings when team structure changes
- [ ] Audit compliance with protection rules

## 📝 Notes

Date Configured: _______________

Configured By: _______________

Issues Encountered: 
_______________________________________________
_______________________________________________
_______________________________________________

Additional Configuration Details:
_______________________________________________
_______________________________________________
_______________________________________________

## 🆘 Troubleshooting

If you encounter issues:

1. **Status checks not appearing**: 
   - Ensure workflows run on `pull_request` events
   - Verify workflows have run at least once

2. **Code owners not requested**:
   - Check CODEOWNERS file syntax
   - Verify usernames are correct
   - Ensure users have repository access

3. **Cannot merge despite approvals**:
   - Check if branch is up-to-date
   - Verify all required checks have passed
   - Ensure all conversations are resolved

For detailed troubleshooting, see `.github/BRANCH_PROTECTION.md`

---

**Reference**: See `.github/BRANCH_PROTECTION.md` for complete configuration guide.
