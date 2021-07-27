---
title: Adobe Sign Integrations Product Versions and Lifecycle
description: Learn how to set up Adobe Sign Integrations
audience: External
---
# Product versions and lifecycle {#version}

The Adobe Sign versioning convention and support lifecycle for integrated services aligns with other Adobe products that you may be familiar with.

## Version numbers 

The package version uses a three-part numbering system to identify the sequential build number of the released version and the relative import of the upgrade in terms of new or changing content. 

The version number follows this pattern: N.m.p 

Where, N = Major version; m = Minor version; p = Patched version.

For example, an integration package version 23.2.1 indicates a release status of:

* Major version: 23
* Minor version: 2
* Patch version: 1

As engineers develop new “builds” of the package, they increment the version number according to the nature of the updates to the code.

* Major version changes involve a significant addition in features or an important change to the core systems.
* Minor version updates include smaller feature updates and security patches. Adobe Sign may require an upgrade to the latest patched version in case of security updates or to address a reported item.
* Patch versions are almost exclusively bug fixes and UI adjustments

>[!NOTE]
>
>All versions are not released to the public as the product iterates in development. So, there might be significant jumps in the patch version between releases.

The admins must keep their version up-to-date to ensure that the account has full access to all the features and all known security issues are patched. Adobe Sign may require an upgrade to the latest patched version in the case of a security concern or to address a critical system issue.

## Version support lifecycle

The version support lifecycle of an Adobe Sign integration product is defined based on the major version of the package, and indicates the time frame that Adobe Sign is actively supporting the individual version of the integration.

Adobe Sign supports the current version of a package, and the previous two major versions (inclusive with all related minor and patch updates). Major versions are expressed as follows:

* Current version (N): The latest major version of the package
* Previous version (N-1): One major version behind the latest version
* Last supported version (N-2): Two major versions behind the current version

For example, if the current available version of the package is 23.2.1, then:

* Current major version (N) is 23
* Previous major version (N-1) of this package is 22
* Last supported major version (N-2) of this package is 21
* Every version older than 21.0.0 is unsupported

 ![Version chart](images/version_chart.png) 

## Version service lifecycle

The version service lifecycle defines the full scope of when the service is usable. The timeline matches the version support lifecycle with the addition of a 90-day grace period that allows customers to complete their upgrade.

* During the grace period of an unsupported version, support is only provided to upgrade to a newer version, not to maintain an unsupported version
* After the grace period, the version falls out of service

* Adobe Sign will not accept requests from versions that are out of service
* Once the integration is upgraded to the current version, communications between Adobe Sign and the integration will resume normally

 ![Shut down period](images/shutdown_period.png) 

Contact your reseller or customer support if you have any questions.
