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

### Generating Test Configurations

You can generate test configurations interactively:

```bash
npx auto-test generate --output path/to/output.json
```

Options:
- `--output, -o`: Output file path

## Test Configuration

A test configuration file is a JSON file containing an array of test cases:

```json
[
  {
    "name": "Login Test",
    "description": "Tests the login functionality",
    "tags": ["login", "smoke"],
    "steps": [
      {
        "name": "Navigate to login page",
        "action": {
          "type": "navigate",
          "url": "/login"
        }
      },
      {
        "name": "Enter credentials",
        "action": {
          "type": "fill",
          "selector": "#username",
          "value": "testuser"
        }
      },
      {
        "name": "Click login button",
        "action": {
          "type": "click",
          "selector": "button[type='submit']"
        },
        "validation": {
          "type": "url",
          "expectedUrl": "/dashboard"
        },
        "errorMessage": "Failed to login"
      }
    ]
  }
]
```

## Environment Variables

You can also configure the tool using environment variables:

- `GITHUB_OWNER`: GitHub owner/organization name
- `GITHUB_REPO`: GitHub repository name
- `GITHUB_TOKEN`: GitHub personal access token
- `APP_URL`: URL of the app interface
- `ADMIN_URL`: URL of the admin interface
- `APP_USERNAME`: Username for app login
- `APP_PASSWORD`: Password for app login
- `ADMIN_USERNAME`: Username for admin login
- `ADMIN_PASSWORD`: Password for admin login

## Reports

After test execution, the tool generates various HTML reports:

- Test Report: Summary of all test results with details
- Performance Report: Performance metrics captured during testing
- Accessibility Report: Accessibility issues detected during testing
- Visual Testing Report: Visual regression test results

## License

MIT