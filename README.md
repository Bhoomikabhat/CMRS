Customer Relationship Management System


Problem Statement
In today's competitive market, businesses must effectively manage their customer relationships to drive growth, enhance customer satisfaction, and improve decision-making. However, many organizations struggle with fragmented customer data, untracked sales interactions, and a lack of actionable insights.
This project aims to develop a Customer Relationship Management (CRM) System that provides a centralized platform for managing customer profiles, tracking sales and interactions, and generating insightful reports. The system will include features like customer profile management, sales tracking, interaction logging, and reporting on customer activity and trends. It will also incorporate robust error handling, logging mechanisms, and thorough testing using JUnit to ensure system reliability and maintainability.
Tech Stack
•	Spring Boot
•	Spring Security
•	 MySQL 
•	JUnit & Mockito
•	Postman (for testing)
Modules
1.	Customer Management
o	Create, update, delete, and fetch customer profiles.
2.	Sales Tracking
o	Manage sales data, assign sales to customers.
3.	Interaction Logs
o	Log different types of interactions with follow-up dates.
4.	Reporting
o	Analyze customer interactions and sales trends.
5.	Authentication and Authorization
o	Secure endpoints with Spring Security and role-based access (ADMIN, SALES_REP).
6.	Logging
o	System logging and error tracking using SLF4J/Logger.
7.	Testing
o	Unit tests with JUnit
o	Service mocking with Mockito

Entities Table
1. Customer
Field Name	Type	Description
id	Long	Unique ID for the customer
name	String	Customer's full name
email	String	Unique email address
phone	String	Contact phone number
address	String	Residential or office address
🔗 Relationships:
•	One customer can have many sales
•	One customer can have many interaction logs
________________________________________
2. Sales
Field Name	Type	Description
id	Long	Unique ID for the sale
customer	Customer	The customer who made the purchase
product	String	Product or service sold
amount	Double	Sale amount in currency
saleDate	LocalDate	Date when the sale happened
🔗 Relationships:
•	Many sales belong to one customer



________________________________________
3. InteractionLog
Field Name	Type	Description
id	Long	Unique ID for the interaction
customer	Customer	Customer involved in the interaction
interactionType	String	Type of interaction (Call, Email, Meeting)
notes	String	Additional details or comments
interactionDate	LocalDate	Date of the interaction
salesRepUsername	String	Username of the sales representative
followUpDate	LocalDate	Optional follow-up date
🔗 Relationships:
•	Many interaction logs belong to one customer

Commands for postman
1.	Add a Customer
Method:  POST
URL: http://localhost:8081/customers

2.	Add an Interaction Log for a Customer
Method: POST
URL: http://localhost:8081/interactions/{customerId}
3.	Get All Customers
Method: GET
URL: http://localhost:8081/customers

4.	Get Customer Activity Report
Method: GET
URL: http://localhost:8081/reports/customer-activity

Delete update and put methods are implemented in similar way

The Customer Relationship Management (CRM) system developed in this project provides a comprehensive solution for managing customer data, tracking sales, logging customer interactions, and generating insightful reports on customer activity and trends. By integrating modules for customer profile management, sales tracking, and interaction logging, the system enables organizations to maintain a complete and up-to-date view of their customer relationships. It also incorporates role-based access control using Spring Security, ensuring that sensitive information is protected and accessible only to authorized users. Robust logging and error handling mechanisms are implemented to monitor system behavior and capture unexpected issues, improving reliability and maintainability. Additionally, unit and integration tests using JUnit ensure that individual components and the overall system function correctly. Overall, this CRM system supports better customer engagement, enhances decision-making through data insights, and lays a solid foundation for future scalability and feature enhancements.

