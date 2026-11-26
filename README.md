# Route Builder V20 — workspace and recorded-road rebuild

Replace index.html and demo.html in the existing GitHub Pages repository. The existing account/cloud data code remains in place. Back up your library first; Demo changes reset on refresh. No Google Maps API or key is used.

## Workspaces
Routes: create/rename/import, saved versions. Stops: existing address and stop tools. Build: offline recorded GPX sequencing, optional online named-street matching, recorded-road optimization, manual reorder, auto-renumber and auto-GPX. Review: replay, export, comparison and dump-trip markers. Settings: existing map layers and imagery controls. Run: existing Driver Mode, with compact navigation sizes and Complete/Not Out.

## Sequencing and safety
- Follow recorded GPX keeps every coordinate and orders estimated right-side stops along the track. Same-street address neighbors help infer a local street axis; this is not verified street data. Ambiguous stops are flagged; unmatched pins are retained at the end.
- Named streets uses the existing public online road service to label recorded passes, not to redraw the GPX. If the service fails, the route is unchanged. Partial matches are flagged.
- Flagged stop list in Build: choose a candidate pass and inspect the highlighted segment and direction on the map, then confirm if correct. Change incorrect pins/pickup side in Stops. Re-run Follow recorded GPX to apply confirmed matches. All customers are preserved.
- Optimize and Generate GPX now use only exact shared recorded vertices and subdivisions of actual GPS segments, never proximity-based joins. Optimization only saves a separate shorter proposal; it may reject a route if the existing GPS trace cannot form a connected path, contains gaps, has unresolved matches or has dump markers. Manual generation likewise rejects disconnected or uncertain matches. This is conservative, not a full truck-road network planner. It cannot certify legal turns, access, backing safety or service order without review. Original data is preserved as a version.
- Review both paths, stop order and replay before driving. The generated path uses original sampled geometry rather than moving the recorded points. Exact shared coordinates are not a guarantee of legal intersection connectivity.

## Validation
JavaScript syntax checked for both pages. Demo 3: 2,998 track points / 1,014 pins; offline matching places 1,000, flags 35 including 14 unassigned. All 1,014 are retained. Optimizer refuses this input until review. Synthetic exact-vertex repeat-loop test verifies shortened path without diagonal shortcuts. Browser navigation was blocked in the development environment; live maps, online service, account sync, actual device layout, GPX replay and Driver Mode require user testing before production use.
