# Containers for Base Image Builds

[![GitHub Container Registry](https://img.shields.io/badge/ghcr-container%20registry-blue)](https://ghcr.io/tibia-oce)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

This repository contains a collection of base Docker images that are used for container builds in other repositories. These images are designed to streamline the build process and ensure consistency across different projects by providing pre-configured environments with necessary dependencies.

<br>

## Usage

To use one of these base images in your own project:

1. Pull the image from GitHub Container Registry:
   ```bash
   docker pull ghcr.io/tibia-oce/blacktek-arm:latest

<br>

## Images Overview

### 1. **Blacktek (ARM64)**

[![Blacktek Build](https://github.com/tibia-oce/containers/actions/workflows/blacktek.yml/badge.svg)](https://github.com/tibia-oce/containers/actions/workflows/blacktek.yml)

- **Dockerfile**: `blacktek/Dockerfile.arm`
- **Description**: This base image is used for building the ARM64 version of the Black-Tek game server. It includes essential tools such as `vcpkg`, `premake`, and common build dependencies required for cross-compilation to ARM64.
- **Registry**: Available at [ghcr.io/tibia-oce/blacktek-arm](https://github.com/orgs/tibia-oce/packages/container/package/blacktek-arm)
  
  **Key Dependencies:**
  - Premake for project generation.
  - Vcpkg for managing external dependencies.
  - ARM64 cross-compilation support.
