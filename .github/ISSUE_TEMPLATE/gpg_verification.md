---
name: GPG Verification
about: Verify your GPG key setup
title: '[GPG - VERIFICATION] GPG Key Setup Verification'
labels: ['gpg', 'verification', 'good first issue']
assignees: ''
---

[GPG - VERIFICATION] GPG Key Setup

## Description
This issue is for verifying that your GPG key is correctly set up and can sign commits.

## GPG Key Information
- **Key ID**: `YOUR_KEY_ID` (last 8 characters)
- **Key Fingerprint**: `YOUR_KEY_FINGERPRINT`
- **Key Owner**: Your Name <your.email@example.com>

## Verification Steps Completed
- [ ] Forked the repository
- [ ] Cloned the forked repository locally
- [ ] Configured Git with my GPG key
- [ ] Created a test commit with GPG signing
- [ ] Pushed the signed commit to my fork
- [ ] Created a pull request to verify the setup

## Screenshots

### 1. Verified Commit
<!-- 
Add a screenshot showing the verified commit status in GitHub.
To take this screenshot:
1. Go to your commit in GitHub
2. Look for the "Verified" badge next to the commit hash
3. Take a screenshot showing the commit message and verification status
-->

### 2. GPG Key Configuration
<!-- 
Add a screenshot showing your GPG key configuration in GitHub.
To take this screenshot:
1. Go to GitHub Settings > SSH and GPG keys
2. Find your GPG key in the list
3. Take a screenshot showing the key details (you may blur the key ID if needed)
-->

### 3. Local Git Configuration
<!-- 
Add a screenshot showing your local Git configuration with GPG signing enabled.
To take this screenshot:
1. Run: `git config --list | grep gpg`
2. Take a screenshot of the output showing your GPG key is configured
-->

## Additional Notes
<!-- Add any additional information or context about your setup -->

## Checklist
- [ ] I have read and followed the [GPG setup instructions](https://github.com/TuxTechLab/test-gpg-sign#readme)
- [ ] My commit is signed with a verified signature
- [ ] I understand that maintainers will review and verify my GPG setup

---
*This issue template is used to verify GPG key setup for TuxTechLab contributors.*
