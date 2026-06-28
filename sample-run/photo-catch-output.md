# Marshal Output: `photo-catch-input.md` (+ rack photo)

> What Marshal returned when run on the demo doc WITH `photo-catch-rack-photo.jpg` attached.
> Produced in a cold-test: a blank-slate reviewer given only the Marshal folder, this input, and the
> photo, with no other context. This is the run that proves the photo cross-check, the part nobody
> else does.

## Verdict: RETURN TO TECH

The doc reads as service-ready on the form alone: front door open, every documented subsystem
clears its support-critical fields, no internal contradictions in the text. On the form, this would
pass. The photo is what stops it.

The Cameras section is marked **N/A, no camera system on this site.** But the attached Rack Room
photo shows a clearly labeled **NVR** mounted in the rack. A network video recorder is a camera
system. The form denies a system the photo proves is installed. That is a contradiction the tech
has to resolve, so the doc cannot be accepted as written.

## Order of operations

**0. Front door: PASS.** OvrC attested. Tier-2 documented: VPN (UniFi/WireGuard) + Crestron Home reach (DDNS, RMS, App/HTTPS/CIPS ports).

**1. Presence.** Present and documented: Network, Control, Zone Audio, Distributed Video, Lighting. Marked N/A: Shades, Alarm, Access Control, **Cameras.**

**2. Support-critical fields.** Every documented subsystem clears. Nothing missing on the form.

**3. Photo cross-check (the decisive step).** Reading `photo-catch-rack-photo.jpg`:
- Confidently legible in the rack: a labeled **NVR**, two **Sonos** ports (House Music 1 and 2), and a **Crestron SWAMP expander.**
- Sonos and the SWAMP expander match the documented Zone Audio. No conflict there.
- The **NVR does not.** Cameras is marked N/A, yet the recorder is physically in the rack and labeled. **Gear in the photo, denied by the form.** This is the highest-value catch.

**4. Advisories.** None pending until the contradiction is resolved.

**5. Decision: RETURN TO TECH.**

## Punch list to the submitting tech

1. Cameras is marked N/A, but the Rack Room photo shows a labeled NVR in the rack. Either document the camera system or correct the N/A. If it is real, add:
   - NVR brand + model, and how support reaches it (IP / remote).
   - Camera brand(s) and total count on the recorder.
   - Which PoE switch powers the cameras.
   - Integrated with control system? (yes/no)

Resolve that one item and resubmit. Everything else is service-ready.

## Why this is the catch nobody else makes

A form-only checker accepts this doc: every field it asks about is filled or legitimately N/A. The
gap is not a blank, it is a **denial the photo disproves.** Marshal reads the marked-up rack shot,
builds a device inventory, and reconciles it against what the form claims is present. The form can
say a system is not there. The photo does not lie.
