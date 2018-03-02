# RFC: Hacks in Play Services

## Current
Everyone does it - some more than others - but it is a fact of life for modern developers. This will typically be an isolated “feature” to support a bounded use case. Developers often resort to one off “hacks” for a variety of reasons:

"Get something out" quickly under time pressure without taking time to properly design and implement a feature (typically a client-mandated launch with a hard date) - ie. prioritizing urgency over long term and enduring
Unideal dependency on another service owned by another team/person
Laziness (or there may be other, more interesting/important tasks to do) - not really a reason, but it happens

#### Previous process

- Submit PR with “Hack”
- Once reviewed and merged, add a ticket in Clubhouse “Hacks” epic ([https://app.clubhouse.io/flow/epic/2194/hack-things-we-must-fix-later](https://app.clubhouse.io/flow/epic/2194/hack-things-we-must-fix-later))

#### Issues with this process:

- Difficult to actually find the hacks in the code
- Difficult to verify that a hack was actually removed
- Hacks get “paid down” sometimes (e.g. “December Projects”), but difficult to track and make visible that these actually happened

## Proposal

#### Create a single `Hacks.scala` in each application

- Contains at least one of: `object Hacks` or injectible `class Hacks`
- Contains all hacks for a given service
- Easily verifiable documentation and location of existing hacks for a service
- Addition to Hacks should ideally still be made available for review via PR to other members of the team to make them aware (and make sure unintended consequences are accounted for)
- (Older) Example: [https://github.com/flowcommerce/label/pull/445](https://github.com/flowcommerce/label/pull/445)
- Pros:
	- Ensure all “hacks” per service are documented in a single, easy-to-find location
	- Self-documenting, unambiguous, easily searchable
- Cons:
	- Does not solve for “when will we fix these hacks?”
	- If class gets too big, nobody may actually care
	- A “correctly implemented feature” for someone may be a “hack” for someone else

#### Hack reviews

- Propose to periodically do this at least once a quarter
- Build script to programmatically find all of our hacks via the class convention
- Goal is to remove contents of Hacks class
- December projects can involve getting rid of all hacks (just like make sure all pending.sql scripts are applied)
- Just like tech debt, we should see this as extra “interest” we accrue until we need to pay down, so periodically doing this would:
	- Actually fix potential issues
	- Make it easier to add new things after
	- Ensure high software quality
	- We don’t have to do it farther down the future when making an important feature change will be bogged down by a hack that’s already in place
