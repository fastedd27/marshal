# Site Documentation (V2.0): SAMPLE (photo-catch demo)

> A focused demo of the one thing nobody else does: Marshal reading the marked-up equipment photo
> and catching a system the form denied. This doc is otherwise service-ready. The Cameras section
> is marked N/A, but the attached Rack Room photo (`photo-catch-rack-photo.jpg`) clearly shows a
> labeled NVR. Run Marshal on this doc WITH the photo attached. Identity invented; configuration
> realistic, scrubbed.

**Project:** Hadley, Dana, 88 Marsh Point Ct (fabricated)
**Checklist:** Site Documentation V2.0
**Tasks completed:** 56 / 58
**Submitted by:** field tech
**Attached photo:** `photo-catch-rack-photo.jpg` (Rack Room, marked up)

---

## Remote Diagnostic Tools Check
- Are all OvrC devices added, named, and ports labeled? Yes
- Is there a PC in the rack for remote access? No
- Remote-access platform: N/A

## Equipment Locations
Called out, each with a marked-up photo: **Rack Room** (see `photo-catch-rack-photo.jpg`), Living Room, Man Cave.

## Network Details
- ISP: Spectrum (Cable). Backup provider: No.
- Wired: Router UniFi UDM-Pro; primary switch UniFi USW-Pro-24-PoE; AV distribution switch N/A; IP range 172.27.0.x (gateway 172.27.0.1).
- DDNS url: sample-88mp.ddns.example.com
- VPN method for Advanced Support: UniFi (WireGuard)
- Wireless: Wi-Fi UniFi; client SSID: Hadley-Home; Wi-Fi password: (in dealer credentials doc); PtP links: No.

## Control System
- Brand: Crestron Home. Main processor location: Rack Room. Touch panel locations: N/A.
- Crestron DDNS address: sample-88mp-cres.ddns.example.com · myCrestron RMS enabled: Yes · App port: 41796 · HTTPS port: 443 · CIPS port: 41794 · UI device password: (in dealer credentials doc) · Advanced user password: (in dealer credentials doc)

## Zone Audio
- Amp types: Matrix audio. Matrix: Crestron SWAMP (with expander). AVR: Integra.
- Inputs: 1 Sonos Port (House Music 1), 2 Sonos Port (House Music 2), 3 Living Room Blu-ray.
- Zones (outputs): 1 Kitchen, 2 Living Room, 3 Man Cave.

## Distributed Video
- Matrix: AVProEdge.
- Inputs: Living Room Blu-ray, House Roku.
- Outputs: 1 Man Cave TV, 2 Living Room TV.

## Lighting Control
- Brand: Crestron. System type: Wireless. Form factor: Decora. Integrated with control system: Yes. Lighting control covers only the landscape transformers.

## Shades
- N/A (no shades on this site).

## Cameras
- N/A (no camera system on this site).

## Alarm
- N/A (no alarm system on this site).

## Access Control
- N/A (no access-control system on this site).

## Rooms (in AV scope)

| Room | Video | Audio | Touch panel | Thermostat | Lighting | Shades |
|------|-------|-------|-------------|------------|----------|--------|
| Living Room | Distributed video (Roku) | AVR (Sonos) | No | No | No | No |
| Man Cave | Distributed video (Roku) | Zone audio (Sonos) | No | No | No | No |
| Kitchen | NA | Zone audio (Sonos) | No | No | No | No |
