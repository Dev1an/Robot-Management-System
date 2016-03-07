# Design decisions

## Robot communication

- **Models for state machines:** Make a solid state machine model, that everyone in network will use.
- **Which Zyre implementation:** The current one I use is the python script from Johan. Should I use another one
- **Policy for tracability requirement:** Should we define a policy so that the zyre<->database mediator can communicate whether it is ready to log the events into the database? This can then be used by modules to ensure tracibility.

## Database

- **Structure:** We can have a configuration of
  - *i* databases
  - *j* mediators
  - *k* browser clients
    What's the balance of *i*, *j* and *k* that we will use?


- **Rethink vs mongo**: Rethink and mongo both have their (dis)advantages.
  - Rethink
    - (advantage) Has change feed API's in *Javascript, Ruby, Python and Java*
    - (disadvantage) Changefeed api is a bit sloppy (no easy way to close a feed when you are done with it, no fine-grained change updates, ...)
  - Mongo
    - (advantage) Fine-grained changefeed API
    - (disadvantage) Changefeed API only in *Javascript*

## PnP application
### How are we going to visualize the web of trays
- modules are rectangles next to each other and you could have (based on a config file) an initial idea of which modules to expect and where they would be positioned
- module names above these rectangles, together with their state and a small circle which colours green if the module is ready, orange if it’s busy and red if there is an **issue**
  - UNCLEAR: Is there already somthing defined in the communication protocol to indicate issues? I suppose this shoud part of the hierarchical state machine model?
- the line controller above the modules, showing its stop light protocol
  - UNCLEAR: Where is the stoplightprotocol defined?
- the actual web of trays:
  - This is the most challenging thing, I guess. Not just because of the
    geometric complexity, but also because the web grows over time; or in the
    context of what Johan suggests: the selection of what to display changes
    over time.
- "command buttons", to start/stop activities on modules.
  - UNCLEAR: How are the activities defined?