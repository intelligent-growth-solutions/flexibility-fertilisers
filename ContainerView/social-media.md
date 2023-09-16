## Social Media
The PostCreator receives a request by the application to create a post. This is handled in RoadWarrior, instead of on the user's device so more booking and trip information than may be available on the device can be used to write the post.

![](2023-09-15-16-16-57.png)

### Sequence diagram
#### User shares booking or trip
```mermaid
sequenceDiagram
    Application->>PostCreator: Create post 
    PostCreator->>TripSystem: Get trip
    TripSystem-->>PostCreator: [trip]
    PostCreator->>BookingSystem: Get booking
    BookingSystem-->>PostCreator: [booking]
    PostCreator->>PostCreator: Create post
    PostCreator-->>Application: [post]
```