# Product Wizard

A complete development pipeline that guides users from initial idea to deployed application, built on top of [GitHub Spec Kit](https://github.com/github/spec-kit).

## What is Product Wizard?

Product Wizard extends Spec Kit with additional tooling and workflows to help developers at any level—from junior developers on their first project to non-technical founders with an app idea—build working software through guided, specification-driven development.

## Features

- **Idea to Implementation**: Complete pipeline from rough concept to working code
- **Universal Workflow**: Works for frontend, backend, AI development, architecture, and tooling projects
- **Flexible Scale**: Build tiny features in large projects or standalone MVPs
- **Beginner Friendly**: No prior knowledge of technical terms required
- **Built on Spec Kit**: Leverages GitHub's proven spec-driven development methodology

## Getting Started

This repository includes GitHub's Spec Kit as a submodule. To get started:

```bash
# Clone with submodules
git clone --recurse-submodules https://github.com/grigb/product-wizard.git

# Or if already cloned, initialize the submodule
git submodule update --init --recursive
```

## Project Structure

```
product-wizard/
├── spec-kit/          # GitHub Spec Kit (submodule)
└── README.md          # This file
```

## Documentation

- See the [Spec Kit documentation](./spec-kit/README.md) for the core methodology
- Additional Product Wizard documentation coming soon

## License

This project is not licensed and is not available for use. No license has been granted for this software. See the Spec Kit submodule for its license terms.
