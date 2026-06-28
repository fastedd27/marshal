# examples.md

> Worked decisions showing Marshal's logic in action, including an edge case the obvious rules do
> not cover. Sites and names here are fabricated.

## Example 1: RETURN TO TECH (missing support-critical fields)

**Input (excerpt).** Network section: ISP and switch documented, but the remote-access method is
blank. Cameras section: NVR brand "Uniview," 8 cameras, power source "NVR PoE ports," but no NVR IP
or remote-reach detail. OvrC attestation: checked.

**Marshal's read.**
- Front door: OvrC is attested, so tier-1 is fine. But the network has no documented remote-access
  method and the NVR has no reach detail, so tier-2 advanced cannot get into either. Both are
  support-critical and both systems are present.
- Everything else on the site clears.

**Verdict: RETURN TO TECH.**
> To the submitting tech: two items before this can be accepted.
> 1. Network: add the remote-access method (DDNS URL and VPN method/type, e.g. IPSec or
>    UniFi/WireGuard).
> 2. Cameras: add the NVR IP and how support reaches it remotely.
> Everything else is service-ready. Fix these two and resubmit.

## Example 2: the edge case, an empty section that is not actually empty

**Input (excerpt).** Control System section: completely blank, N/A not toggled. But three rooms
list "touch panel: yes," and the Rack Room equipment photo clearly shows a Crestron processor,
labeled "Processor."

**Why this is the hard one.** A naive checker sees a blank Control System section and either
ignores it (blank means nothing is there) or blocks it (blank means incomplete). Both are wrong.
The rest of the doc proves a control system exists; it just was not documented.

**Marshal's read.**
- Presence reconciliation: Control System is blank and not marked N/A, but the Rooms matrix (three
  touch panels) and the equipment photo (a labeled processor) both show a control system is
  present. This resolves to PRESENT-but-undocumented, not ABSENT.
- It also trips the photo-versus-section contradiction check.

**Verdict: RETURN TO TECH.**
> To the submitting tech: the Control System section is empty, but this site clearly has one. The
> rack photo shows a Crestron processor and three rooms list touch panels. Document the control
> system (brand, processor location and IP, Crestron DDNS and outside ports, touch-panel
> locations), or mark the section N/A if it truly does not apply. Resubmit.

## Example 3: ACCEPTED, with a support advisory riding along

**Input (excerpt).** Every present subsystem clears its support-critical fields. OvrC attested,
tier-2 path documented. The Network section records a wireless PtP link feeding the "Guest House."

**Marshal's read.**
- Front door confirmed, all present subsystems complete, no contradictions. The doc clears for
  handoff.
- The PtP link is not a problem to fix, but support should know it is there.

**Verdict: ACCEPTED.**
> Cleared for handoff to support.
> Advisory attached for support: the Guest House is fed by a wireless point-to-point link. If that
> area drops while the rest of the site is fine, suspect the PtP hop first.
