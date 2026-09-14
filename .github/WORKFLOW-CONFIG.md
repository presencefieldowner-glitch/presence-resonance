name: Workflow Configuration Schema

# This file documents the extensible workflow system
# Use this to understand and extend the workflow ecosystem

workflows:
  dev-environment:
    description: "Scheduled development environment setup"
    triggers: [schedule, manual, dependency-changes]
    purpose: "Ensure dev environment is always ready to go"
    extensibility:
      - Add more build steps for new packages
      - Extend to additional Node versions
      - Integrate container image builds

  quality-gates:
    description: "Comprehensive quality assurance"
    triggers: [push, pull-request, manual]
    checks:
      - type-checking
      - linting
      - unit-tests
      - build-verification
      - security-scanning
      - dependency-audits
    extensibility:
      - Add e2e testing
      - Add performance benchmarks
      - Add code coverage reporting
      - Add SonarQube integration

  deploy:
    description: "Multi-environment deployment pipeline"
    triggers: [push-to-main, manual]
    environments: [development, staging, production]
    steps:
      - prepare (versioning, build-ids)
      - build-api (TypeScript/Express)
      - build-web (Next.js)
      - test-integration
      - deploy (environment-dependent)
    extensibility:
      - Add infrastructure provisioning (Terraform/CloudFormation)
      - Add smoke testing post-deployment
      - Add rollback mechanisms
      - Add canary deployments
      - Add database migrations

global-extensions:
  node-versions:
    current: [20.x]
    extensible: true
    add-versions: "Modify matrix.node-version in workflow files"

  environments:
    current: [development, staging, production]
    extensible: true
    add-environments: "Add to workflow_dispatch.inputs.environment.options"

  cache-strategies:
    pnpm-cache: "Enabled globally"
    artifact-retention: "7 days (configurable)"
    extensibility: "Add Docker layer caching, build output caching"

  secrets-management:
    structure: "Use GitHub Environments for credentials"
    extensibility: "Add environment-specific secrets as needed"

custom-hooks:
  pre-build: "Define in .github/hooks/pre-build.sh"
  post-build: "Define in .github/hooks/post-build.sh"
  pre-deploy: "Define in .github/hooks/pre-deploy.sh"
  post-deploy: "Define in .github/hooks/post-deploy.sh"
