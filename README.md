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

One of the central entities of the model is Staff, which contains a unique identifier for each employee, their first & last name, contact information, and shifts they work. Staff has a one-to-many relationship with the Department entity, meaning many staff members can be in one department, and one department has many employees. The Department entity contains information such as the name, phone number, and floor of each department.

The Department entity also has a one-to-many relationship with Facility, which contains the name of the facility and the year it was established. The Facility entity also has a one-to-many relationship with the Inventory table. Inventory includes details about each item the facility has, the quantity they have, the date of the last restock, and supplier information. A facility can have many things in inventory, and many items in the inventory can be in one facility.

Another central entity in our model is Patient, which includes the first & last name of the patient, their date of birth, contact information, medical history, and insurance information. The Patient table has a many-to-many relationship with the Prescription entity - which contains information about the medication, dosage, and the date prescribed - as a patient can be prescribed many medications, and medications can be prescribed to many patients. These are connected by the intermediate table Patient_Prescription.

The Patient entity is also connected to the Billing table, which contains details about what and how much the patient is being billed for. This is a one-to-many relationship, as one patient can have many bills, and a bill is sent to one patient. Patient also has a one-to-many relationship with Feedback, a table which contains comments about and a rating of their experience at this clinic. Patients can send feedback multiple times, and one feedback report is connected to one patient. The Patient table also has a relationship with the Medical Records entity. This entity contains the diagnosis of the patient as well as important information from their visit to the clinic. This is a one-to-many relationship; patients could have multiple records, if they visit the clinic multiple times, and one record is connected to one patient.

**Question for the group**

So the only tables I haven't included in this are Diagnostic Test and Appointment; I wanted to know if we are calling these intermediate tables, meaning Staff and Patient have two many-to-many relationships? Just wanted to clarify before I wrote a whole thing about it lol

**Also need to insert final picture of the data model**

# Data Dictionary: 

Figured we should wait and finalize the data model before putting in our data charts.

# Queries:

# Database Information:

Fully did not understand this part of the project guidelines :) 
