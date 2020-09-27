# Assignment 2 - Use Case Model
_Large Systems Development, Fall 2020_  
_**Team B**_

## Objective
Create a Use Case Model for the team project. The model should be have:
* UML Use case diagram
* Actor descriptions including responsibilities.
* Fully dressed use case descriptions.

The model should be accompanied by a short textual walk-through.

[extended description](https://datsoftlyngby.github.io/soft2020fall/resources/a9edbcd7-02-use-case-model.pdf)

## Content
- [Verbs Glossary](#verbs-glossary)
- [Use Case Model](#use-case-model)
- [Text Written Use Cases](#text-written-use-cases)

##  Verbs Glossary
|Word                       |UCM|
|---                        |:-:|
|Have agreed                |-|
|Provide online booking     |-|
|Access to GDS through a web service for third party  |-|
|Access to GDS through a web application for employees  |-|
|Schedules will have the same departures and arrival on the same destination every day in the week |-|
|Carries identified by IATA carrier code   |✔️|
|Airports identified by IATA airport code   |✔️|
|Info timezone should be stored for each airport   |-|
|Booking one or more passengers   |✔️|
|Booking oneway trip  |✔️|
|Booking round-trip  |✔️|
|Passenger identified by PNR   |✔️|
|Show a time schedule  |✔️|
|Information about the carrier|✔️|
|Information about seats on the flight|✔️|
|Make booking for up to 9 person|✔️|
|See a booking given a PNR|✔️|
|Cancel a booking given a PNR|✔️|

## Use Case Model
![Use Case model](../assets/diagrams/UCD.svg )

## Text Written Use Cases

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

    Postcondition: (Success guaranties) A specific carrier found and returned.

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

    Postcondition: (Success guaranties) A specific airport found and returned.

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
    Employee select See bookings.
    System shows search form.
    Employee enters PNR.
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

    Postcondition: (Success guaranties) A booking has been canceld and delete.