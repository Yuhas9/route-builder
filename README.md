Route Builder V9 – visual GPX navigation

Turns in Driver Mode enables GPS-based approximate turn cues. No voice or automatic rerouting. Cues derive from GPX geometry, not verified road instructions. Overlaps and poor GPS may suppress cues. Use only when safe; obey road signs.

V10: Manual turns uses GPX geometry without location permission; explicit previous/next turn controls; approximate stop-based advance when unambiguous. Live turns and GPS remain optional. No voice or path recording.

V11: Manual turns are bounded to the selected work order along the saved GPX. Checking off advances to the next pending order; turn controls preview only that leg. Ambiguous matches or backward legs warn instead of inventing directions. No GPS or voice in manual mode.

V12: Driver map heading-up (GPX-based), north-up and free rotation; +/-45 degree controls, Shift+wheel and two-finger rotation, center and zoom toggles. Rotation uses external Leaflet Rotate 0.2.8; if unavailable the map remains north-up. Browser/device testing required.

V13: selecting a map pin or work order highlights and scrolls to that order without auto-panning or rotating. On narrow portrait screens, tapping a pin opens the order list. Resume center, advancing a turn or completing a stop resumes automatic navigation framing. Live GPS updates continue while inspecting a stop, but auto-follow is paused.

V14: Disable Leaflet marker focus auto-pan; keep driver markers stable across selection; pause navigation camera on marker pointer-down and preserve list selection.

V15: phone-only driver layout with slide-up searchable stop list, compact navigation banner, map and extra-action menus, large service buttons, and separate stop preview. Tablet/desktop retain the V14 layout. Previewing another stop pauses automatic camera following without changing the active work order; return to current or explicitly use the previewed stop. Layout checked at representative phone/tablet dimensions in Chromium; actual iPhone Safari and live map/auth testing still recommended.

V16: Route setup & sequencing (Master and Demo)
- Create/name an empty route, GPX-only, CSV-only or GPX+CSV; merge matching address/coordinate pairs rather than duplicate the same customer. Rename or import into an existing route; replacing an existing driving track creates a separate route.
- Sequence from GPX makes a separate copy using recorded segment direction and collection-side geometry; named-street recalculation remains available as an online check. Road matching is approximate, not proof of actual collection.
- Optimize Sequence compares a greedy recorded-road traversal and recorded-order path rebuild, preserving all customers and recorded start/end. It rejects proposals longer than the recorded track. Generate GPX from Stops uses the chosen stop order. Both use only observed directed GPX segments with up to 6 m vertex snapping; no routing across unrecorded streets. These are proposed routes, not truck-validated navigation. Closely spaced roads, GPS noise, intersections, one-way changes and access restrictions require review. Existing dump markers block rebuilding until collection and dump trips are split; unmarked dump travel is not detected automatically.
- Auto-Renumber ON shifts intervening stops; OFF swaps the two positions rather than allowing duplicate order numbers. Auto-Update GPX is optional (off by default). Changes can be undone. Manual changes preserve the recorded version and stale paths warn in Driver Mode and at export.
- Compare recorded and current map geometry, show mileage, export current GPX and recorded track GPX. Original export preserves track coordinates, not necessarily source file metadata/timestamps. Existing V15 driver layout and authentication scripts remain in place.
- CSV rows without coordinates can be located using the existing Find address / Place pin controls; GPX generation needs a recorded road network and located confirmed customers.
- Tested with Demo 3 (2,998 recorded points, 1,014 customers) in the offline engine and both pages in Chromium with mocked browser storage, no external services. Recorded 28.90 mi; proposed 28.61 mi. This is an estimated geometric distance, not measured truck mileage. Live maps, cloud login/save, actual iPhone Safari, tablet UI and truck suitability not verified in this test. Test in Demo before using Master/live operations.
- Deployment: upload index.html and demo.html to the existing repo; engine is embedded. Other files are included for continuity. Back up your route library first.

## V17 tablet driver layout
Tablet/desktop Driver Mode has a 47/53 split, live filter counts, status icons, compact map options, and persistent large Complete and Not Out buttons. Existing phone layout and V16 sequencing retained. Use controls only when parked.

V18: Full website release (Master and Demo)
- Route setup & sequencing includes Recalculate using named streets (online). Uses public OpenStreetMap Overpass endpoints to retrieve road geometry and named streets; creates a separate proposal using mapped connected directed edges and approximate address-side matching. Road queries send geographic bounding boxes to the external service, not the customer CSV. Requires recorded GPX and located customers. If data is unavailable, customers are unmatched, or no connected path exists, retains the current route. Existing dump-trip markers block recalculation. No automatic online update after manual edits: use recorded-road rebuild or recalculate online as a separate proposal. Online route generation is heuristic and may produce longer proposals; turn restrictions, dimensions, safe turnaround locations and actual road conditions are not fully modeled. Review before field use.
- Original and revised GPX versions remain selectable; comparison shows a dashed blue recorded track and green revised track. Replay can use original or current GPX, and stale revised paths are blocked until rebuilt. Navigation display offers Full, Compact and Mini; iPhone defaults to Compact, tablet to Full. Existing V17 layout and authentication/storage keys preserved.
- Both HTML files pass Node JavaScript syntax checks. Synthetic online-network engine tests check right-side sequencing, retaining stops, start/end, unmatched addresses and one-way failure. Live Overpass, authentication, maps, and device behavior were not tested in this release.
- Upload index.html and demo.html to your existing GitHub repository to replace the current pages; back up your route library first. No test page is needed.
