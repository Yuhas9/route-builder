Route Builder V9 – visual GPX navigation

Turns in Driver Mode enables GPS-based approximate turn cues. No voice or automatic rerouting. Cues derive from GPX geometry, not verified road instructions. Overlaps and poor GPS may suppress cues. Use only when safe; obey road signs.

V10: Manual turns uses GPX geometry without location permission; explicit previous/next turn controls; approximate stop-based advance when unambiguous. Live turns and GPS remain optional. No voice or path recording.

V11: Manual turns are bounded to the selected work order along the saved GPX. Checking off advances to the next pending order; turn controls preview only that leg. Ambiguous matches or backward legs warn instead of inventing directions. No GPS or voice in manual mode.

V12: Driver map heading-up (GPX-based), north-up and free rotation; +/-45 degree controls, Shift+wheel and two-finger rotation, center and zoom toggles. Rotation uses external Leaflet Rotate 0.2.8; if unavailable the map remains north-up. Browser/device testing required.

V13: selecting a map pin or work order highlights and scrolls to that order without auto-panning or rotating. On narrow portrait screens, tapping a pin opens the order list. Resume center, advancing a turn or completing a stop resumes automatic navigation framing. Live GPS updates continue while inspecting a stop, but auto-follow is paused.

V14: Disable Leaflet marker focus auto-pan; keep driver markers stable across selection; pause navigation camera on marker pointer-down and preserve list selection.

V15: phone-only driver layout with slide-up searchable stop list, compact navigation banner, map and extra-action menus, large service buttons, and separate stop preview. Tablet/desktop retain the V14 layout. Previewing another stop pauses automatic camera following without changing the active work order; return to current or explicitly use the previewed stop. Layout checked at representative phone/tablet dimensions in Chromium; actual iPhone Safari and live map/auth testing still recommended.
