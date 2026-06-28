# The Story Behind Marshal

> The Wildcard brief asked us to be our own client and solve a real problem. This is the real one,
> and where it is going. The people and companies involved are kept anonymous; everything else is
> exactly how it happened.

I run technical operations for a residential smart-home integration company. Most of what I build
is for us. I had already built an AI tool for my field techs' daily site notes: it standardizes them, makes
sure they are complete and detailed enough to be useful, and turns them into structured files that
feed a company knowledge base we can query later when troubleshooting.

Site documentation is the next problem down the list, and it is not only mine. I was in a working
conversation with a peer who runs a support-services platform used across a network of integration
dealers. We were circling the same problem from two sides: how do you get every dealer to hand over
site documentation that support can actually use? They want it standardized across their dealer
base. I want my own techs to stop leaving me holding the bag on half-finished docs. Same problem,
two doors into the same room.

So Marshal is not a demo I built for a competition. It is the working logic for something I am
taking to a real industry partner as a beta. The competition was the forcing function: it made me
scope it tightly, write the decision logic down, and prove it cold, instead of leaving it as a
someday idea.

That is also why the examples in this repo are what they are. The sample site docs are real
installs from my own work, scrubbed: invented client names and addresses, fake remote-access
details and credentials, but real gear, real zones, and real gaps. I ran the finished folder
against them as a blank-slate reviewer and stress-tested it both directions: a gapped doc has to
bounce, and a corrected doc has to pass without the reviewer inventing new problems. The
before-and-after pair in `examples/` is that test, left in so anyone can re-run it.

I am not chasing a prize. I am shipping a tool I need, that a peer in my industry needs, scoped and
proven on a deadline. The competition gave me the deadline. The prize, if it comes, is a bonus.
