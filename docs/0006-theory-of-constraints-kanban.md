# Apply Theory of Constraints and Kanban to Development Processes

Kanban is a popular "Lean" approach to software development that originated out of the Theory of 
Constraints, which itself was derived from manufacturing plant world. 

In a manufacturing plant it can be easier to identify which parts of the plants are constraints by 
walking around and looking at WIP (work in progress) inventory. The machines with the most WIP 
inventory in front of them are the constrained machines. All other machines have extra capacity 
that should not be used because it drives up inventory blocked in front of the constrained 
machines. By limiting WIP and working on smaller batches, manufacturing plants are able to 
reduce inventory and operational costs while increasing throughput. All of that, of course, 
makes the customers and managers happy.

Kanban also looks to limit WIP, but Kanban does it electronically where "tickets" become the 
inventory. Keeping a few assigned, in-progress tickets per worker and not allowing more work to 
pile up allows managers to better predict the length of time it takes to complete a feature 
request from idea to code deployment. In the software world, the most successful products are 
the agile ones that can adapt to rapidly changing market pressures predictably.

## Sponsors

- Alex Finnarn - DE Front-end Developer - alexander.finnarn@cu.edu

## Status

This ADR is in the proposed status currently. Developers are following the process somewhat, but 
the process is not holistic nor is it complete. Part of this ADR is creating sample process 
documentation stored in the general team development documentation site where more review and 
iterations can take place.

## Prior Art

The proposer of this ADR thought searching for constraints was the best way to improve the 
current development process. A quick internet search for "constraint-based development" led to 
the book *Goal: A Process of Ongoing Improvement* by Eliyahu M. Goldratt. Within that book, the 
Theory of Constraints is laid out in a fun, socratic novel about turning a failing manufacturing 
plant around.

Kanban with a capital "K" originated from David Anderson's 2010 book, *Kanban*, where he takes a 
Theory of Constraints approach and marries it with the kaizen culture of Toyota and the TPS 
system based off of "cards" which translates to "kanban" in Japanese.

Both Theory of Constraints and Kanban are thought of as "pull systems" where work gets pulled 
into the queue and WIP is limited based on work ahead of it. By limiting WIP 
some teammates will have slack time while the constraints are fully in production without a huge 
backlog to worry about. Managers don't need to crack the whip because they're given an accurate 
sense of lead time from requesting a feature to deploying it.

Contrast that method with "push systems" where work is pushed into the system no matter what current 
work is being done or still in progress. By not limiting WIP for the non-constrained resources, 
they inevitably pile up work in front of the constraints causing overhead to deal with the 
growing and outdated backlog of tasks. Managers rush to expedite and no one has any good idea of 
lead time from announcing a feature idea and deploying the code.

Inspirations: 
- Discussion at the end of "Goal: A Process of Ongoing Improvement"
- Kanban Wikipedia - https://en.wikipedia.org/wiki/Kanban
- Kanban Development Wikipedia: https://en.wikipedia.org/wiki/Kanban_(development)
- Kanban book - https://www.amazon.com/Kanban-David-J-Anderson-ebook/dp/B0057H2M70/
- ToC Wikipedia article - https://en.wikipedia.org/wiki/Theory_of_constraints
- Context for Agile - https://www.leadingagile.com/2018/03/the-theory-of-constraints-in-agile/
- ToC book - https://www.amazon.com/Goal-Process-Ongoing-Improvement-ebook/dp/B002LHRM2O/

## Current Context

If attention is not paid to "pulling" work through a system, people inevitably pile up work next 
to constraints. We hypothesize that Central Advancement works in a push system approach and that 
enacting a pull system within Digital Engagement will help to show others how effective pull 
systems can be. 

The benefits of switching to this mindset really start to show up with 
cross-team work, but within-team work should also improve by looking to identify and mitigate 
the effects of constraints on overall team productivity.  

## Decision

We will use a Kanban style of project management limiting WIP and visualizing all work on 
project boards within GitHub. The process will follow documentation in the
[Development Philosophies and Workflows](https://github.com/CUCentralAdvancement/github-docs#development-philosophies-and-workflows)
section in the main set of developer documentation.

## Consequences

It might be challenging to limit WIP since traditional dev team backlogs notoriously grow to be 
hundreds or thousands of outdated issues no one wants to go through but no one wants to close.

We have "Stalebot" which automatically closes issues after so many days of inactivity; however 
it will probably be tricky to get other parts of Central Advancement to adopt such a strategy as 
they habitually plan for work to be done many months ahead of when anyone can actually work on it.

Members of the Digital Engagement team should find it easier to identify when other coworkers 
are overburdened and easier to spot ways that the process can be improved by investigating why 
some issues get stuck in the queue. 
