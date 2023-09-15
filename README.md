# Road Warrior by Flexibility Fertilizers

## Requirements
The architecture outlined below is based on the business case, requirements and user stories described [here].(Road%20Warrior%20Requirements%20and%20User%20Stories.md)

## System Overview

The below gives a high level view of the various systems and personas involved in interacting with Road Warrior
![image](https://github.com/intelligent-growth-solutions/flexibility-fertilisers/assets/2922498/45a69004-776c-4852-965a-abd711428279)

## Architectural Characteristics

Following the requirements and additional context, we assessed different architectural characteristics that are of main concern to the Road Warrior architecture.

| Characteristic |  Notes |
|--------|----|
| Availability | The system has strict downtime requirements of a maximum of 5 minutes a month. This is especially important for parts of the system that handle adding or updating travel details. |
| Reliability | The system must reliably add and update travel details. Missing updates could negatively impact the user's travel experience and have negative effects on user retention. |
| Elasticity  | Travel suffers from disruption in which case the system becomes even more important to its users wanting to keep on top of travel updates. In these instances, a surge in demand is expected and the system needs to be able to handle this gracefully and without impact to performance.
| Extensibility | The system integrates with various 3rd party travel and booking systems. Evolving with existing interfaces and adding new ones will be crucial to providing users the best possible set of details about their trips.  |


The following are characteristics that where considered relevant to the application but can be addressed through design and common practice.

| Characteristic |  Notes |
|--------|----|
| Localization | The application should be available internationally, which helps us support availability through multiple deployment locations. Different languages can be made available through design. |
| Installability | The system is accessible through a mobile app and website. To reach as many users as possible the app should be easy to install. This is well supported through different Application stores already.  |
| Privacy  | The system handles peoples' travel information which is personal and sensitive data. Identifiable data must therefore be kept private while an anonymized version must be accessible for data analytics. |
| Archivibility | The business model includes income to be derived from analytics run on user data. To make this successful, data needs to be retained and available to use for report creation. |

## Workflows

To identify the main components of the Road Warrior system, we looked at some of the workflows it needs to support.

![Workflowsv2](https://github.com/intelligent-growth-solutions/flexibility-fertilisers/assets/104081505/bc57a4cf-f925-473d-a336-7df2581d0551)

From the workflows we identified the following systems that we wanted to explore further. We may discover the need for more as we intestigate how the systems fit together and learn more about the use cases. 

- Booking system - Handles users bookings and trips
- Travel system - Handles the communication with the various external travel and booking systems
- Email system - Entry point for User emails
- User system - Handles user related information
- Data analytics system - Handles processing of any user and travel data for data analytics

## Container Diagram
![image](https://github.com/intelligent-growth-solutions/flexibility-fertilisers/assets/1071238/ae6d85b7-304a-42e9-a51b-f8f65f260ff8)

This diagram shows the interactions of the various parts of the RoadWarrior system at a very high level. It indicates the flow through the RoadWarrior application rather than define the individual containers which are specified in narrower diagrams below.

