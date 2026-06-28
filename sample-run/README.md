# Sample Run

Two worked runs on the **same fabricated site**, showing Marshal in both directions. The client
identity is invented; the technical configuration is realistic (drawn from a real install,
scrubbed).

| Input | Marshal's verdict |
|-------|-------------------|
| [`sample-site-doc.md`](sample-site-doc.md) : a half-finished doc (front door undocumented, blanks across several subsystems, one room/matrix mismatch) | [`sample-output.md`](sample-output.md) : **RETURN TO TECH**, with a specific punch list addressed to the submitting tech |
| [`sample-site-doc-corrected.md`](sample-site-doc-corrected.md) : the same site with every punch-list item fixed | [`sample-output-corrected.md`](sample-output-corrected.md) : **ACCEPTED**, with a multicast support advisory riding along |

Both verdicts were produced by a **blank-slate reviewer given only this folder and the input doc**,
with no other context, so the folder alone drives the call. The gate works both ways: feed it the
gapped doc and it bounces a precise punch list; feed it the corrected one and it accepts cleanly,
without inventing nits.

## Want to push it?

Drop this folder into a Claude project (or paste its files in as context), then hand Marshal one of
the samples, or your own site doc, and ask for a verdict. Edit a sample to add or remove a gap and
watch the call change. It was stress-tested this way during the build: a corrected doc has to accept
cleanly, and a different site has to still get a sensible call. Try to break it.
