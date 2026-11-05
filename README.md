# Cobalt Ridge Platform Release Repository

This repository is the release-control home for the Cobalt Ridge platform
organization. It holds build registries used when onboarding services
into the production platform.

## Build registry layout

* `catalog/consolidated/services.json` — a consolidated snapshot generated
  periodically from the team registries. The snapshot in this repository
  is stamped with its `last_refresh` date and can lag behind recent
  registrations.
* `catalog/teams/<team>/builds.json` — the build registry maintained by
  each owning team. Team registries are refreshed on every release and are
  the authoritative source of build artifacts; a build registered after the
  latest consolidation pass exists only here.

Each artifact record carries the container image, the container port and
a `deprecated` flag indicating whether the build is still supported for
production onboarding. When several builds are registered for a service,
the one with the most recent `released_at` is the current build.

## Release records

* `release/2026-Q4/` — records for the Q4 2026 onboarding program.
