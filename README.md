Node

An append-only directed acyclic graph that holds agent state — and the public record of when it was first set down.

Author and copyright holder: Shane Killeen (Dao_Tribe) — Cape Town. Copyright © 2026 Shane Killeen (Dao_Tribe). Licensed under the Apache License, Version 2.0 — see LICENSE and NOTICE. Attribution to the original author is required under Section 4 of the Apache License.

This repository exists for two reasons, in this order:

    Provenance. To fix, in public and with timestamps nobody controls, when this idea was written down and by whom.
    The container. A DAG in which each node is an agent's record: append-only, ancestry always traceable, nothing able to rewrite its own history. Usable by anyone, for any agent system.

What this is not

This is not a physics paper and makes no claim about primes, the Riemann hypothesis, or anything else. If someone finds further structure in the graph, that is theirs to find. The provenance below already says where the graph came from.
Provenance chain
Record 	Where it lives 	Date 	What it holds
node zero 	WhatsApp note, own timestamp 	⟨DATE OF NODE ZERO⟩ 	a rough, short equation
node one 	given to an AI, which hashed it 	⟨DATE OF NODE ONE⟩ 	a second node, hashed
node two → 	this repository, Apache-2.0 	commit dates in git log 	the graph, sealed and open records

Node zero and node one prove when. This repository proves what, from node two onward.
Sealed records

Some content stays private for now. It is committed as a SHA-256 hash only: the date is locked, the content is not shown. When a record is revealed later, anyone can check that it matches.

To seal a record (from the repository folder):

Copy
sha256sum node-two.md > node-two.sha256
git add node-two.sha256
git commit -m "seal node two"
git push

To verify a reveal:

Copy
sha256sum node-two.md
cat node-two.sha256

The two hashes must be identical, character for character.

To read the timeline:

Copy
git log --date=iso --pretty="%ad  %h  %s"

Rules of the graph

    Append only. A node is written once. Corrections are new nodes that name what they correct.
    Every node names its parents. Ancestry is always traceable back to node zero.
    No path returns to its origin. This holds inside one graph and across connected graphs: a connector between two graphs is valid only if no chain of edges can loop back. An edge that would close a loop is rejected.
    A record is either open or sealed. Sealed means hash committed, content withheld. Nothing else is permitted.
    State survives restart. The graph is the memory. An agent that reads its own node and its ancestors is fully restored.

Contributing

Contributions are welcome under the Apache License 2.0. Open an issue or a pull request. Please keep the NOTICE file intact in any copy, fork or derivative — that is what carries attribution forward.
Author

Shane Killeen (Dao_Tribe) — Cape Town.
License

Apache-2.0. See LICENSE and NOTICE.
