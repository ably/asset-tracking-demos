> [!IMPORTANT]
> As of September 2025, Ably Asset Tracking has been sunsetted and is no longer being maintained.

# Ably Asset Tracking Demos

_[Ably](https://ably.com) is the platform that powers synchronized digital experiences in realtime. Whether attending an event in a virtual venue, receiving realtime financial information, or monitoring live car performance data – consumers simply expect realtime digital experiences as standard. Ably provides a suite of APIs to build, extend, and deliver powerful digital experiences in realtime for more than 250 million devices across 80 countries each month. Organizations like Bloomberg, HubSpot, Verizon, and Hopin depend on Ably’s platform to offload the growing complexity of business-critical realtime data synchronization at global scale. For more information, see the [Ably documentation](https://ably.com/documentation)._

## Overview

This repository contains content which is common to the suite of demos, written by Ably, demonstrating our
[Asset Tracking solution](https://ably.com/solutions/asset-tracking) (AAT).

The demos present functionality matching that expected for the typical use case for AAT,
being the tracking of deliveries to customers.
Those deliveries could be food, groceries or other packages ordered for home delivery.

### Demo Source Code Repositories

- **Backend Service**: Used by all the demo apps. Exposes a REST API for creating and assigning deliveries.
  - [Firebase Functions + Firestore](https://github.com/ably/asset-tracking-backend-demo)
- **Rider App**: Used by delivery riders / drivers. The publisher.
  - [Android](https://github.com/ably/asset-tracking-android-rider-app-demo)
  - [iOS](https://github.com/ably/asset-tracking-ios-rider-app-demo)
- **Subscriber App**: Used by customers / consumers, to track their delivery.
  - [Android](https://github.com/ably/asset-tracking-android-customer-app-demo)
  - [iOS](https://github.com/ably/asset-tracking-ios-customer-app-demo)
  - [Web](https://github.com/ably/asset-tracking-web-customer-app-demo)

## Requirements

- [Demo Apps](app-requirements.md)
