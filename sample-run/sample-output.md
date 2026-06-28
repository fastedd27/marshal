# Marshal Output: `sample-site-doc.md`

> What Marshal returned when run on the sample. Produced in a cold-test: a blank-slate reviewer
> given only the Marshal folder and this input doc, with no other context.

## Verdict: RETURN TO TECH

The doc is not service-ready. The front door is not open (OvrC unattested, and the tier-2 remote
path is undocumented on a site that has a Crestron Home control system), several present subsystems
are missing support-critical fields, and one room contradicts the audio matrix. None of it needs a
call above the tech's authority, so this is RETURN TO TECH, not ESCALATE. The header counter
(27 / 58 tasks) is an early yellow flag, not the basis for the call.

## Order of operations

**0. Front door: FAILS (blocks acceptance on its own)**
- Tier 1 (OvrC): the "all OvrC devices added, named, ports labeled" attestation is blank.
- Tier 2 (advanced): a Crestron Home control system is present, but the VPN method, Crestron DDNS,
  and App / HTTPS / CIPS ports are all blank. Advanced has no documented way in.

**1. Presence**
- Present: Equipment Locations, Network, Control System, Zone Audio, Distributed Video, Lighting,
  Cameras, Rooms.
- Shades, Alarm, Access Control: blank with N/A not toggled, but no corroborating evidence anywhere
  (rooms show no shades; no alarm or access gear, no integration claims). Resolved absent, not
  blocking. The UniFi "door/gate station" is filed under Cameras (a video doorbell), not Access
  Control, so it is not evidence of an access-control system.

**2. Support-critical gaps (the blockers)**
- Network: remote-access method (DDNS + VPN) blank; client SSID blank.
- Control System: processor IP / Crestron Home reach blank; Crestron DDNS blank; App/HTTPS/CIPS
  ports blank.
- Lighting: "integrated with control system?" not stated.
- Cameras: NVR brand+model and reach are "Other" with no note; camera brand "Other"; specific PoE
  switch blank; total camera count blank.

**3. Contradiction**
- The Pool Projector room lists its audio as "Zone audio," but the Zone Audio outputs list only
  Kitchen and Library. The room and the matrix disagree.

**4. Advisory (rides along once accepted)**
- Crestron NAX is networked audio, so multicast is in play. Heads-up for support once the doc is
  fixed and accepted.

## Punch list to the submitting tech

Front door (do first):
1. OvrC: confirm devices added / named / ports labeled and check the attestation.
2. Advanced path: document the VPN method/type.

Network:
3. Add the remote-access method (DDNS URL + VPN method, e.g. IPSec or UniFi/WireGuard).
4. Add the client SSID.

Control System:
5. Add the processor IP / Crestron Home reach.
6. Add the Crestron DDNS URL.
7. Add the App, HTTPS, and CIPS outside ports.

Lighting:
8. State whether it is integrated with the control system (yes/no).

Cameras:
9. Identify the NVR brand + model and how support reaches it.
10. Identify the camera brand(s).
11. Name the specific PoE switch powering the cameras.
12. Add the total camera count on the recorder.

Zone Audio:
13. Pool Projector is marked "Zone audio," but only Kitchen and Library are listed as zones. Add
    the Pool zone or correct the room entry.

Tidy-up (not blocking): toggle N/A on Shades, Alarm, and Access Control if they truly do not apply,
so the next reader is not left inferring.

## Photo check (deferred)

This input was a text rendering, so the four marked-up equipment photos were not readable. With the
photos, Marshal would also run its highest-value check: gear visible in a rack or closet shot but
missing from its section. Here that would most likely identify the NVR and cameras the form left as
"Other," and confirm the camera PoE switch. The verdict does not depend on it; the photos would
only add catches.
