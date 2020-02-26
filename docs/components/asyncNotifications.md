### Async Notifications

- Areas used:
  - header

#### Overview

The system's architecture is modeled around 3FA, there is a delay and lack of information for actions such as approving and order or a payment. Validation is handled by the event system asyncroniously. When ever there is a an error, be it validation or some other sort of problem an async_notification record is created. This component must monitor this table using subscritions and display new notifications for the logged in user.

#### Context

#### Details
