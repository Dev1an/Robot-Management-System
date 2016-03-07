## Design decisions

### PnP application

- How are we going to visualize the web of trays

### Robot communication

- **Models for state machines:** Make a solid state machine model, that everyone in network will use.
- **Which Zyre implementation:** The current one I use is the python script from Johan. Should I use another one
- **Policy for tracability requirement:** Should we define a policy so that the zyre<->database mediator can communicate whether it is ready to log the events into the database? This can then be used by modules to ensure tracibility.

### Database

- **Structure:** We can have a configuration of

  - *i* databases

  - *j* mediators

  - *k* browser clients

  What's the balance of *i*, *j* and *k* that we will use?


- **Rethink vs mongo**: Rethink and mongo both have their (dis)advantages.
  - Rethink

    (+) Has change feed API's in *Javascript, Ruby, Python and Java*

    (-) Changefeed api is a bit sloppy (no easy way to close a feed when you are done with it, no fine-grained change updates, ...)
  - Mongo

    (+) Fine-grained changefeed API

    (-) Changefeed API only in *Javascript*