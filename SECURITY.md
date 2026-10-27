# Security

## Reporting a vulnerability

Report vulnerabilities privately to hola@invitas.co. Include the affected version, reproduction steps and impact without sharing real credentials or personal data. Please do not open a public issue for an unpatched vulnerability.

## Supported versions

Security fixes target the current release or the current `main` branch. Older versions do not have a separate support commitment.

## Secrets

Keep credentials outside the repository and use the deployment environment's secret store. Do not commit tokens, private keys or production configuration. Rotate any credential that may have been exposed.
