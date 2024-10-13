
# PartyThyme Data Base

This database is designed to manage information related to a music festival, including attendees, performers, performances, vendors, sales, sponsors, employees, and stages. It captures data related to multiple festivals, with the goal of organizing festival logistics and ensuring smooth operations.

## Team Name
MIS JACKSON OOO
## Authors

- [@CassiusClover](https://github.com/CassiusClover)

 - [@joneill325](https://github.com/joneill325)
 - [@emmaeslick](https://github.com/emmaeslick)
  - [@Lexip124](https://github.com/Lexip124)
  - [@iandriggers](https://github.com/iandriggers)

 
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


## Queries
<img width="305" alt="image" src="https://github.com/user-attachments/assets/c2eb5055-b521-48e4-9e18-b499d9be9e12">

1.	 Retrieve the names of employees working on a particular stage.
<img width="432" alt="image" src="https://github.com/user-attachments/assets/42addca9-ff7b-4eef-b109-520e3a959fa3">
<img width="178" alt="image" src="https://github.com/user-attachments/assets/5e245570-9890-4157-aebc-b06a1a0c6e59">


2.	This query counts how many direct reports each manager has.
 <img width="468" alt="image" src="https://github.com/user-attachments/assets/6670b6ab-4e8a-41c9-9ab2-41bf12f1ee08">
 <img width="282" alt="image" src="https://github.com/user-attachments/assets/6dbb36df-5da0-45ee-a9e8-7ae4dfa196e8">

3.	This query is designed to retrieve a list of employees who report directly to Jessica Wilson by checking the idBoss of each employee against Jessica Wilson's employee ID. Useful for finding who reports to a specific boss
   <img width="444" alt="image" src="https://github.com/user-attachments/assets/e69853e0-5273-4cb0-a0e1-ffe0a1564140">
<img width="192" alt="image" src="https://github.com/user-attachments/assets/c441b85d-dd02-43d1-b5f5-70f837257536">

4.	Query: Total amount of sponsorship money received from a specific company for each festival (see variation on next page where I instead search a specific company to see what their total sponsorship was for a festival instead of pulling every company and sponsorName.
   <img width="274" alt="image" src="https://github.com/user-attachments/assets/0fc839ce-990d-49a1-b674-c1d922a4681c">
<img width="223" alt="image" src="https://github.com/user-attachments/assets/40d1a865-cffa-495c-ae60-fff833115c44">
5.	Query returns the number of tickets sold for each ticket type for attendees aged 20 to 30, grouped by both ticket type and age.
   <img width="315" alt="image" src="https://github.com/user-attachments/assets/72c9164f-3a00-4f35-a2a3-455bf59c9fb9">
   <img width="234" alt="image" src="https://github.com/user-attachments/assets/596c31ef-aa2d-4c8e-bf37-af55c4d169ea">
6.	This query identifies performers who have participated in more performances than the average number of performances and also lists the number of performances
<img width="362" alt="image" src="https://github.com/user-attachments/assets/3229a4e5-e780-4938-985f-c239cc0a17fa">
<img width="231" alt="image" src="https://github.com/user-attachments/assets/d791c9a8-3987-4691-a900-51027ab5889c">
7.	This query retrieves the attendees who have purchased tickets of more than one type. 
Note: It doesn’t return anything because the data we pulled from ChatGPT just had everyone buy one ticket (or maybe we stipulated that, idk) but this query still would be useful for  a manager. 
<img width="429" alt="image" src="https://github.com/user-attachments/assets/724eb214-3418-4434-bae7-04e8fb743197">
<img width="369" alt="image" src="https://github.com/user-attachments/assets/05f776ff-50c6-4d80-b6e2-f69140b6dcdf">

8. List the Vendors by Total Sales
<img width="534" alt="image" src="https://github.com/user-attachments/assets/e3686c9f-2bde-4947-ab6b-86d18a9da76a">
<img width="288" alt="image" src="https://github.com/user-attachments/assets/7638bff7-fff2-464f-ad2f-db23ce6f0277">

9.Which customers spent more than average on merch?
<img width="353" alt="image" src="https://github.com/user-attachments/assets/56ea0b79-b2ba-4aa5-ab1b-48e919683042">
<img width="358" alt="image" src="https://github.com/user-attachments/assets/4117117a-64e7-4586-889d-6a9aec547e40">

10.How much did top earning artists get paid?
<img width="468" alt="image" src="https://github.com/user-attachments/assets/656e7a9d-2e33-4233-90ac-0bc12478f367">
<img width="372" alt="image" src="https://github.com/user-attachments/assets/0e5af96c-bb8d-4044-97c0-f5c77c3c046f">






