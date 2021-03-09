# Use C4 Model For Architecture Diagrams

https://c4model.com/

> The C4 model was created as a way to help software development teams describe and communicate software architecture, 
> both during up-front design sessions and when retrospectively documenting an existing codebase. It's a way to create 
> maps of your code, at various levels of detail, in the same way you would use something like Google Maps to zoom in 
> and out of an area you are interested in.

## Status

This idea is in the proposal stage. Previously, diagrams were made ad hoc using various diagraming tools and shapes
to denote applications and the links between them. 

## Context

The current architecture diagrams are not standardized and it is hard to "zoom into" the proper layer and not leave
a bunch of details out. Rather than use zoom functions in tools, it would be a better idea to use a standardized model
detailing the different levels of context depending on the group you need to discuss the architecture with.

## Decision

Use a diagram tool, https://app.diagrams.net/, to create diagrams with C4 notation of current applications and future
state. Export the diagrams in PNG, PDF, etc. formats for distribution to wikis and documentation repositories. 

## Consequences

Team members have to adhere to creating these diagrams and models before doing work and adjusting them as time goes 
on. Also, being new to implementing this style of architectural mapping we will create non-ideal diagrams in the 
beginning.