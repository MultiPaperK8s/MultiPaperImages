# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
- Finalise release for 1.18.2 and archive it, building all other versions to maintain backwards compatibility.
- Update Master and Server (container versions 1.18.2 and builds 47-96) from eclipse-temurin 17 Alpine 3.15.4 -> Eclipse Temurin 17.0.5+8 Alpine 3.17.0
- Update Debug (container version 0.0.1) from alpine 3.16.0 -> alpine 3.17.0
- Update dependencies for Master and Server (container versions 1.18.2 and builds 47-96) dumb-init=1.2.5-r1 -> dumb-init=1.2.5-r2
- Update dependencies for Debug (container version 0.0.1) libintl=0.21-r2 -> libintl=0.21.1-r1 and gettext=0.21-r2 -> gettext=0.21.1-r1

## [0.1.2] - 2022-06-07
### Changed
- Move Master JAR outside of work (data) directory (#4)

## [0.1.1] - 2022-06-05
### Added
- CHANGELOG.md

### Changed
- Update openjdk -> eclipse-temurin jdk 17

## [0.1.0] - 2022-06-04
### Added
- Dockerfile for debug
- Dockerfile for master
- Dockerfile for server