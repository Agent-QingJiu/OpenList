# OpenList for Synology DSM 6.2.3

This repository builds an installable Synology SPK for the confirmed target:

- Device/platform: DS3615xs / `synology_bromolow_3615xs`
- DSM: `6.2.3-25426`
- Package architecture: `bromolow` (x86_64)
- Upstream source: [OpenListTeam/OpenList](https://github.com/OpenListTeam/OpenList)
- Build runner: GitHub Actions (no local VMware/Ubuntu build VM)

## Build

Open **Actions → Build OpenList SPK (DSM 6.2.3) → Run workflow**.

The workflow checks out the official OpenList source, runs its upstream release build (including the official frontend distribution), assembles the DSM package, and uploads the `.spk` as a workflow artifact.

The package uses OpenList's standard data directory under the Synology package variable directory. The default web port is OpenList's upstream default, **5244**.

## Data and service

- Package service is managed by DSM Package Center.
- OpenList data, database, index, temporary files, and logs are stored under the package variable directory.
- Upgrade builds replace the application binary while retaining the package variable directory.
- The uninstall hook stops the service; it does not explicitly erase the data directory.

## Important

This is an initial packaging build. A successful GitHub build validates compilation and archive assembly, but the first installation and lifecycle test must still be performed on the actual DSM 6.2.3-25426 device before treating the package as production-ready.

OpenList is licensed under AGPL-3.0. The upstream license is included in the package.
