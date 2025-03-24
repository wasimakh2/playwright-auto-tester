# Playwright Auto Tester

An automated testing framework using Playwright with automatic issue detection and GitHub integration. This tool helps you create, run, and manage tests for both app and admin interfaces, automatically detects issues, and can create GitHub issues for detected problems.

## Features

- Test both app and admin interfaces
- Automatically detect issues during testing
- Create GitHub issues for detected problems
- Capture performance metrics
- Check for accessibility issues
- Perform visual regression testing
- Generate comprehensive HTML reports
- Define test cases programmatically or via configuration files
- Interactive CLI for generating test configurations

## Installation

```bash
npm install playwright-auto-tester
npx playwright install # Install browser dependencies
```

## Usage

### Running Tests

You can run tests using the CLI:

```bash
npx auto-test run --config path/to/test-config.json
```

Options:
- `--config, -c`: Path to test configuration file (required)
- `--tags, -t`: Tags to filter tests (comma separated)
- `--github-owner`: GitHub owner/organization name
- `--github-repo`: GitHub repository name
- `--github-token`: GitHub personal access token
- `--headless`: Run tests in headless mode
- `--screenshots`: Capture screenshots on failure
- `--video`: Record video of test execution
- `--create-issues`: Create GitHub issues for test failures
- `--performance`: Capture performance metrics
- `--accessibility`: Check for accessibility issues
- `--visual`: Perform visual validation
- `--report-dir`: Directory to store test reports