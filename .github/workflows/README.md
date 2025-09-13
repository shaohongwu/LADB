# GitHub Actions Workflows

This directory contains GitHub Actions workflows for the LADB Android application.

## Workflows

### build.yml - Main Build Workflow
- **Triggers**: Push to main/master branches, Pull Requests
- **Features**:
  - Sets up Java 11 and Android SDK
  - Caches Gradle dependencies for faster builds
  - Runs lint checks and tests
  - Builds both debug and release APKs
  - Uploads APK artifacts and lint reports

### release.yml - Release Build Workflow  
- **Triggers**: Release published, Manual dispatch
- **Features**:
  - Builds release APK when a new release is created
  - Automatically attaches APK to GitHub releases
  - Uploads APK as build artifact

## Build Requirements

- **Java**: 11 (compatible with Android Gradle Plugin 8.9.3)
- **Android SDK**: API level 35 (as specified in app/build.gradle)
- **Gradle**: 8.11.1 (as specified in gradle wrapper)
- **Minimum API**: 26
- **Target API**: 35

## Artifacts

The workflows generate the following artifacts:
- `debug-apk`: Debug version of the app
- `release-apk`: Release version of the app  
- `lint-reports`: Android lint analysis reports

## Manual Workflow Dispatch

The release workflow can be manually triggered from the Actions tab in GitHub if needed for testing or custom builds.