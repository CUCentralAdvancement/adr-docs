# ADR Docs

A repository of Architectural Decision Records (ADR) for CU Central Advancement.

ADRs are great tools for development teams to catalog past decisions and draw upon that catalog for future work. Far too often, 
a decision is made in isolation and while the solution exists new developers often ask the "why?" of the codebase and not the "what?" and "how?"
of the codebase they can already see.

For example, if you are working on migrating a legacy application to a new tech stack, you might go through several iterations of
design hopefully making sure to document the final version. However, if you delete the failed iterations' repositories, issues, and comments, 
you lose a lot of the "why?" context that got you to the final solution, and you can waste a lot of time being a new employee doomed to repeat 
past failed ideas.

For these reasons, CU Central Advancement will document all future significant architectural decisions in the ADR format.

## What Decisions Necessitate An ADR?

The first question you may ask when learning about ADRs is: "when should I write one?" Is every change worthy? Of course, if every change was
recorded as an ADR it would make their use case meaningless and divulge into an unmaintainable mess. However, there is no hard and fast rule to 
answer "when should I write one?", and ADRs exist on a continuum of change notifications.

- Git commits - These are the most basic change notices. If atomic commits are used, developers can follow the trajectory of an idea placed into
code. Using `git blame` devs can even see the history for each line of code and who changed it.
- Code comments - Used with a `We did this because... @see https://issue.url/path` syntax, developers can comment on blocks of code as to why the 
change was made, and if appropriate link to an issue thread about the change.
- Issue/PR threads - On GitHub, each code change is accompanied by an issue thread with comments and original hypothesis of why the code needs to
be changed. The PR threads involve specific discussion on lines of code and alternatives to proposed changes.
- Project documentation - Each part of the codebase for each project should have documentation covering all of the concerns and be informed by using
a standardized `README.md` template. That readme should link to more general documentation where appropriate.
- Organizational code-related documentation - These documents outline overall philosophies on areas of development and architecture concerns. 
Individual projects will link to these when describing common dev topics as well as using templates to generate project scaffolds amongst the
chosen tech stacks.
- Architectural decision records - Finally, at the top of all change notices and documentation sits the ADRs. They mainly inform organization-wide
documentation and rarely will be related to individual projects. 

Even with a good overview of that continuum it can be hard to identify when an ADR makes sense to write up. Looking for guidance, [the following
quotes](https://en.wikipedia.org/wiki/Architecturally_significant_requirements) are helpful when making a decision.

> Architecturally significant requirements are those requirements that have a measurable effect on a computer system’s architecture. This can comprise both software and hardware requirements. They are a subset of requirements, the subset that affects the architecture of a system in measurably identifiable ways...A requirement that has **wide effect, targets trade-off points, is strict (constraining, limiting, non-negotiable), assumption breaking, or difficult to achieve** is likely to be architecturally significant.

## ADR Proposal Process

Proposals from any Central Advancement employee are welcome. As developers, we might write some CLI tools to generate ADR templates and the like;
however, for non-technical people, it is easier to start out with just GitHub and it's content editing tools.

1. File an issue using the "Decision Record" template. It has prompts you can fill out. If you don't know the full answers to some of the questions,
that's okay. Fill in as much as you can.
1. Look in the `/docs` directory for the last ADR. They begin with a four digit code used to order ADRs sequentially as they are accepted. It might be
the case that you pick a prefix, e.g. `0007-`, to a file and someone else commits an ADR before you, but that is easy enough to fix and will be shown
via the GitHub UI as a merge conflict.
1. Once in `/docs` click "Add file" and then "Create new file" from the dropdown. Name the file `[prefix]-[title]`, e.g. `0002-web-styling-tailwind-css.md`.
1. Copy `/templates/adr-template.md` into your new file.
1. Write up the ADR with your notes.
1. Choose "Create a new branch for this commit and start a pull request." from the bottom "Commit new file" fieldset naming the branch after the GitHub
issue number, e.g. `/adr/7` for issue #7.
1. Add some reviewers to the newly created pull request.

## Background

The idea for creating this repo came from the 2021 BYU UAPI conference with particular advice from the great Brent Moore.

This is obviously a work in progress, but here are some links for background orientation:

- ADR main GitHub repo and readme with links - https://adr.github.io/
- ...
