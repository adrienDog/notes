# Eric Evans: "What I've learned about DDD since the book"
[Source](https://youtu.be/lE6Hxz4yomA)

## What is essential
### Creative collaboration of domain experts and software experts
### Exploration and experimentation
Don't stop at the first model you come up with --> constant evolution.
### Emergin models shaping and re-shaping the Ubiquitous Language
### Explicit Context Bounderies
Should be amongst the first chapters!
### Focus on the core domain
Explain it in business terms --> If have this we'll be able to ... (e.g. "Enter a new Market", et...)

## Domain events
### Allow for clearer, more expressive models

### Architectural options
- Representing the states of entities
- Decoupling subsystems with event streams
Example: Core transactional system that takes care of addressing the business problem is not tightly coupled with the reporting system. Use Context Map to show the different contexts --> does not mean we need to use different models, but we could.
- Enabling high performance systems (Greg Young)

## Aggregates
Not emphasized enough.
### Consistency bounderies
- Transactions
- Distribution
- Concurrency
If stuff happens all over the place for the same conceptual whole, it is impossible to understand, hence to change.
--> Always try to gather things in a conceptual whole, keep pulling back to the model: 
```
- "We've got this transactional problem."
- "Why? What is the rule that we discovered we need to enforce? And how can we incorporate it in our conceptual model? What is it about that that it is so associated with this? Why do we need them to be so together?"
``` 
These questions can also lead to discovering we dont need an aggregate for this concept. Maybe it is just a monster aggregate that should be separate things.
### An aggregate is a conceptual whole
- Properties
- Invariants

## Strategic Design
- Context Mapping
- Distillation of the Core Domain
- Large-scale structure

## Set the stage for DDD project
### Don't spread modelling too thin
Where modelling comes really useful is not in the big known happy flow, it is in the details, the specific rules and intricacies.
### Focus on the core domain
Where there is a need for extreme clarity.
Comparison with APple product:"What do people want with an mp3 player?" And those parts are crystal clear
### Clean bounded context
"Clean" because it is clear what every context is doing, their responsibility. There is no chaos.
### Iterative process
Get a chance to experiment and make the model evolve along with learnings that are put back into it.
### Access to domain experts

## Context Mapping
### Definitions
#### Context
A setting in which a word or statement appears that determines its meaning.

#### Bounded Context
A description of the conditions under which a particular model applies.

### Patterns
#### Partners
Two teams that are:
- Mutually dependent:
Not on the technical sense, but on the sense "Can I deliver my project succesfully if they don' t?" 
- Cooperative.

#### Big Ball of Mud
[Original concept](http://www.laputan.org/mud)
Concept introduced by the realisation that there is very little written about the most popular architectural pattern, which is when people just do stuff all over the place, "dictated more by expediency than design".
"'Let's just put it there for now and not worry about it'. It builds up and it builds up and yet functions"

**Dont fix it** We draw a Context Map and put it where it belongs: Define the boundery with some firm assumptions.

## DDD helps you make better SOA
- The service interface must be defined in some context
- Internals also, but often not the same one (it is actually thevalue of the service)
- The Service interface may define a context boundery
