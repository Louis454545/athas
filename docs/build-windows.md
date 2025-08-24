# Windows Build Workflow

This workflow (`build-windows.yml`) provides a Windows-only build of the Athas application that can be triggered manually.

## How to Use

1. Go to the **Actions** tab in your GitHub repository
2. Select **"Build Windows"** from the workflow list
3. Click **"Run workflow"**
4. Optionally uncheck "Upload build artifacts" if you only want to test the build without saving artifacts
5. Click **"Run workflow"** to start the build

## What It Does

- Builds the Athas application for Windows only
- Runs quality checks (TypeScript type checking and Biome linting)
- Creates Windows installer packages (MSI format)
- Uploads the build artifacts for download

## Build Artifacts

After a successful build, you can download:
- **athas-windows-msi**: Windows MSI installer package
- **athas-windows-nsis**: Windows NSIS installer (if generated)

## Build Requirements

The workflow automatically sets up:
- Bun (JavaScript package manager)
- Rust toolchain
- Required dependencies and caching

## Differences from Release Workflow

This workflow differs from the main release workflow in that it:
- Only builds for Windows (faster execution)
- Does not create GitHub releases
- Does not require version tags
- Can be triggered manually anytime
- Uploads artifacts instead of publishing releases