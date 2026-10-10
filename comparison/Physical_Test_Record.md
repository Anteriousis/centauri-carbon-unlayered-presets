# Physical test record - first trial reported with defects

**Status: physical trial reported on 10 October 2026; print quality and support behavior need revision. This is not a successful validation of the presets.**

The owner supplied seven photographs and reported the observations below. The broken coupon is the **planar** specimen. The apparent block distortion was corrected by the owner to **seams changing position between the planar and inclined sections**, not warping. These corrections supersede any earlier interpretation.

The exact printed project, changes, installed nozzle, actual material, firmware, date of printing, and whether any toolhead contact occurred have not yet been confirmed. The prepared project was Centauri_FOUR_object_AB_curved_support_free.3mf (0.4 mm PETG profile, 0.20 mm layers). Its project SHA256 is c7bc7ef224bbc5d049bd8308d91be6c1e4b6e5facc2a7cd141ad6d63153235bd. Do not assume that file hash identifies the physical print until the owner confirms it.

## Reported observations

| Specimen or issue | Physical evidence / owner report | What remains unknown |
|---|---|---|
| Planar support coupon | Broken specimen; photo shows base separated into pieces | Whether break occurred during printing, removal, handling, or a strength test |
| Inclined support coupon | Owner saw supports start in midair and experience difficulty; photographs show substantial loose extrusion on one coupon | Exact failing support islands and whether the printed project matches the reviewed Preview |
| Support removal | Supports adhered too strongly to the part | Removal force, actual contact spacing and weighed support masses |
| Inclined curved block transition | Owner reports a gap where planar and inclined portions meet | Gap dimensions and whether it is cosmetic, an unbonded region or a larger separation |
| Inclined block seam | Owner identifies different seam positions in planar and inclined portions; explicitly says there is no warping | Exact start positions in the physically used paths |
| Stringing | Owner reports stringing; fine strands are visible in photographs | Moisture, temperature, retraction, nozzle cleanliness and actual material |
| Surface finish | Both photographed tops show bead texture and terrace bands; the owner does not see a clear winner | Which of photos 6 and 7 is planar; comparable lighting, roughness and repeatability |
| Clearance | No physical clearance conclusion established | Contact/rubbing observations and physical toolhead dimensions |

Photographs are retained in the local project evidence folder. They have not been uploaded to this public repository. Owner statements are distinguished from the read-only prepared-path checks below.

## Prepared-path follow-up

The saved project already has **seam_position = aligned**. Selecting that option again is not a demonstrated remedy for cross-section seam continuity. A shared seam location on the physical part needs to be selected and checked in both sections after their different slice transforms.

Saved support settings are: Follow layers; support on build plate only OFF; top/bottom contact distances 0.20/0.20 mm; XY distance 0.35 mm; top interface spacing 0.50 mm with two top interface layers. The modeled head allowance of 0.5 mm and worst-direction CAD clearance of about 0.584 mm are separate from these support and interlayer distances.

Read-only review of the prepared Preview finds the first inclined coupon support loop at X193.816-194.550, Y182.951-183.046, nozzle-tip Z2.622-2.630 mm. At the start of the loop, the highest earlier model line within an approximate 0.25 mm XY bead half-width is at Z2.000 mm, with no earlier support line within that radius. The tip-height difference there is 0.622-0.630 mm. Later points in the same loop overlap prior support lines at Z2.400 mm, leaving differences around 0.222-0.230 mm. This identifies **partial support anchoring at the section transition**, consistent with the reported midair start; it does not establish that every support floats or prove the cause of every defect. The calculation compares line-center tip positions, not measured bead surfaces. See [path review](reported_print_support_path_review.json).

The earlier curved-block review also identified newly advancing cap regions with tip-to-root line-height differences up to about 0.433 mm, despite nominal 0.20 mm layer spacing. These are not measured air gaps. The physical transition-gap report is consistent with that known uneven transition, but the exact cause is not proven. See [saved transition review](Support_Free_Curved_Blocks.md).

## Interpretation and next experiment

- Treat this as a first physical trial with defects, not a calibrated or safe-printing certificate. No conclusion about all-direction 5 degree clearance or firmware behavior follows.
- The 63.263 percent coupon support reduction remains a **sliced deposition estimate**. A failed support system does not establish usable physical savings; removed support masses have not been measured.
- No measured finish or strength improvement is established. Retain planar printing as the ordinary workflow while this trial is revised.
- First establish an ordinary planar material baseline for stringing and top-surface coverage. The prepared profile has 250 C nozzle temperature, 0.8 mm retraction at 30 mm/s and wipe ON; these are saved values, not confirmation of the actual print or optimum calibration.
- Next isolate one simple shallow-ramp surface comparison, verify a fully supported and bonded root-to-cap transition, and force/check the same physical seam location in both sections. This should precede another complex overhang comparison.
- Revise the coupon supports so every starting island has a real foundation from the bed or an earlier printed section. Vertical-world support direction is a candidate for review, not a validated fix. Re-slice, inspect deposition order/anchoring and run the native collision check before any print. Do not loosen head clearances to force a slice through.
- Only then tune support contact separation using a small contact specimen; increasing a support gap before fixing foundations can worsen unsupported extrusion. Aligning seams alone cannot repair an unbonded transition.

The 0.2 mm preset remains physically untested. No slicer settings, printer presets, models, or toolpaths were changed during this observation-record update, and no printer code was exported or sent.
