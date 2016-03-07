# Design decisions

## System structure

The main application is generic and will visualize all the modules (and their events) in a common way.

Extensions can be written to provide better (more specific) visualizations adapted a certain project/robot.

## Robot communication

### Models for state machine
All modules use should use what we call the (hierarchical) life cycle state machine (aka LCSM)![hierarchical lifecycle state machine](imports/LifeCycleStateMachine-hierarchical.png)

Once in the “active” state, the module should be discoverable on the network (setting up the network should be done in the “configuring resources” state)

### Which Zyre implementation
UNCLEAR: The current one I use is the python script from Johan. Should I use another one
### Policy for tracability requirement
UNCLEAR: Should we define a policy so that the zyre<->database mediator can communicate whether it is ready to log the events into the database? This can then be used by modules to ensure tracibility.

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

## PnP Extension
### How are we going to visualize the web of trays
- Modules are rectangles next to each other and you could have (based on a **config** file) an initial idea of which modules to expect and where they would be **positioned**.
	- Nico has already defined a [json-schema for the **configuration** of a module](https://gitlab.mech.kuleuven.be/rob-picknpack/pnp-line/blob/633dda2ae2d00875301e3bcc9436d2001515ec99/json_models/configuration_schema.json). But it does not include the **positioning** of the module. So a more specific schema should be made (UNCLEAR).
- Module names above these rectangles, together with their state and a small circle which colours green if the module is ready, orange if it’s busy and red if there is an **issue**
	- Currently I only have [these models](imports/rFSM) of the LCSM.
	- How are state transitions communicated over the Zyre network?
	- UNCLEAR: Is there already somthing defined in the communication protocol to indicate issues?
- The line controller above the modules, showing its stop light protocol
	- UNCLEAR: Where is the stoplight protocol defined?
- The actual web of trays:
	- This is the most challenging thing, I guess. Not just because of the
		geometric complexity, but also because the web grows over time; or in the
		context of what Johan suggests: the selection of what to display, changes
		over time.
- command buttons, to start/stop activities on modules.
	- UNCLEAR: How are the activities defined?

## Sherpa Extension

UNCLEAR