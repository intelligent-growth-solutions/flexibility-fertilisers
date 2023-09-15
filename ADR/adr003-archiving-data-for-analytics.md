# Context
Part of Road Warrior's business model is to gather a rich set of analytical data about users and their trips. 

We considered a frequent (e.g. nightly) copy of the data available in persistent storage to an archive and using events to communicated changes to  <<< what about travel preferences .. are those events?>>>

# Decision
We haven chosen to use event based communication. 

In a Mircoservice architecture ownership of the data lies with the service. Copying the database seems an infringement on that ownership, as well as tying the analytical storage to the data representation in operational storage without further processing.

Instead with event based communication changes to entities are communicated which can be selectively subscribed to by the analytical system and stored in whatever way is suitable.

# Consequences
### Pros
- Data is available more timely which could be useful during times of travel disruptions.
- Avoids polling of the relevant services and increasing their load

### Cons
- Events can be dropped or not delivered - given the events are not relevant for operations, missing the occasional event is acceptable. Mitigations like dead-lettering can be put in place.