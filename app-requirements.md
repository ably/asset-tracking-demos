# Ably Asset Tracking Demo App Requirements

These requirements have been broken down into a couple of milestones, with the goal of keeping the scope of work required to reach each milestone realistic.

## Milestone 1: Simplistic

For this milestone we prove that we can bring the key components together, demonstrating that they effectively interoperate to deliver the core customer-facing functionality.

All apps:

- Should authenticate with Ably using a raw API key, which may be embedded in the app
- Must Consume the SDK from the same public distribution point that we release to normally (i.e. Maven Central / SPM)
- Must use latest versions of development tools / foundational frameworks as provided by Google or Apple
- Should prefer best practice, modern patterns, as recommended by Google or Apple
- Should enable lint / static analysis from the outset
- Should treat all warnings as errors from the outset (keep it clean)

Publisher app (the rider):

- May embed the Mapbox access token in the app
- Must ensure that GPS permission is requested when using the app
- Should create an AAT trackable when given an ID and a destination
- Make sure the publish rate of GPS locations is dependent on the battery level and on whether someone is subscribing from the feed as well as proximity to destination
- Must continue to run when the app is sent to background
- Only needs to support publishing of a single trackable at any given time
- Should not display a map (unnecessary overhead)

Subscriber app (the consumer / customer):

- Must allow an trackable ID to be entered to track
- Must display a map, with a tracker showing the rider's location
- May request GPS permission when using the app in order to show the user's current location, though this is not a requirement
- Should only support tracking of a single trackable at any given time
- Android:
  - Must use Google Maps to render the map
  - May embed the Google Maps API key in the app
- iOS:
  - Must use Apple Maps to render the map

## Milestone 2: Production

For this milestone we improve on the simplistic solution by bring in additional features that more accurately represent the real world requirements of a production quality app.

All apps:

- Must use [the demo backend service](https://github.com/ably/asset-tracking-backend-demo), via HTTPS
- Must authenticate with Ably using token authentication, with tokens obtained from the backend service
- Must not embed any API keys or access tokens in the app

Publisher app (the rider):

- Must use the backend service to accept delivery jobs
- Must source Mapbox access token from the backend service
- Should make sure the publish rate of GPS locations is dependent on the battery level and on whether someone is subscribing from the feed as well as proximity to destination
- Must support stacked deliveries - publishing updates for more than one trackable at any given time

Subscriber app (the consumer / customer):

- Must use the backend service to generate an order for delivery - TBC whether this is simply by entering order id into the app, or perhaps by getting a list of active orders that can be accepted
- Should configure the resolution based on the user’s behaviour (if the app is in the background, or the user is looking at a different page: we don’t need a high resolution)
- Should ideally, when the tracker is 10 m from the address, remove the map and mention the food is here
- Android:
  - Must source Google Maps API key from the backend service

## Milestone 3: Enhanced

This milestone is yet to be scoped out fully but it is expected to add:

- the concept of "rider state", likely including "accepted the delivery", "waiting at the merchant", "has picked up your deivery" / "is on the way", "is nearby", "is here", "will not deliver" and "delivered"
- capability to build the demo app to use Mapbox maps rendering, instead of Google on Android/Web, or Apple on iOS - a choice that the app source code configuration should allow at build time (not a runtime switch)
- support for push notifications to the subscriber app, including key events such as when the delivery has been picked up from the merchant and when the item has been delivered

## Future Milestones

### Idea: Multiple Map Rendering Engines

Dreaming big... This is something that would be really useful for demonstration purposes, in respect of showing performance - as well as behavioural - differences between different map rendering engines, when fed by Ably Asset Tracking.

Engines include:

- Here
- Mapbox
- Google Maps
- Apple Maps
- Bing Maps
- Tencent
