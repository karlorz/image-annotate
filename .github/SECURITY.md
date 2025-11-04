# Security Policy

## Supported Versions

Currently, we support the following versions with security updates:

| Version | Supported          |
| ------- | ------------------ |
| 0.1.x   | :white_check_mark: |
| < 0.1   | :x:                |

## Reporting a Vulnerability

If you discover a security vulnerability in this project, please follow these steps:

1. **DO NOT** create a public GitHub issue for the vulnerability.
2. Send a detailed report to the maintainer via:
   - GitHub Security Advisories (preferred)
   - Email to the maintainer (check package.json for contact)

### What to include in your report:

- Description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if any)

### Response Timeline:

- Initial response: Within 48 hours
- Status update: Within 1 week
- Fix timeline: Depends on severity
  - Critical: Within 1-2 days
  - High: Within 1 week
  - Medium: Within 2 weeks
  - Low: Next regular release

## Dependencies

This project uses automated dependency updates via Dependabot to ensure dependencies are kept up to date with the latest security patches.

## Best Practices

When using this library in production:

1. Always use the latest stable version
2. Monitor security advisories
3. Implement proper input validation in your application
4. Follow React security best practices