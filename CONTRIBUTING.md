# Contributing to GPG Key Verification

Thank you for your interest in contributing to our GPG Key Verification repository! We welcome all contributions that help improve this project.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Enhancements](#suggesting-enhancements)
  - [Your First Code Contribution](#your-first-code-contribution)
- [Pull Request Process](#pull-request-process)
- [Development Environment Setup](#development-environment-setup)
- [Code Style Guide](#code-style-guide)
- [License](#license)

## Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check if the issue has already been reported. If you're unable to find an open issue addressing the problem, open a new one using the [Bug Report](.github/ISSUE_TEMPLATE/bug_report.md) template.

### Suggesting Enhancements

We welcome enhancement suggestions that improve the project. Please use the [Feature Request](.github/ISSUE_TEMPLATE/feature_request.md) template when suggesting new features or improvements.

### Your First Code Contribution

1. Fork the repository and create your branch from `main`.
2. Make your changes following the [Code Style Guide](#code-style-guide).
3. Ensure your code is properly tested.
4. Commit your changes with a clear and descriptive commit message.
5. Push your changes to your fork.
6. Open a Pull Request with a clear description of the changes.

## Pull Request Process

1. Ensure any install or build dependencies are removed before the end of the layer when doing a build.
2. Update the README.md with details of changes to the interface, this includes new environment variables, exposed ports, useful file locations, and container parameters.
3. Increase the version numbers in any examples files and the README.md to the new version that this Pull Request would represent. The versioning scheme we use is [SemVer](http://semver.org/).
4. You may merge the Pull Request in once you have the sign-off of one other developer, or you may request the reviewer to merge it for you.

## Development Environment Setup

1. Fork and clone the repository
2. Install the required dependencies:
   ```bash
   # Install Docker and Docker Compose
   # Follow instructions for your OS: https://docs.docker.com/get-docker/
   ```
3. Start the development environment:
   ```bash
   docker-compose -f scripts/gpg_manager/gpg-key-manager.docker-compose.yml up -d
   ```

## Code Style Guide

- Use clear and descriptive variable and function names
- Include comments explaining the "why" behind complex logic
- Keep functions small and focused on a single responsibility
- Follow the existing code style in the codebase
- Ensure all tests pass before submitting a pull request

## License

By contributing, you agree that your contributions will be licensed under its [MIT License](LICENSE).
