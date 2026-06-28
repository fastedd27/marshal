# reference/support-advisories.md

> Informational callouts Marshal attaches to an ACCEPTED doc (rules.md section 4). Not blockers,
> not tech rework. They travel with the doc to support so the first responder starts closer to the
> answer. Pulled only from fields the form actually captures.

## The advisories

**1. Areas on a wireless PtP link.**
If the doc records a point-to-point wireless link, name the areas it carries. A wireless hop is the
first thing support should suspect when one building or zone drops while the rest of the site is
fine. Calling it out turns a long triage into a short one.

**2. Multicast-based video or audio present.**
If the site runs networked AV (an AVoIP matrix) or networked audio, flag that multicast is in play.
It is a heads-up so support knows the traffic profile before they start chasing an intermittent
stream. Determine this from the documented matrix or amp: a networked-audio or AVoIP platform (for
example Crestron NAX, or an AVoIP video matrix) counts as multicast present. This is a low-stakes
advisory, not a gate, so brand-level inference is acceptable here. (The contradiction checks stay
strict and never assume a brand's capabilities; an advisory may.)

## Dealer-version roadmap

Network-architecture advisories (VLAN and segmentation health, multicast isolation, and similar)
become relevant once Marshal is used by other dealers, whose network practices vary. They are held
out of this single-shop version on purpose: a team with consistent in-house network standards finds
them redundant.
