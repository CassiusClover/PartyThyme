
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

<img width="610" alt="image" src="https://github.com/user-attachments/assets/bf0db6a7-840b-4a4c-a831-b32d05fd7c90">

1. **Employees Working at a Specific Stage [CALL PT_Q1();]:**
This query retrieves the names of employees who are assigned to work at a specific stage, such as the "Party Stage." By joining the Employee and Stage tables, it matches employees to their designated stages. This information is crucial for managers who need to know which staff members are positioned where, allowing them to make adjustments for staffing needs, coordinate team activities, and ensure smooth operations during events.

<img width="432" alt="image" src="https://github.com/user-attachments/assets/42addca9-ff7b-4eef-b109-520e3a959fa3">
<img width="178" alt="image" src="https://github.com/user-attachments/assets/5e245570-9890-4157-aebc-b06a1a0c6e59">

2. **Count of Direct Reports per Manager[CALL PT_Q2();]:**
This query counts the number of employees who report directly to each manager by grouping employees based on their idBoss field, which indicates their supervisor. Understanding how many people report to each manager is valuable for assessing workload distribution and ensuring managers aren’t overburdened. It also helps in planning and allocating team members efficiently, especially when managing large teams during festival events.

 <img width="468" alt="image" src="https://github.com/user-attachments/assets/6670b6ab-4e8a-41c9-9ab2-41bf12f1ee08">
 <img width="282" alt="image" src="https://github.com/user-attachments/assets/6dbb36df-5da0-45ee-a9e8-7ae4dfa196e8">

3. **Employees Who Report Directly to Jessica Wilson[CALL PT_Q3();]:**
This query specifically identifies which employees report directly to a manager named Jessica Wilson by matching their idBoss field to her employee ID. Knowing who reports to a particular supervisor is useful for management purposes, such as scheduling meetings, distributing tasks, or resolving issues within a team. It streamlines communication and helps Jessica track and support her direct reports effectively.

<img width="444" alt="image" src="https://github.com/user-attachments/assets/e69853e0-5273-4cb0-a0e1-ffe0a1564140">
<img width="192" alt="image" src="https://github.com/user-attachments/assets/c441b85d-dd02-43d1-b5f5-70f837257536">

4. **Total Sponsorship Money Received from Each Company for Each Festival[CALL PT_Q4();]:**
This query calculates the total sponsorship amount received from each company for different festivals. It groups the results by SponsorName and Festival. Tracking sponsorship funds by company and festival is essential for financial planning and analysis. It provides insights into which sponsors are contributing the most and can help in identifying valuable partnerships for future events.

   <img width="274" alt="image" src="https://github.com/user-attachments/assets/0fc839ce-990d-49a1-b674-c1d922a4681c">
<img width="223" alt="image" src="https://github.com/user-attachments/assets/40d1a865-cffa-495c-ae60-fff833115c44">

5. **Ticket Sales by Type for Attendees Aged 20 to 30[CALL PT_Q5();]:**
This query retrieves the number of tickets sold, grouped by ticket type and the age of attendees (specifically those aged 20 to 30). By analyzing ticket sales by age group and type, managers can identify which demographics are buying certain types of tickets. This information is key for marketing strategies, promotions, and pricing models for future events.

 <img width="315" alt="image" src="https://github.com/user-attachments/assets/72c9164f-3a00-4f35-a2a3-455bf59c9fb9">
   <img width="234" alt="image" src="https://github.com/user-attachments/assets/596c31ef-aa2d-4c8e-bf37-af55c4d169ea">

6. **Performers Who Participated in More Performances Than the Average[CALL PT_Q6();]:**
This query identifies performers who have participated in more performances than the average number across all performers. By listing these high-performing artists, it can help organizers recognize popular or in-demand acts. Understanding which artists are most active can also inform scheduling decisions for future festivals and ensure top performers receive the exposure they deserve.

<img width="362" alt="image" src="https://github.com/user-attachments/assets/3229a4e5-e780-4938-985f-c239cc0a17fa">
<img width="231" alt="image" src="https://github.com/user-attachments/assets/d791c9a8-3987-4691-a900-51027ab5889c">

7. **Attendees Who Purchased More Than One Type of Ticket[CALL PT_Q7();]:**
This query checks for attendees who bought more than one type of ticket, although it currently returns no results because of a one-ticket-per-person limit. Tracking ticket purchases in this way would help identify attendees who are especially interested in multiple experiences at a festival, and it may guide changes to ticketing policies or create opportunities for special packages in the future.

<img width="429" alt="image" src="https://github.com/user-attachments/assets/724eb214-3418-4434-bae7-04e8fb743197">
<img width="369" alt="image" src="https://github.com/user-attachments/assets/05f776ff-50c6-4d80-b6e2-f69140b6dcdf">

8. **Vendors Ranked by Total Sales[CALL PT_Q8();]:**
This query ranks vendors based on their total sales, providing a clear view of which vendors performed best during the festival. Knowing which vendors are bringing in the most revenue can help organizers make decisions on vendor selection, placement, and partnership opportunities for future events. It’s a key piece of data for maximizing profit and enhancing the attendee experience.

<img width="534" alt="image" src="https://github.com/user-attachments/assets/e3686c9f-2bde-4947-ab6b-86d18a9da76a">
<img width="288" alt="image" src="https://github.com/user-attachments/assets/7638bff7-fff2-464f-ad2f-db23ce6f0277">

9. **Customers Who Spent More Than Average on Merchandise[CALL PT_Q9();]:**
This query identifies customers who spent more than the average amount on festival merchandise. Recognizing these high spenders is useful for targeting loyal customers with special offers, loyalty rewards, or exclusive merchandise. It helps build relationships with attendees and encourages repeat purchases.

<img width="353" alt="image" src="https://github.com/user-attachments/assets/56ea0b79-b2ba-4aa5-ab1b-48e919683042">
<img width="358" alt="image" src="https://github.com/user-attachments/assets/4117117a-64e7-4586-889d-6a9aec547e40">

10. **Top-Earning Artists and Their Pay[CALL PT_Q10();]:**
This query retrieves a list of the top-earning performers, displaying their salary. Knowing which artists are the highest earners provides insight into budget allocations for performances. It also helps in negotiating contracts for future festivals, ensuring the festival can balance high-profile acts with cost-effective performances.

<img width="468" alt="image" src="https://github.com/user-attachments/assets/656e7a9d-2e33-4233-90ac-0bc12478f367">
<img width="372" alt="image" src="https://github.com/user-attachments/assets/0e5af96c-bb8d-4044-97c0-f5c77c3c046f">


## Data Base Information
Name of the database: cs_jpo90532

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL PT_Q1();



