roles, policies.
# AWS IAM — Basics (Sept 26)

- **IAM (Identity & Access Management)** = service for controlling access to AWS resources.
- Core entities:
  - Users (individuals, login with username/password or access keys).
  - Groups (collection of users with common permissions).
  - Roles (temporary access, assumed by services or users).
  - Policies (JSON docs that define permissions).
- Best practice: 
  - Follow least privilege.
  - Use roles for services instead of hardcoding access keys.
  - Enable MFA (multi-factor authentication).
