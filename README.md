# MIST4610-Project-1
# Team: 
**Team Name:**

Mac And Cheese

**Team Members:**

1. Nidhi Ramani @nid20
2. Sarah Serghi @sserghi
3. Arushi Charu @arushicharu
4. Isabelle Jordan @isabelle-hj

# Problem Description:

We have been tasked with modeling and building a relational data model for an emergency healthcare clinic. For this project, ChatGPT acted as the owner and operator of this clinic. We asked it for the data it thought was the most important to model, and we developed our model from there. The central entities of this model are Patients - which contains information about patients seen at the clinic - and Staff - which includes information about every staff member employed by the clinic. Other entities we modeled include billing information, medical records, appointment details, and clinic inventory, among others. We also performed several queries using the data model that could be used to provide key insights into the operations of the clinic.

# Data Model:

Our model represents operations of an emergency clinic. 

One of the central entities of the model is Staff, which contains a unique identifier for each employee, their first & last name, contact information, and shifts they work. Staff has a one-to-many relationship with the Department entity, meaning many staff members can be in one department, and one department has many employees. The Department entity contains information such as the name, phone number, and floor of each department. Staff also has a one-to-one relationship with Department to designate a staff member as the head of a department, and a one-to-one recursive relationship to indicate that certain employees are supervisors of others.

The Department entity also has a one-to-many relationship with Facility, which contains the name of the facility and the year it was established. The Facility entity also has a one-to-many relationship with the Inventory table. Inventory includes details about each item the facility has, the quantity they have, the date of the last restock, and supplier information. A facility can have many things in inventory, and many items in the inventory can be in one facility.

Another central entity in our model is Patient, which includes the first & last name of the patient, their date of birth, contact information, medical history, and insurance information. The Patient table has a many-to-many relationship with the Insurer entity, which contains information about the patient's insurance company. These tables are joined by the table Insurer_has_Patient, which includes the policy number, type of coverage, and the start & end dates of the policy.

The Patient table also has a relationship with the Medical Records entity. This entity contains the diagnosis of the patient as well as important information from their visit to the clinic. This is a one-to-many relationship; patients could have multiple records, if they visit the clinic multiple times, and one record is connected to one patient. The final one-to-many relationship is with Feedback, which allows the patient to give feedback about and rate their time at the clinic.

The Patient and Staff tables have two many-to-many relationships between them. The first creates the Diagnostic Test table. This table contains information about the date and type of the test. The other many-to-many relationship creates the Appointment table, which shows the date and time of the appointment and the reason for the patient's visit. This table has one-to-many relationships with both Prescription, which contains data such as the name of the medication, the dosage, and the date prescribed, and Billing, which details the amount the patient is being billed and the services provided during their stay.

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/ef1d7571-72d8-45b7-959f-c0d050c96d54)

# Data Dictionary: 

Figured we should wait and finalize the data model before putting in our data charts.

# Queries:

# Database Information:

Fully did not understand this part of the project guidelines :) 
