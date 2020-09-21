  
  
  
  
  
#  Assignment 1 - Logical Data Model
  
_Large Systems Development, Fall 2020_  
_**Team B**_
  
##  Objective
  
Create a Logical Data Model for the team project. The model should be a UML class diagram, be sure to get the syntax right. The model should be accompanied by a short textual walk-through.
  
###  Resources
  
* [Assignment 1](https://datsoftlyngby.github.io/soft2020fall/resources/535325c7-01-logical-data-model.pdf )
* [Case 2](https://datsoftlyngby.github.io/soft2020fall/resources/aa00a079-case-2.pdf )
  
##  Content
  
  
- [Case II](#case-ii )
  - [Glossary](#glossary )
- [Logical Data Model](#logical-data-model )
  - [Diagram](#diagram )
  - [PUML Source](#puml-source )
  
___
##  Case II
  
_An Airline GDS Global Distribution System_
###  The Isac GDS
  
A **number** of **flight** **carriers** have agreed to form a new **Global Distribution System** (GDS) called Isac. The GDS will provide online **booking** of **flight** **seats** for the involved **carriers**. Access to the GDS will be through a **web service** meant for third party **solutions**, and through a **web application** meant for **employees** in travel **agencies**.
  
####  Schedules
  
Schedules for the **carriers** will be all **week** **schedules**, meaning that the **schedules** will have the same **departures** and **arrivals** on the same **destinations** on every **day** in the **week**. **Schedules** has **information** about: departure **airport** and **time**, arrival **airport** and **time**, **seat** count, **price** in **euros**.
  
**Carriers** are identified by their two letter IATA **carrier code**. **Flights** are identified by the **carrier code** followed by three **digits**.
  
**Airports** are identified by their three letter IATA **airport code**. **Information** about **timezone** should be stored for each **airport**.
  
####  Bookings
  
As a **starting point**, **bookings** will not include **seat numbers**, but they might do in the future.
  
A **booking** can involve one or more **passengers**, and it can be a **one-way booking** or a **round-trip booking**. A **credit card number** or **frequent flyer number** should be attached to the **booking** as **e-ticket identification**.
  
A passenger on a **flight** is identified by a **Passenger Name Record (PNR)**, a PNR is a unique combination of **numbers** from the **English alphabet** and **numbers**, there is always six **alphanumeric characters** and the first can’t be a **number**. **Passenger names** must be given exactly as stated in the **passport**, but in **capital letters**.
  
####  The service
  
The following tasks should be handled by the **web application**.
* Show a **time schedule** between two **airports** on a given **day**. The **schedule** should besides departure and arrival **times** include **information** about the **carrier** and number of free **seats** on the **flights**.
  
* Make a **booking** for up to 9 **persons** on a **one-way** or **round-trip** from one **airport** to another on a given **day**. An error message should be returned if the **seats** are not available any more. **Bookings** are atomic, meaning that all **passengers** and all legs should be either included or none of them should.
  
* See a **booking**, given a PNR from the **booking**.
* Cancel a **booking**, given a PNR from the **booking**.
  
###  Glossary
  
  
|Word                       |LDM|Description |
|---                        |:-:|---|
|Number                     | - ||
|Flight                     | ✔️ ||
|Global Distribution System | - ||
|Booking                    | ✔️ ||
|Seats                      | ✔️ ||
|Web Service                | - ||
|Solutions                  | - ||
|Employees                  | ✔️ ||
|Agencies                   | ✔️ ||
|Schedules                  | ✔️ ||
|Carriers                   | ✔️ ||
|Week                       | ? ||
|Time Zone                  | ✔️ ||
|Departures                 | ✔️ ||
|Arrivals                   | ✔️ ||
|Destinations               | ✔️ ||
|Day                        | ✔️ ||
|Information                | - ||
|Airport                    | ✔️ ||
|Time                       | ✔️ ||
|Seat                       | - ||
|Price                      | ✔️ ||
|Euros                      | - ||
|Carrier Code               | ✔️ ||
|Digits                     | - ||
|Airport Code               | ✔️ ||
|Starting point             | ✔️ ||
|Seat numbers               | ✔️ ||
|Passengers                 | ✔️ ||
|Round-trip booking         | ✔️ ||
|One-Way booking            | ✔️ ||
|Credit Card Number         | ✔️ ||
|Frequent flyer number      | ✔️ ||
|E-ticket Identification    | ✔️ ||
|Passenger Name Record (PNR)| ✔️ ||
|English Alphabet           | - ||
|Alphanumeric characters    | - ||
|Passport                   | ✔️ ||
|Capital Letters            | - ||
|Passenger names            | ✔️ ||
|web application            | - ||
|Persons                    | ✔️ ||
|Service                    | - ||
  
___

###  Verbs

|Word                       |UCM|
|---                        |:-:|
|Have agreed                |-|
|Provide online booking     |-|
|Access to GDS through a web service for thrid party  |-|
|Access to GDS through a web application for employees  |-|
|Schedules will have the same depatures and arrival on the same destination every day in the week |-|
|Carries indentified by IATA carrier code   |✔️|
|Airports indentified by IATA airport code   |✔️|
|Info timezone should be stored for each airport   |-|
|Booking one or more passengers   |✔️|
|Booking oneway trip  |✔️|
|Booking round-trip  |✔️|
|Passenger indentifed by PNR   |✔️|
|Show a time scheddule  |✔️|
|Information about the carrier|✔️|
|Information about seats on the flight|✔️|
|Make booking for up to 9 person|✔️|
|See a booking given a PNR|✔️|
|Cancel a booking given a PNR|✔️|

### Actors
- Employee
- Passenger

___
##  Logical Data Model
  
  
###  Diagram
  
![logical data model](assets/diagrams/logical-data-model.svg )
  

## Use Case Model

### Diagram

![Use Case model](assets/diagrams/UCD.svg )

### Text written Use Cases

    UC1
    Name: Find Carrier

    Description: 
    An employee has to be able to enter the web application and find a carrier using IATA code.

    Primary Actor: Employee 

    Preconditions: None

    Main Scenario:

    Employee selects find carrier.
    System show searchform.
    Employee enters IATA as search data.
    System returns carrier.

    Postcondition: (Success guaranties) A specific carrier found and returend.

___

    UC2
    Name: Find airport

    Description: 
    An employee has to be able to enter the web application and find a airport using IATA code.

    Primary Actor: Employee 

    Preconditions: None

    Main Scenario:
    Employee selects find airport.
    System show searchform.
    Employee enters IATA as search data.
    System returns airport.

    Postcondition: (Success guaranties) A specific airport found and returend.

___
  
    UC3
    Name: Book flight

    Description: 
    A passenger has to be able to book a flight for up to 9 people per booking and indicate 
    if booking is a oneway-trip or a round-trip.

    Employee should be able to book the flight in case passenger needs help.


    Primary Actor: Passenger 
    Secondary Actor: Employee

    Preconditions: Passenger or Employee has to be in the "See schedule" use case.

    Main Scenario:
    Passenger choose scheduled flight.
    System show booking form with available seats.
    Passenger fills booking form.
    Passenger books flight.

    Alternative Scenario:
    Employee choose scheduled flight.
    System show booking form with available seats.
    Employee fills booking form with passengers information.
    Employee books flight.
    
    Postcondition: (Success guaranties) Passenger is returned to page with order confirmation.

___
  
    UC4
    Name: See Schedule

    Description: 
    Passenger has to be able to see a list of schedueled flights. 
    Employee has to be able to see a list of schedueled flights.

    Primary Actor: Passenger
    Secondary Actor: Employee

    Main Scenario:
    Passenger selects see schedule.
    System show list of scheduled flights.
    Passenger see list of scheduled flights.   
   
    Alternative Scenario:
    Employee selects see schedule.
    System show list of scheduled flights.
    Employee see list of scheduled flights.  
   
    Postcondition: (Success guaranties) Passenger see list of scheduled flights. 
    Alternative Postcondition: (Success guaranties) Employee see list of scheduled flights. 
___
  
    UC5
    Name: See Booking

    Description: 
    Passenger has to be able to see a list of all their bookings given a PNR.
    Employee has to be able to see a list of all Passengers booking given a PNR

    Primary Actor: Passenger
    Secondary Actor: Employee

    Main Scenario:
    Passenger select See bookings
    System shows search form
    Passenger enters PNR
    System list relevant bookings.
    Passenger selects a booking in list.

    Alternative Scenario:
    Employee select See bookings
    System shows search form
    Employee enters PNR
    System list relevant bookings.
    Employee selects a booking in list.

    Postcondition:(Success guaranties) A booking has been selected. 

___
  
    UC6
    Name: Cancel Booking

    Description: 
    Passenger has to be able to cancel a booking.
    Employee has to be able to cancel a booking.

    Primary Actor: Passenger
    Secondary Actor: Employee

    Precondition: A booking has to have been selected.

    Main Scenario:
    Passenger select cancel booking.
    System promts a confirmation window.
    Passenger confrims.
    System deletes booking from system.

    Alternative Scenario:
    Employee select cancel booking.
    System promts a confirmation window.
    Employee confrims.
    System deletes booking from system.

    Postcondition:(Success guaranties) A booking has been canceld and delete.

###  PUML Source
  
_puml_
```java
@startuml "logical-data-model"
skinparam Shadowing False
skinparam RoundCorner 10
skinparam DefaultFontColor DimGrey
  
skinparam Object {
    BackgroundColor DodgerBlue
    ArrowColor DimGrey
    BorderColor White
    FontColor White
    FontStyle Bold
    AttributeFontColor White
    StereotypeFontColor White
}
  
Object Flight {
    'This is a combination of carrier code and the three digits
    IATA Combined Code
    Departure Date & Time
    Arrival Data & Time
    Number of Seats
    Seat Price
}
  
Object Carrier {
    IATA Carrier Code
}
  
Object Airport {
    IATA Airport Code
    Name
    Time Zone
}
  
Object Person {
    First Name
    Last Name
    Passport
}
  
Object Booking {
    Price
    'if credit card is null booking is paid by Frequent Flyer Number
    Credit Card Number
    Frequent Flyer Number
}
  
Object Schedule
Object Agency 
  
Airport o-"*" Flight: Start Destination
Airport o-"*" Flight: End Destination
  
Flight "*"--"1" Schedule
Flight "*"-"*" Person: PNR
Carrier o-"1" Schedule
  
Person "1.9"--"*" Booking: Passenger
Person "*"-o Agency: Employee
  
Booking "*"--"1.*" Flight
  
@enduml
```  
  