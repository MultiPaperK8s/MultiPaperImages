# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
### Added
- Add ubuntu-jammy distribution (build + Docker support)
- Add ubuntu-focal distribution (build + Docker support)

### Changed
- Update Eclipse Temurin Ubuntu image from 17.0.3_7-jre -> 17.0.5_8-jre-(jammy|focal)
- Update Eclipse Temurin Debian image from 17.0.3_7-jdk -> 17.0.5_8-jdk
- Update Debian slim image from stable-20220622-slim -> stable-20221205-slim
- Update Debian slim dependency tzdata (using bullseye-updates repository) 2021a-1+deb11u4 -> 2021a-1+deb11u8
- Update Debian slim dependency curl 7.74.0-1.3+deb11u1 -> 7.74.0-1.3+deb11u3
- Update Debian slim dependency locales 2.31-13+deb11u3 -> 2.31-13+deb11u4
- Docker images tags from Ubuntu generic to specific ((multipaper|multipaper-master) -> (multipaper|multipaper-master)-(jammy|focal))
- Update Alpine init image from Alpine 3.16.0 -> 3.17.0
- Update Alpine init image dependency libintl 0.21-r2 -> 0.21.1-r1
- Update Alpine init image dependency gettext 0.21-r2 -> 0.21.1-r1
- Downgrade Ubuntu focal dependency dumb-init 1.2.5-2 -> 1.2.2-1.2
- Update Multipaper to 1.19.2

### Removed
- Generic ubuntu distribution

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