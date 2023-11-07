# MIST4610-Project-1
# Team: 
**Team Name:**

macNcheese

**Team Members:**

1. Nidhi Ramani @nid20
2. Sarah Serghi < HREF="https://github.com/sserghi" TARGET="_blank">Sarah Serghi</a> 
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

**Table: Appointment**

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/0fde35cd-8b8f-4a14-bd8d-1d26c76ab392)

**Table: Billing**

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/321d93fa-82c5-4fa9-9237-4792d8d2a3a8)

**Table: Department**

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/7a5478e8-6b13-4020-aec7-5deb4314ff46)

**Table: Diagnostic Test**

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/9a774f7d-83fd-48e1-a950-b43bc4d4ba86)

**Table: Facility**

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/763d1e91-2f4d-4949-b70e-cb7091a346c6)

**Table: Feedback**

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/16ae38b9-1365-4992-bbf8-ffbef75740de)

**Table: Insurer**

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/dd042b54-677e-426a-88ba-36aabbc4b562)

**Table: Insurer_has_Patient**

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/09f590de-c99e-4766-aea4-08fdfadcc9cc)

**Table: Inventory**

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/e167a5ea-0683-4863-a7bd-51a44ddbd86c)

**Table: Medical Records**

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/327a3bb1-22fb-4179-b27c-26885403f806)

**Table: Patient**

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/a29550f2-e8d7-44cf-a49e-403137c1d827)

**Table: Prescription**

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/041cf449-258a-46c1-ade1-17923ea09012)

**Table: Staff**

![image](https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/edaeb1d5-dc56-45a4-972b-0386070eefb8)

# Queries:

# Database Information:

Fully did not understand this part of the project guidelines :) 
