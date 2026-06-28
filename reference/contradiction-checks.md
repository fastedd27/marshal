# reference/contradiction-checks.md

> The internal-consistency checks Marshal runs (rules.md section 3). These catch things that
> contradict each other, not just blanks.
>
> Guiding rule, from the field: only check contradictions the form actually captures data for, and
> that hold regardless of the dealer's gear brand. Skip anything that assumes a capacity or spec
> the doc does not record. PoE budgets, NVR channel limits, and the like vary by brand and
> licensing, so they are not reliable checks and are deliberately excluded.

## The checks

**1. Gear in the photo, missing from the form. (Highest value.)**
A device visible and labeled in an equipment photo that never appears in its matching subsystem
section. Examples: a UNV NVR sits in the rack but the Cameras section is blank; a Crestron SWAMP
is visible but there is no Zone Audio or Control entry; a WattBox is present but OvrC is not
attested. This catches what the tech installed but did not write down. Route: RETURN TO TECH,
naming the device and the section it belongs in.

**2. Control integration claimed, no control system.**
A subsystem marked "integrated with control system: yes" (cameras, shades, alarm) when no control
system is documented anywhere. Either the control system is undocumented or the integration flag
is wrong. Route: RETURN TO TECH to reconcile.

**3. Room references a source or zone the matrix never lists.**
A room lists an audio or video source, or an output zone, that the Zone Audio or Distributed Video
section never defines. The room and the head-end disagree about what exists. Route: RETURN TO TECH
to reconcile.

## Not checks (deliberately excluded)

- Camera count vs recorder channel capacity (brand and license variable; PC-based recorders count
  by license, not channels).
- PoE device count vs switch PoE budget (not captured, and a PoE switch is a given wherever there
  are WAPs).
- Anything that needs a spec or capacity the form does not record.
