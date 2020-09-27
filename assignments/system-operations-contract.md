# Assignment 3 - System Operations Contract
_Large Systems Development, Fall 2020_  
_**Team B**_

## Objective

**Sequence Diagram**  
Create sub-system sequence diagrams for your use case scenarios. The diagrams should have the actor and the two sub-systems.
Be sure there is traceability between use case scenario and the left side of
the sub-system sequence diagram.

**System Operations Contract**  
In a Java (or C# or other strongly typed language with support for remote objects) Write the system operations contracts as found in the sub-system sequence diagram’s right side. Add the DTOs and ETOs needed. Use a package manager as Maven, Gradle, or NuGet that allows for compilation outside the IDE.

Do this in a project on GitHub.
Add inline documentation for all methods, DTOs, and ETOs.

[extended description](https://datsoftlyngby.github.io/soft2020fall/resources/a3cead66-03-system-operations-contract.pdf)

## Content
- [Sequence Diagram](#sequence-diagram)
- [System Operations Contract](#system-operations-contract)

## Sequence Diagram

### System sequence diagram 1
![SSD1](/assets/SSD/UC1.png)
### System sequence diagram 2
![SSD2](/assets/SSD/UC2.png)
### System sequence diagram 3
![SSD3](/assets/SSD/UC3.png)
### System sequence diagram 4
![SSD4](/assets/SSD/UC4.png)
### System sequence diagram 5
![SSD5](/assets/SSD/UC5.png)
### System sequence diagram 6
![SSD6](/assets/SSD/UC6.png)


## System Operations Contract

[IContract](https://github.com/TEAM-B-SOFT2020/LSDContract)

``` Javascript
export default interface IContract {

    getCarrierInformation(iata: string): ICarrierDetail | NotFoundError | InvalidInputError

    getAirportInformation(iata: string): IAirportDetail | NotFoundError | InvalidInputError

    getFlightsAvailable(departure: IAirportDetail, arrival: IAirportDetail, depart: Moment): IFlightSummary[] | NotFoundError | InvalidInputError

    reserveFlight(id: IFlightIdentifier, amountSeats: number): IReservationSummary | NotFoundError | InvalidInputError

    bookFlight(reservedIds: IReservationDetail[], creditCardNumber:number, frequentFlyerNumber: number): IBookingDetail | InconsistentLengthError | NotFoundError | InvalidInputError

    getBooking(id: IBookingIdentifier): IBookingDetail | NotFoundError | InvalidInputError

    cancelBooking(id: IBookingIdentifier): void | NotFoundError | InvalidInputError

}  
```

