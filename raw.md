---
export_on_save:
  markdown: true
markdown:
  path: README.md
  ignore_from_front_matter: true
---

<!-- made with markdown-preview-enhanced-->

# Assignment 1 - Logical Data Model {ignore=true}
_Large Systems Development, Fall 2020_  
_**Team B**_

## Objective {ignore=true}
Create a Logical Data Model for the team project. The model should be a UML class diagram, be sure to get the syntax right. The model should be accompanied by a short textual walk-through.

### Resources {ignore=true}
* [Assignment 1](https://datsoftlyngby.github.io/soft2020fall/resources/535325c7-01-logical-data-model.pdf)
* [Case 2](https://datsoftlyngby.github.io/soft2020fall/resources/aa00a079-case-2.pdf)

## Content {ignore=true}
[TOC]

___
## Case II
_An Airline GDS Global Distribution System_
### The Isac GDS {ignore=true}
A **number** of **flight** **carriers** have agreed to form a new **Global Distribution System** (GDS) called Isac. The GDS will provide online **booking** of **flight** **seats** for the involved **carriers**. Access to the GDS will be through a **web service** meant for third party **solutions**, and through a **web application** meant for **employees** in travel **agencies**.

#### Schedules {ignore=true}
Schedules for the **carriers** will be all **week** **schedules**, meaning that the **schedules** will have the same **departures** and **arrivals** on the same **destinations** on every **day** in the **week**. **Schedules** has **information** about: departure **airport** and **time**, arrival **airport** and **time**, **seat** count, **price** in **euros**.

**Carriers** are identified by their two letter IATA **carrier code**. **Flights** are identified by the **carrier code** followed by three **digits**.

**Airports** are identified by their three letter IATA **airport code**. **Information** about **timezone** should be stored for each **airport**.

#### Bookings {ignore=true}
As a **starting point**, **bookings** will not include **seat numbers**, but they might do in the future.

A **booking** can involve one or more **passengers**, and it can be a **one-way booking** or a **round-trip booking**. A **credit card number** or **frequent flyer number** should be attached to the **booking** as **e-ticket identification**.

A passenger on a **flight** is identified by a **Passenger Name Record (PNR)**, a PNR is a unique combination of **numbers** from the **English alphabet** and **numbers**, there is always six **alphanumeric characters** and the first can’t be a **number**. **Passenger names** must be given exactly as stated in the **passport**, but in **capital letters**.

#### The service {ignore=true}
The following tasks should be handled by the **web application**.
* Show a **time schedule** between two **airports** on a given **day**. The **schedule** should besides departure and arrival **times** include **information** about the **carrier** and number of free **seats** on the **flights**.

* Make a **booking** for up to 9 **persons** on a **one-way** or **round-trip** from one **airport** to another on a given **day**. An error message should be returned if the **seats** are not available any more. **Bookings** are atomic, meaning that all **passengers** and all legs should be either included or none of them should.

* See a **booking**, given a PNR from the **booking**.
* Cancel a **booking**, given a PNR from the **booking**.

### Glossary

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
|Week                       | ✔️ ||
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
|Euros                      | ✔️ ||
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
## Logical Data Model

### Diagram
![logical data model](assets/diagrams/logical-data-model.svg)

### PUML Source
_puml_
@import "diagrams/diagrams.puml" {code_block=true as="java"}