
# PartyThyme Data Base

This database is designed to manage information related to a music festival, including attendees, performers, performances, vendors, sales, sponsors, employees, and stages. It captures data related to multiple festivals, with the goal of organizing festival logistics and ensuring smooth operations.

## Team Name
MIS JACKSON OOO
## Authors

- [@CassiusClover](https://github.com/CassiusClover)

 - [@joneill325](https://github.com/joneill325)
 - [@emmaeslick](https://github.com/emmaeslick)
  - [@Lexip124](https://github.com/Lexip124)

 
## Data Model
### Music Festival Data Model

**Explanation of Data Model:**

Our model is based on the structure of a hypothetical music festival system, where multiple festivals take place, each with a variety of attendees, performances, vendors, and sponsors. This model helps manage key operational aspects of the festival, such as ticketing, sales, performances, and employee management.

At the core of this model is the **Festival** entity, representing each individual festival. Festivals are held at different locations and have specific start and end dates. Each festival has multiple vendors, performances, stages, and employees linked to it. To maintain clear relationships, we've established several one-to-many and many-to-many relationships that reflect the real-world structure of these events.


### Key Relationships:

1. **Festival to Vendors**:  
   Each festival has multiple vendors selling goods during the event. This is represented by a one-to-many relationship between the **Festival** and **Vendor** entities. Vendors can sell various items, tracked in the **Item** table, and each vendor's sales are recorded in the **Sale** and **LineItem** tables.

2. **Vendor to Sales and Items**:  
   Vendors are linked to the **Item** entity, which contains details of the items they sell. A one-to-many relationship exists between **Vendor** and **Item**. Vendors make sales to attendees, and each sale is captured in the **Sale** table, which records the total sales amount and the date of each transaction. The **LineItem** table breaks down each sale into individual items, allowing the system to track what was sold and at what price.

3. **Festival to Stages and Performances**:  
   Each festival has several stages, and each stage hosts multiple performances. This is represented by a one-to-many relationship between the **Festival** and **Stage** entities. The **Stage** entity captures information such as the stage's name and capacity. A stage can have multiple performances, which are tracked in the **Performance** entity, where details like start and end times, as well as the associated performers, are stored.

4. **Performer to Performance**:  
   Each performance features one performer or group, represented by the **Performer** entity. Performers are linked to performances via a one-to-many relationship, meaning one performer can have multiple performances at the festival. The **Performer** entity contains details like the performer's name, genre, and performance cost.

5. **Attendee and Tickets**:  
   Attendees, represented by the **Attendee** entity, are linked to the **Ticket** entity, which tracks the type and price of tickets purchased. Each attendee can buy one ticket, creating a one-to-one relationship between **Attendee** and **Ticket**. The **Attendees** table captures personal information like the attendee's name, age, and email.

6. **Attendee to Performances (Attendants)**:  
   Attendees can attend multiple performances, and each performance can be attended by multiple attendees. To capture this many-to-many relationship, we have an associative entity called **Attendants**, which links **Attendee** to **Performance**. This allows the system to track which attendees attended which performances.

7. **Festival to Sponsorships**:  
   Each festival is supported by multiple sponsors, represented in the **Sponsorship** entity, which captures the sponsor's name and the amount of money given. The relationship between festivals and sponsors is managed via the **FestivalSponsor** junction table, which creates a many-to-many link between the **Festival** and **Sponsorship** entities. This ensures that each sponsor can support multiple festivals, and each festival can have multiple sponsors.

8. **Employee Management**:  
   Each festival employs various staff members, represented by the **Employee** entity. Employees are associated with specific stages (e.g., stage crew) and have roles such as stage boss or general staff. The **Employee** entity contains details like employee names, roles, and salaries. To capture the hierarchy within the staff, there is a self-referencing relationship in the **Employee** table, where each employee can have a supervisor (stage boss), indicated by the **idBoss** field.

9. **Total Purchases by Attendee**:  
   Attendees purchase items from vendors, and these purchases are summarized in the **TotalPurchases** table, which links the **Attendee** and **Sale** entities. This table provides a comprehensive view of an attendee’s spending during the festival.

### Additional Entities:

- **Stages**: Each festival consists of multiple stages, which are linked to the **Performance** and **Employee** entities. Each stage has an assigned capacity, and the stage boss (an employee) is responsible for overseeing it.
  
- **Items and LineItems**: Vendors sell different items, captured in the **Item** entity. Each sale made by a vendor is recorded in the **LineItem** table, allowing for detailed tracking of transactions.

### Conclusion:
The data model provides a robust structure to manage a multi-faceted music festival environment. From tracking attendees and their ticket purchases to managing performances, vendors, and sales, this model ensures that all critical aspects of festival management are covered. The well-defined relationships between entities allow for easy reporting on sales, attendee participation, sponsorships, and employee management, making this model suitable for use in a real-world music festival scenario.

---

