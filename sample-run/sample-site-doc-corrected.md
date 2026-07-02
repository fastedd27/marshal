# Site Documentation (V2.0): SAMPLE (corrected)

> The same fabricated site as `sample-site-doc.md`, with every item from Marshal's first-pass
> punch list resolved. Used to test whether Marshal accepts a corrected doc cleanly or invents new
> issues. Identity invented; configuration realistic.

**Project:** Bennett, Marcus, 5120 Oak Hollow Dr (fabricated)
**Checklist:** Site Documentation V2.0
**Tasks completed:** 58 / 58
**Submitted by:** field tech

---

## Remote Diagnostic Tools Check
- Are all OvrC devices added, named, and ports labeled? Yes
- Is there a PC in the rack for remote access? No
- Remote-access platform: N/A

## Equipment Locations
Called out, each with a marked-up photo: Rack Room, Living Room, Man Cave, Laundry Closet.

## Network Details
- ISP: Spectrum (Cable). Backup provider: No.
- Wired: Router UniFi UDM-Pro; primary switch UniFi USW-Pro-24-PoE; AV distribution switch N/A; IP range 172.27.0.x (gateway 172.27.0.1).
- DDNS url: sample-5120.ddns.example.com
- VPN method for Advanced Support: UniFi (WireGuard)
- Wireless: Wi-Fi UniFi; client SSID: Bennett-Home; Wi-Fi password: (in dealer credentials doc); IoT-Net password: (in dealer credentials doc); PtP links: No.

## Control System
- Brand: Crestron Home. Main processor location: Rack Closet. Touch panel locations: N/A.
- Crestron DDNS address: sample-5120-cres.ddns.example.com · myCrestron RMS enabled: Yes · App port: 41796 · HTTPS port: 443 · CIPS port: 41794 · UI device password: (in dealer credentials doc) · Advanced user password: (in dealer credentials doc)

## Zone Audio
- Amp types: Matrix amp + standalone landscape amps. Matrix: Crestron NAX. Landscape amp: Origin Acoustics. AVR: Integra.
- Inputs: 1 Sonos Port (House Music), 2 Living Room Blu-ray, 3 Her Roku, 4 His Roku.
- Zones (outputs): 1 Kitchen, 2 Library, 3 Pool.

## Distributed Video
- Matrix: AVProEdge.
- Inputs: Her Roku, His Roku, Living Room Blu-ray.
- Outputs: 1 Man Cave TV, 2 Living Room TV, 3 Pool Projector (video) / Living Room Blu-ray (audio).

## Lighting Control
- Brand: Crestron. System type: Wireless. Form factor: Decora. Integrated with control system: Yes. Lighting control covers only the landscape transformers.

## Shades
- N/A (no shades on this site).

## Cameras
- NVR brand + model: Uniview NVR301-08X. Reach: 172.27.0.20 (via VPN). Camera brands: Uniview. Door/gate station: UniFi.
- Power source: PoE network switch. Primary camera PoE switch name: SW02-24POE. Integrated with control: No.
- Total cameras on recorder: 6

## Alarm
- N/A (no alarm system on this site).

## Access Control
- N/A (no access-control system on this site).

## Rooms (in AV scope)

| Room | Video | Audio | Touch panel | Thermostat | Lighting | Shades |
|------|-------|-------|-------------|------------|----------|--------|
| Living Room | Local (Roku) | AVR (Sonos) | No | No | No | No |
| Man Cave | Local + HDMI balun (Roku) | AVR (Sonos) | No | No | No | No |
| Office | Local (Roku) | Powered soundbar (Sonos) | No | No | No | No |
| Fitness | Local (Roku) | Powered soundbar (Sonos) | No | No | No | No |
| Pool Projector | Distributed video (Roku) | Zone audio (Sonos) | No | No | No | No |
| Kitchen | NA | Zone audio (Sonos) | No | No | No | No |
| Library | NA | Zone audio (Sonos) | No | No | No | No |
