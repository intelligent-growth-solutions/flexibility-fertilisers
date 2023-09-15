# Road Warrior by Flexibility Fertilizers

## Requirements
The architecture outlined below is based on the business case, requirements and user stories described [here](requirements/requirements-user-stories.md).

## System Overview

The below gives a high level view of the various systems and personas involved in interacting with Road Warrior
![image](https://github.com/intelligent-growth-solutions/flexibility-fertilisers/assets/2922498/45a69004-776c-4852-965a-abd711428279)

## Architectural Characteristics

Following the requirements and additional context, we assessed different architectural characteristics that are of main concern to the Road Warrior architecture.

| Characteristic |  Notes |
|--------|----|
| Availability | The system has strict downtime requirements of a maximum of 5 minutes a month. This is especially important for parts of the system that handle adding or updating travel details. |
| Reliability | The system must reliably accept travel updates from external travel agents and notify the user. Missing updates could impact the user's travel experience and have negative effects on user retention. |
| Elasticity  | Travel suffers from disruption in which case the system becomes even more important to its users wanting to keep on top of travel updates. In these instances, a surge in demand is expected and the system needs to be able to handle this gracefully and without impact to performance.
| Extensibility | The system integrates with various 3rd party travel and booking systems. Evolving with existing interfaces and adding new ones will be crucial to providing users the best possible set of details about their trips.  |

The following are characteristics that where considered relevant to the application but can be addressed through design and common practice.

| Characteristic |  Notes |
|--------|----|
| Installability | The system is accessible through a mobile app and website. To reach as many users as possible the app should be easy to install. This is well supported through different Application stores already.  |
| Privacy  | The system handles peoples' travel information which is personal and sensitive data. Identifiable data must therefore be kept private while an anonymized version must be accessible for data analytics. |
| Archivibility | The business model includes income to be derived from analytics run on user data. To make this successful, data needs to be retained and available to use for report creation. |

## Architecture Style


## Workflows

To identify the main components of the Road Warrior system, we looked at some of the workflows it needs to support.

![Workflowsv2](https://github.com/intelligent-growth-solutions/flexibility-fertilisers/assets/104081505/bc57a4cf-f925-473d-a336-7df2581d0551)

From the workflows we identified the following systems that we wanted to explore further. We may discover the need for more as we investigate how the systems fit together and learn more about the use cases.

- Booking system - Handles users bookings and trips
- Travel system - Handles the communication with the various external travel and booking systems
- Email system - Entry point for User emails
- User system - Handles user related information
- Data analytics system - Handles processing of any user and travel data for data analytics

## Container Diagram
![image](https://github.com/intelligent-growth-solutions/flexibility-fertilisers/assets/1071238/ae6d85b7-304a-42e9-a51b-f8f65f260ff8)

This diagram shows the interactions of the various parts of the RoadWarrior system at a very high level. It indicates the flow through the RoadWarrior application rather than define the individual containers which are specified in narrower diagrams [here](./ContainerView/).

1. [Booking system](./ContainerView/booking-system.md)
1. [Alerting](./ContainerView/alerting.md)
1. [Data analytics](./ContainerView/data-analytics.md)
1. [Email](./ContainerView/email-system.md)
1. [Travel system API](./ContainerView/travel-system-api.md)
1. [Social media](./ContainerView/social-media.md)
1. [Users](./ContainerView/user-system.md)

## Critical Infrastructure
We identified that availability, reliability and elasticity are specifically important to the alert system, travel system API and booking system. By ensuring these systems are design to withstand surges, users will be able to received notifications even during times of travel disruptions. 

Other parts of the system such as the data analytics and social media integrations are not vital for keeping users up-to-date with ongoing travel issues.

<<<Diagram here>>>

The database technology that will be chosen needs to lend itself to horizontal scaling and distribution, as we require the data to be held in multiple data nodes.

[Link to ADR here]()

## Next Steps
While we have tried to keep the scope of the various systems quite narrow, there are a lot of requirements to cover that span a broad spectrum of technologies and engineering practices. There is a lot of front-end work, there asynchronous events to handle, email protocols, data analytics concepts etc.

Instead of trying to build everything before making the system available, our recommendation would be to run a series of prototypes or perhaps a public alpha version that will help with getting real world feedback. This way we can measure if our predictions of architectural characteristics and business cases are correct without spending several months or years of development.

![](./Misc/next-steps.png)

A simplified version of Road Warrior can be tried out by internal staff or perhaps a select group of volunteers to get a sense of what is important during inputting trips and while traveling.
