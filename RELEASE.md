# Release Process

This repository is configured to automatically create releases for Mac builds only.

## How it works

When a new tag is pushed to the repository:

1. **Mac builds are created**: The workflow builds both x86_64 and arm64 versions
2. **Universal binary is created**: The two architectures are combined into a single universal macOS app
3. **Release is created**: A GitHub release is automatically created with the Mac build attached

## Creating a release

To create a new release:

1. Create and push a new tag:
   ```bash
   git tag v1.0.0
   git push origin v1.0.0
   ```

2. The GitHub Actions workflow will automatically:
   - Build the Mac universal binary
   - Create a GitHub release named "AzaharPlus v1.0.0"
   - Upload the Mac build artifacts to the release
   - Generate release notes automatically

## Supported platforms

- **macOS**: Universal binary (Intel and Apple Silicon) ✅
- **Windows**: Not supported ❌
- **Linux**: Not supported ❌
- **Android**: Not supported ❌

The release artifacts will be available as `.zip` files on the GitHub releases page.