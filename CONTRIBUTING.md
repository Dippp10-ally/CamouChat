## Contributor Navigation & Contribution Verification Workflow

CamouChat follows a plugin-based and modular architecture.
This repository acts as the umbrella repository for the complete CamouChat ecosystem.

Many components, integrations, automation modules, and internal systems are maintained across multiple repositories under the `CamouChat-Team` organization. These repositories are not isolated projects — together they form the complete CamouChat platform.

To avoid contributor confusion:

* Contributors should explore all repositories under the organization before starting development.
* Issues, plugins, integrations, and platform-specific implementations may exist in separate repositories.
* Some repositories may depend on or extend functionality from others.
* Contributors must always read the `CODE_OF_CONDUCT.md` and contribution guidelines of the target repository before contributing.

## Contribution Workflow

Contributors are expected to work in the actual implementation/plugin repositories where the real codebase exists.

### Contribution Steps

**1. Select and work on issues in the appropriate plugin/code repository.**

**2. After the PR is successfully merged in the target repository:**
* Open a verification issue in the umbrella `CamouChat` repository.

**3. Raise an Issue ,the verification issue must contain:**

   * Contributor name
   * Open source program/organization name (if applicable)
   * Actual merged PR link
   * Repository name
   * Short summary of the contribution
 
**4. After admin verification:**

   * Contributor may create a PR in the umbrella repository updating the contribution tracking file ( `PR_validation.md`).

This workflow exists to maintain centralized contribution tracking, contributor visibility, and ecosystem-level coordination across the modular CamouChat architecture.

This will improve:

* contributor onboarding
* contribution verification
* ecosystem discoverability
* cross-repository collaboration
* organization-wide contribution tracking
