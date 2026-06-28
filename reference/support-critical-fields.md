# reference/support-critical-fields.md

> PROPOSED: first pass off the site-documentation platform's schema. Red-line freely: move fields between
> CRITICAL and nice-to-have, add what I missed, kill what does not matter.
>
> **CRITICAL** = if this is missing on a PRESENT subsystem, the doc cannot be ACCEPTED.
> Support cannot triage or resolve without it → RETURN TO TECH, naming the field.
> **Nice-to-have** = note it, do not block.
>
> The test for every field: *"If a client calls about this system and support opens this doc,
> can they actually do something, or are they blind?"* If blind without it, it is CRITICAL.

---

## Cross-cutting: Access & Credentials (the front door)

The single most common reason support is blind. Applies across subsystems.

**CRITICAL**
- OvrC attestation checkbox checked (Tier-1 remote reboot/visibility).
- Tier-2 remote path where control/managed network is present: VPN access detail + Crestron
  Home reach (processor IP / portal).

**Nice-to-have (kept in this doc for basic call-in support)**
- Client Wi-Fi credentials.
- Crestron Home advanced user password.

**Credentials handling (resolved):** the full, sensitive credential set lives in a separate
dealer-only document, not this site doc. The two basics above are safe to keep here because both
are harmless from offsite: a Wi-Fi password and the Crestron Home advanced user password only work
for someone already on the local network, so they grant a remote party nothing. They are included
purely so support can answer a client calling in about them. Anything that actually grants remote
access stays in the dealer-only doc. Missing credentials never block ACCEPTED; the access *method*
(OvrC, VPN, CH reach) is what matters for the gate.

---

## 1. Network

**CRITICAL**
- ISP: primary provider + service type. Backup provider if one exists.
- Core/primary switch brand + model.
- Router brand + model.
- Network IP range / scheme.
- Remote-access method: DDNS URL and VPN method/type (e.g. IPSec, UniFi/WireGuard).
- Wi-Fi brand + client SSID.
- PtP links: if present, what they connect.

**Nice-to-have**
- AV distribution switch brand.
- DDNS beyond URL, exact model revisions.

---

## 2. Control System

**CRITICAL**
- Brand.
- Main processor location.
- Processor IP / how advanced reaches it (Crestron Home access).
- Crestron-specific DDNS URL.
- Outside (forwarded) ports: App, HTTPS, CIPS.
- Touch panel locations.

**Nice-to-have**
- Firmware/program version.

---

## 3. Zone Audio

**CRITICAL**
- Amp types present + matrix/switcher brand.
- AVR brand (if present).
- **Zone-to-room mapping** (outputs): which zone serves which room. Without this, "no music in
  the kitchen" cannot be triaged.

**Nice-to-have**
- Every input exhaustively labeled (a few key sources is enough).
- Secondary/landscape amp brand (CRITICAL if it is the only amp serving an area).

---

## 4. Distributed Video

**CRITICAL**
- Matrix brand.
- **Output-to-room/display mapping**: which output feeds which room. Without it, "no picture in
  the den" cannot be triaged.

**Nice-to-have**
- All inputs exhaustively labeled (key sources is enough).

---

## 5. Lighting Control

**CRITICAL**
- Brand.
- System type: Centralized, Wireless, or Hybrid. For hybrid, note which areas are centralized vs
  wireless, so support knows what lighting still works when part of the system is down.
- Integrated with control system? (yes/no)
- Areas without lighting control (scope boundary).

**Nice-to-have**
- Device form factor.

---

## 6. Shades

**CRITICAL**
- Primary brand + type.
- Integrated with control system? (yes/no)
- Shade panel / power locations (where service happens).

**Nice-to-have**
- Secondary brand + type (CRITICAL if a distinct second system, not a minor add).

---

## 7. Cameras

**CRITICAL**
- NVR brand + model, and how to reach it (IP / remote).
- Camera brand(s).
- **Camera power source** (which PoE switch / injector): first thing checked on "cameras down."
- Total camera count on recorder.
- Integrated with control system? (yes/no)

**Nice-to-have**
- Door/gate station brand (CRITICAL if there is an intercom/entry workflow).

---

## 8. Alarm

**CRITICAL**
- Brand.
- System infrastructure + communication type + comm paths (how it reports, core to alarm service).
- Integrated with control system? (yes/no)
- Smoke/heat devices present? (life-safety awareness).
- Keypad locations.

**Nice-to-have**
- Full zone list.

---

## 9. Access Control

**CRITICAL**
- Brand.
- Number of doors + door locations.

**Nice-to-have**
- Credential/reader type.

---

## 10. Rooms (only for rooms in AV scope)

Per room that is in scope:

**CRITICAL**
- Video delivery method + sources available.
- Audio delivery method + sources available.
- Capability flags: touch panel / thermostat / lighting / powered shades (yes/no).

These let support map a room-based client complaint to the systems behind it.

**Nice-to-have**
- Exhaustive per-room source enumeration.

---

## 11. Equipment Locations (always present)

**CRITICAL**
- At least one equipment location called out (equipment closet, rack, or multimedia panel)
  with a photo. Every project has this; an empty section is an automatic RETURN TO TECH.
- The head-end locations support needs to find (rack, control processor, NVR, network core,
  amp/matrix) represented across the called-out locations.

*The photo is not decoration; it is the gear inventory. Techs mark up the rack and closet shots,
labeling each device, and the operator reads them (brands, models, and the markup labels) to
confirm what is installed and cross-check against the form. On a text/CSV-only export it cannot
see the photo and flags "confirm photo attached"; on the full PDF it reads it.*

**Nice-to-have**
- Every minor device location.

---

## Decisions log

- **Credentials:** full set lives in a separate dealer-only doc; this doc keeps only client Wi-Fi
  and the CH advanced user password as nice-to-have. Missing creds never block ACCEPTED.
- **Zone / output mapping:** confirmed make-or-break (CRITICAL) for audio and video.
- **Alarm zone list:** nice-to-have.
- **Schema gaps:** none to add now; revisit during the beta app build, not here.
