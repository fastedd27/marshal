# Marshal Output: `sample-site-doc-corrected.md`

> What Marshal returned on the corrected sample, where every item from the first-pass punch list
> was resolved. Produced in a cold-test: a blank-slate reviewer given only the Marshal folder and
> this input, with no other context.

## Verdict: ACCEPTED, cleared for handoff

Front door open, every present subsystem clears its support-critical fields, no contradictions. The
corrected doc passes cleanly, with no manufactured nitpicks. One support advisory rides along
(below). Environmental caveat: this is a text rendering, so the photo cross-check could not be
physically run; nothing in the text contradicts acceptance.

## Order of operations

**0. Front door: PASS.** OvrC attested. Tier-2 documented: VPN method (UniFi/WireGuard) plus
Crestron Home reach (Crestron DDNS, RMS enabled, App/HTTPS/CIPS ports).

**1. Presence.** Present: Network, Control System, Zone Audio, Distributed Video, Lighting, Cameras,
Rooms. N/A and trusted: Shades, Alarm, Access Control. No ambiguity.

**2. Support-critical fields.** Every present subsystem clears:
- Network: ISP + backup, router + switch models, IP scheme, DDNS + VPN, Wi-Fi + SSID.
- Control System: brand, processor location and reach, Crestron DDNS, App/HTTPS/CIPS ports.
- Zone Audio: amp types + Crestron NAX matrix, AVR, zone-to-room mapping (Kitchen / Library / Pool).
- Distributed Video: AVProEdge matrix, output-to-room mapping.
- Lighting: brand, type, integrated yes/no, scope boundary.
- Cameras: NVR brand + model + reach, camera brand, named PoE switch, count, integration.
- Rooms: all in-scope rooms complete.

**3. Contradictions: none.** The Pool zone is now listed in Zone Audio outputs, matching the Pool
Projector room (the earlier mismatch is resolved). Excluded checks (camera count vs channels, PoE
budget) correctly not run.

**4. Advisory (rides along).** The audio matrix is Crestron NAX, a networked-audio platform, so
multicast is in play. Heads-up for support so they know the traffic profile before chasing an
intermittent stream.

**5. Decision: ACCEPTED.** No punch list. Not an agreeable accept: the doc has no support-critical
gap, no presence ambiguity, and no contradiction in anything captured.

## Photo check (deferred)

Text rendering, so the equipment photos were not readable. On the real PDF, Marshal would also read
the marked-up location photos to confirm no installed-but-undocumented gear before final clearance.
Nothing in the text contradicts acceptance.
