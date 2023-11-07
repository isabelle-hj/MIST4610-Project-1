# MIST4610-Project-1
# Team: 
**Team Name:**

macNcheese

**Team Members:**

1. Arushi Charu [@arushicharu](https://github.com/arushicharu)
2. Isabelle Jordan [@isabelle-hj](https://github.com/isabelle-hj)
3. Nidhi Ramani [@nid20](https://github.com/nid20)
4. Sarah Serghi [@sserghi](https://github.com/sserghi) 

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

1. List the staff members whose manager is Bob Duncan.
<img width="539" alt="Screenshot 2023-11-07 at 1 17 35 PM" src="https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/353503d5-da5f-45fb-bcc0-1113f50d14a3">

As with any company or business, we want to be able to keep track of staff members that are considered managers and which staff members need to report to them. In this case, Bob Duncan currently needs to train his staff to follow a new protocol that will be implemented by the clinic. This query will help us figure out which of our staff members we need to send an email to to notify about their upcoming training.

2. Select the inventory from the PPE Storage Facility where the quantity in stock is less than 200.
<img width="581" alt="Screenshot 2023-11-07 at 1 21 50 PM" src="https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/bfa96a9a-e094-433f-8722-4ec207297cd1">

At this clinic, we want to make sure that we have the minimum quantity of basic PPE, such as gloves and masks, at all times. This query would allow us to see what PPE needs to be restocked. However, it should be taken into consideration that some of the PPE including respirators and eye goggles do not necessarily need to have at least 200 of the respective items in stock.

3. Find the day that patient whose name is Brooklyn Jenkins came in and list the staff member that saw her.
<img width="716" alt="Screenshot 2023-11-07 at 1 24 35 PM" src="https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/289b07fb-b8dc-4b93-b6ed-3b9a2f059c84">

In some cases, we need to be able to quickly pull up which staff member saw a specific patient. These cases could include a billing concern, an overall follow up question from the patient  needing to be directed to a staff member, a question from the patient about the medicine prescribed, etc.

4. List out the patient names who saw a staff member from the Pharmacy department and list the comments of the feedback that they wrote along with their name.
<img width="764" alt="Screenshot 2023-11-07 at 1 27 46 PM" src="https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/8692c9ac-e595-42e0-a573-33558cade67b">

This query is important because in the past we have had patients complain about wait time and customer service for our pharmacy department in particular. We can use this query to occasionally check on the reviews that patients are leaving for our clinic after they were checked in or seen by a staff member in the pharmacy department.

5. List the patients who rated the clinic a 7 or below, their rating, and their comments.
<img width="527" alt="Screenshot 2023-11-07 at 1 29 17 PM" src="https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/e142cb26-aa5c-4a40-a32d-c7f2ed0f5655">

This query is important because we always want to improve the patient experience. We can use this query to find patients who felt that their experience was below our standards, and see their comments to see how we can improve from here.

6. List the patients who had their vital signs checked who do not have insurance.
<img width="535" alt="Screenshot 2023-11-07 at 1 30 41 PM" src="https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/4a3f30e3-7d1b-4411-b52b-6939537db422">

This query is important when it comes to questions of billing. If patients are receiving care and having tests run while at the clinic, we need to know what tests are being run and how the patient plans to pay for them. This query shows us patients who will be paying out of pocket for their tests.

7. List the services provided that had an amount billed of at least 200 dollars.
<img width="407" alt="Screenshot 2023-11-07 at 1 32 34 PM" src="https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/26574180-c682-4536-b456-8511d1088207">

This query is important because, at this clinic, we are currently re-evaluating the prices of the different services we offer. We have been getting some feedback from our patients about the more expensive services which is why it is important to see which services are currently above $200 to perform a price analysis. 

8. List the staff members in the Cardiology department and their shift information.
<img width="530" alt="Screenshot 2023-11-07 at 1 33 31 PM" src="https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/6c3caee4-ee82-4177-9cf2-596dfbccb342">

This query is important because we have been receiving some complaints from our staff from the Cardiology department about them being overworked and not having much off time. This is why it’s important to examine the shift information from the cardiology department to re-evaluate the scheduling system. 

9. List the first and last name of patients who had a billing amount that was greater than the average of all billing amounts.
<img width="527" alt="Screenshot 2023-11-07 at 1 52 31 PM" src="https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/15bc4900-f8b1-4853-b303-4329a4bfc7a6">

This query is another one of our initiatives to re-evaluate the prices of the different services we offer.

10. As of June 1st 2023, list the patients first and last names who are not yet of age as well as their date of birth, only for those who have been prescribed Hydrocodone or Alprazolam.
<img width="567" alt="Screenshot 2023-11-07 at 1 35 06 PM" src="https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/28942eaa-f3de-4dd5-8b05-8ec5e549c56a">

This query is important because it allows us to identify who has been prescribed a medication that could potentially interfere with mandatory blood or urine testing (in this case, Alprazolam and Hydrocodone). This allows us to find those patients and schedule them appropriately for an appointment when their respective medication runs out in order for the patient to not consume the treatment for at least a day prior to their appointment to avoid any interference. Those who are underage but have not consumed either of these medications can be scheduled normally, but careful attention is needed for these particular patients.


<img width="609" alt="Screenshot 2023-11-07 at 1 50 50 PM" src="https://github.com/isabelle-hj/MIST4610-Project-1/assets/148258434/d402fa1c-4187-4d18-9ca4-896d62046d0d">

# Database Information:

 Name of the database: cs_macNcheesep1

 Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL Q1();
