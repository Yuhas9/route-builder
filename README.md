# Route Builder V24 — sequencing feedback and cancellation
Replace index.html and demo.html. Back up routes first. V24 is visible in the Build heading.

Offline sequencing now cancels any pending online lookup and reports the count of changed stop numbers, matched pins and flags in the Build workspace. The active version is shown there; map zoom is retained on resequencing. Online lookups can be canceled and time out after 25 seconds; no late response can change the route. Optimization and GPX regeneration still reject ambiguous matches, dump markers and disconnected recorded roads; no promise of a shorter route. No Google Maps API. V23 pin numbers and V22 appearance retained.
