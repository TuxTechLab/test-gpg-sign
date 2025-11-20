# GPG Key Verification with TuxTechIaaC

This repository helps contributors verify their GPG key setup using the TuxTechIaaC GPG Manager tool. Follow these steps to generate a GPG key and configure it with your GitHub account.

## 🚀 Purpose

This repository allows you to:
- Generate a new GPG key using TuxTechIaaC's GPG Manager
- Configure your local Git and GitHub to use the generated key
- Test and verify your GPG commit signing
- Submit a pull request to confirm successful setup

## 🛠️ Prerequisites

- Docker and Docker Compose installed
- Git installed
- A GitHub account

## 🔑 GPG Key Generation with TuxTechIaaC GPG Manager

### 1. Start the GPG Manager

```bash
# Clone the TuxTechIaaC repository (if not already cloned)
git clone https://github.com/TuxTechLab/TuxTechIaaC.git
cd TuxTechIaaC

# Start the GPG Manager
docker-compose -f scripts/gpg_manager/gpg-key-manager.docker-compose.yml up -d
```

### 2. Access the Web Interface

Open your browser and navigate to:
```
http://localhost:5000
```

### 3. Generate a New GPG Key

1. Click on "Generate New Key"
2. Fill in your details:
   - Name: Your full name
   - Email: Your GitHub email address
   - Passphrase: Create a strong passphrase
3. Click "Generate"

### 4. Export Your Public Key

1. Find your key in the list
2. Click the "Export" button next to your key
3. Save the `.asc` file to your computer

## 🔗 Configure GitHub with Your GPG Key

1. **Add GPG Key to GitHub**:
   - Go to GitHub → Settings → SSH and GPG keys
   - Click "New GPG key"
   - Open the exported `.asc` file in a text editor
   - Copy the entire content including `-----BEGIN PGP PUBLIC KEY BLOCK-----` and `-----END PGP PUBLIC KEY BLOCK-----`
   - Paste into GitHub and click "Add GPG key"

2. **Configure Git Locally**:
   ```bash
   # Set your Git identity
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   
   # Get your GPG key ID
   docker exec gpg-manager gpg --list-secret-keys --keyid-format=long
   
   # Configure Git to use your GPG key
   git config --global user.signingkey YOUR_KEY_ID
   git config --global commit.gpgsign true
   
   # (Optional) Configure GPG TTY (for Linux/macOS)
   echo 'export GPG_TTY=$(tty)' >> ~/.bashrc
   source ~/.bashrc
   ```

## 🧪 Test Your Setup

### Option 1: Using Issue Template (Recommended)

1. **Create a new issue** using the [GPG Verification](.github/ISSUE_TEMPLATE/gpg_verification.md) template
2. Fill in the required GPG key information
3. Complete the verification steps in the issue template
4. Submit the issue for verification

### Option 2: Creating a Pull Request

1. **Fork this repository**
2. **Clone your fork** locally:
   ```bash
   git clone git@github.com:YOUR-USERNAME/test-gpg-sign.git
   cd test-gpg-sign
   ```
3. **Create a test commit** with GPG signing:
   ```bash
   echo "Test GPG signature" > test.txt
   git add test.txt
   git commit -S -m "Test: Verify GPG signing with TuxTechIaaC"
   ```
4. **Push your changes**:
   ```bash
   git push origin main
   ```
5. **Create a pull request** using the GPG Verification PR template
   - The PR template will guide you through providing necessary GPG key information
   - Include screenshots of your verified commit and GPG configuration
   - Ensure all checkboxes in the PR template are completed

## 📋 Issue and PR Templates

### GPG Verification Issue Template
When creating a new issue, use the "GPG Verification" template to:
- Provide your GPG key details
- Confirm completion of verification steps
- Upload required screenshots
- Get help with any issues

### GPG Verification PR Template
When creating a pull request, you'll be prompted to:
1. Fill in your GPG key information:
   ```
   - Key ID: Last 8 characters of your GPG key
   - Key Fingerprint: Full fingerprint of your GPG key
   - Key Owner: Your name and email associated with the key
   ```
2. Complete the verification checklist
3. Attach screenshots showing:
   - Verified commit status on GitHub
   - GPG key configuration in GitHub settings
   - Local Git configuration

## 📸 Required Screenshots

For both issues and PRs, please include these screenshots:

1. **Verified Commit**
   - Show the commit in GitHub with the "Verified" badge
   - Include the commit message and hash

2. **GitHub GPG Settings**
   - Go to GitHub Settings > SSH and GPG keys
   - Show your GPG key in the list (you may blur the key ID)

3. **Local Git Configuration**
   - Show the output of: `git config --list | grep -i gpg`
   - Show the output of: `gpg --list-secret-keys --keyid-format=long`

## 🔍 Verification Process

1. **Initial Review**: A maintainer will review your issue or PR
2. **Verification**: They will check:
   - GPG key is properly configured
   - Commits are signed and verified
   - All required information is provided
3. **Approval**: Once verified, your PR will be merged
4. **Completion**: You'll receive confirmation that your GPG setup is working correctly

## 🐛 Troubleshooting

If your commits aren't showing as verified:
1. Ensure the email in your Git config matches the one used in your GPG key
2. Verify your GPG key is added to GitHub
3. Check your Git config: `git config --global -l`
4. Make sure you're using the `-S` flag when committing
5. For Windows, you might need to configure GPG program path:
   ```bash
   git config --global gpg.program "C:\\Program Files (x86)\\GnuPG\\bin\\gpg.exe"
   ```

## 📝 Issue Templates

We use issue templates to streamline the contribution process. Please select the appropriate template when creating a new issue:

### 🐞 [Report a Bug](.github/ISSUE_TEMPLATE/bug_report.md)
Use this template when you've found a bug or unexpected behavior in the repository.
- **When to use:**
  - Something isn't working as expected
  - You're experiencing errors during setup or verification
  - You've found a security vulnerability
- **What to include:**
  - Clear steps to reproduce the issue
  - Expected vs. actual behavior
  - Screenshots or error messages
  - Environment details (OS, browser, etc.)

### ✨ [Request a Feature](.github/ISSUE_TEMPLATE/feature_request.md)
Use this template to suggest new features or improvements.
- **When to use:**
  - You have an idea for a new feature
  - You want to suggest an improvement to existing functionality
  - You'd like to discuss a potential enhancement
- **What to include:**
  - Clear description of the proposed feature
  - Explanation of why this would be valuable
  - Any relevant examples or use cases

### 🔐 [Verify GPG Setup](.github/ISSUE_TEMPLATE/gpg_verification.md)
Use this template to verify your GPG key setup with our repository.
- **When to use:**
  - You've generated a new GPG key
  - You're setting up GPG signing for the first time
  - You want to verify your GPG configuration
- **What to include:**
  - Your GPG key ID and fingerprint
  - Confirmation of completed verification steps
  - Screenshots of your verified commit and GPG settings

### Creating an Issue
1. Click on the "Issues" tab in the repository
2. Click "New issue"
3. Select the appropriate template
4. Fill in all required fields
5. Submit the issue

Our team will review your submission and respond as soon as possible.

## 🤝 Contributing

Contributions are welcome! Please read our [Contributing Guide](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
testing

there is a updated gpg for verification

