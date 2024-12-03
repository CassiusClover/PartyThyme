
# PartyThyme Data Base

This database is designed to manage information related to a music festival, including attendees, performers, performances, vendors, sales, sponsors, employees, and stages. It captures data related to multiple festivals, with the goal of organizing festival logistics and ensuring smooth operations.

## Team Name
MIS JACKSON OOO
## Authors
- [@Caleb O'Neill](https://github.com/CassiusClover)
- [@Jonah O'Neill](https://github.com/joneill325)
- [@Emma Eslick](https://github.com/emmaeslick)
- [@Lexi Page](https://github.com/Lexip124)
- [@Ian Driggers](https://github.com/iandriggers)

## Problem Discription
This database is designed to manage information related to a music festival, including attendees, performers, performances, vendors, sales, sponsors, employees, and stages. It captures data related to multiple festivals, with the goal of organizing festival logistics and ensuring smooth operations.

### Music Festival Data Model

**Explanation of Data Model:**

Our model is based on the structure of a hypothetical music festival system, where multiple festivals take place, each with a variety of attendees, performances, vendors, and sponsors. This model helps manage key operational aspects of the festival, such as ticketing, sales, performances, and employee management.

At the core of this model is the **Festival** entity, representing each individual festival. Festivals are held at different locations and have specific start and end dates. Each festival has multiple vendors, performances, stages, and employees linked to it. To maintain clear relationships, we've established several one-to-many and many-to-many relationships that reflect the real-world structure of these events.

![PNG image](https://github.com/user-attachments/assets/9103a31b-a780-48ba-8668-b64c34c0252a)


## Data Dictionary
<img width="655" alt="Screenshot 2024-12-03 at 14 35 07" src="https://github.com/user-attachments/assets/112b2126-8968-4c18-b47c-aaa83e61ebe1">

<img width="655" alt="Screenshot 2024-12-03 at 14 36 18" src="https://github.com/user-attachments/assets/8a20809f-26ca-426d-ba80-52eed77ba1b4">

<img width="655" alt="Screenshot 2024-12-03 at 14 36 55" src="https://github.com/user-attachments/assets/1ec664dd-3e23-4f05-b05f-9a810f0565eb">

<img width="655" alt="Screenshot 2024-12-03 at 14 38 42" src="https://github.com/user-attachments/assets/c05e125a-da96-438c-a276-c3fb654a4ceb">

<img width="653" alt="Screenshot 2024-12-03 at 14 39 31" src="https://github.com/user-attachments/assets/76203b23-cea5-4777-9222-ebc2f8de8967">

<img width="653" alt="Screenshot 2024-12-03 at 14 40 01" src="https://github.com/user-attachments/assets/97076b9c-ed5d-43f4-91ec-212ad2203830">

<img width="653" alt="Screenshot 2024-12-03 at 14 40 35" src="https://github.com/user-attachments/assets/f6635891-1fce-49f1-bdc3-0a43cd4b7a9c">

<img width="653" alt="Screenshot 2024-12-03 at 14 41 08" src="https://github.com/user-attachments/assets/4c52128d-6310-4a23-ac90-bb389fb1d48e">

<img width="653" alt="Screenshot 2024-12-03 at 14 41 20" src="https://github.com/user-attachments/assets/a178f2d8-0fb7-4dab-b37f-3725ebf954b8">

<img width="653" alt="Screenshot 2024-12-03 at 14 41 35" src="https://github.com/user-attachments/assets/57c7bb20-38b2-42d2-bf04-7c034c2696df">

<img width="653" alt="Screenshot 2024-12-03 at 14 41 44" src="https://github.com/user-attachments/assets/612d3bbd-30f5-4317-91c0-4cfe5fc7da75">

<img width="591" alt="Screenshot 2024-12-03 at 14 43 04" src="https://github.com/user-attachments/assets/094ddcbe-78ed-4399-951c-2d56576f85c6">

<img width="499" alt="Screenshot 2024-12-03 at 14 44 15" src="https://github.com/user-attachments/assets/08f42f44-67d0-4ead-928d-618b7c784048">

<img width="499" alt="Screenshot 2024-12-03 at 14 44 47" src="https://github.com/user-attachments/assets/1d94d236-6958-4000-93e1-04a68c91d503">

<img width="499" alt="Screenshot 2024-12-03 at 14 45 07" src="https://github.com/user-attachments/assets/184be016-fdac-418a-b70d-ca37a420d69e">

<img width="499" alt="Screenshot 2024-12-03 at 14 45 38" src="https://github.com/user-attachments/assets/5f38abe3-99a2-4a0b-86e4-177f0f0dde5b">


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

1. **[Festival Attendee Sales Analysis by Age Group CALL PT_Q1();]:**
This query provides an insightful breakdown of sales performance across festivals by categorizing attendees into age groups: "Under 18," "18–25," "26–40," and "40+." It calculates the total number of unique attendees (TotalAttendees) for each festival, the total sales generated (TotalSales), and the average sales revenue per attendee (SalesPerAttendee). By leveraging these metrics, the query ranks festivals in descending order of their SalesPerAttendee, offering a clear understanding of which festivals and age groups are the most profitable. This analysis helps identify key customer demographics and optimize future marketing and sales strategies for specific festivals.

![PNG image](https://github.com/user-attachments/assets/6ddbb1e3-7c59-46e0-a1c0-b404f50a711e)

![PNG image](https://github.com/user-attachments/assets/7f038827-d297-482e-9ade-bcefddbf4a63)

2. **High-Value Attendee Analysis for Strategic Revenue Optimization[CALL PT_Q2();]:**

This query identifies attendees who have spent over $300 on tickets, providing key metrics such as their name, ticket type, total tickets purchased, total spending, and average ticket price. By focusing on the top 10 highest spenders, this analysis highlights high-value customers who contribute significantly to revenue. The results enable management to target these attendees with personalized offers, refine ticket pricing strategies, and prioritize premium ticket categories. This dynamic and actionable report ensures that as new purchases occur, the data will adapt, maintaining its relevance for strategic decision-making and revenue optimization.


![PNG image](https://github.com/user-attachments/assets/406014b5-590a-47de-8b6d-6561fbc1244b)

![unnamed-1](https://github.com/user-attachments/assets/6e53551b-363c-49fe-a659-b00a128931b2)


3. **"Unsold Items and Vendor Report [CALL PT_Q3();]:**
This query is designed to identify items that have not been sold or have zero sales by analyzing sales data in a database. It retrieves the item name, price, and vendor name from the Item and Vendor tables while calculating the total number of sales (TotalSold) for each item using a LEFT JOIN with the LineItem table. The LEFT JOIN ensures that items with no corresponding sales records in the LineItem table are included in the result, and the HAVING clause filters the data to show only items with TotalSold as NULL (indicating no sales records) or 0. Grouping by the item and vendor details ensures accurate aggregation for each unique item. This query provides valuable insight into unsold inventory, allowing businesses to make informed decisions about product promotion, pricing adjustments, or discontinuation.

![PNG image](https://github.com/user-attachments/assets/8b9574c2-df45-45e8-a38b-5e5885f38d23)


4. **Total Sponsorship Money Received from Each Company for Each Festival[CALL PT_Q4();]:**
This query creates a view that aggregates festival data, calculating the total number of sponsors, stages, and sponsorship revenue for each festival. It then retrieves festivals with sponsorship revenue over 5000 and sorts them in descending order, helping managers identify high-revenue festivals for further analysis or decision-making.

![unnamed](https://github.com/user-attachments/assets/ba6092ff-48aa-4744-8de4-38bdd3c8db30)

<img width="537" alt="Screenshot 2024-12-03 at 15 36 11" src="https://github.com/user-attachments/assets/f70d24d6-bc3d-400c-b71c-812992386258">


5. **Performer Evaluation [CALL PT_Q5();]:**
This query helps a manager evaluate performers by showing their total number of performances, average performance duration, and how their performance count compares to the average across all performers. We calculated duration by using the TIMESTAMPDIFF function, which calculates the difference between StartTime and EndTime of the performance. The query then computes the average of these differences (in minutes) for each performer, resulting in the average performance duration.
<img width="537" alt="Screenshot 2024-12-03 at 15 39 40" src="https://github.com/user-attachments/assets/b03642be-8c56-486d-9d50-d0ee863b2b63">

<img width="537" alt="Screenshot 2024-12-03 at 15 39 52" src="https://github.com/user-attachments/assets/1f5041de-a76b-4c4a-b3c0-cabd033410d9">


## Tableau ##
![PNG image](https://github.com/user-attachments/assets/b001c277-7fa3-453d-b504-033472492b62)
![PNG image](https://github.com/user-attachments/assets/5f35e123-9b5f-4b2a-84f7-fd60fe03fcb7)
![PNG image](https://github.com/user-attachments/assets/9726f1c5-cd9f-4141-8f06-873cdddf49a5)

Dashboard:
![PNG image](https://github.com/user-attachments/assets/714559a8-04b2-43d0-8032-4fd01d51e1e4)



## Data Base Information
Name of the database: cs_ idd69275

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL PT_Q1();



