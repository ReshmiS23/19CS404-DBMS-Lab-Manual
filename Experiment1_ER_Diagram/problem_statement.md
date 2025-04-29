# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name

## Scenario Chosen:
Hospital (choose one)

## ER Diagram:
![ER Diagram](er_diagram.png)"C:\Users\acer\Pictures\Screenshots\Screenshot 2025-04-29 142745.png"

## Entities and Attributes:
```
Patient:
```
Attributes: patient_id (PK), first_name, last_name, dob, gender, phone, address, insurance_info
```
Doctor:
```
Attributes: doctor_id (PK), first_name, last_name, specialization, schedule
```
Appointment:
```
Attributes: appointment_id (PK), patient_id (FK), doctor_id (FK), appointment_date, status
```
Billing:
```
Attributes: billing_id (PK), patient_id (FK), amount, billing_date, payment_status
```
Inventory:
```
Attributes: inventory_id (PK), item_name, quantity, expiration_date

Relationships and Constraints:
Patient–Appointment–Doctor:
Relationship: A patient can have multiple appointments with different doctors.
```
Cardinality: Many-to-Many
```
Participation: Total for appointments (each appointment must link to a patient and a doctor)
```
Patient–Billing:
```
Relationship: A patient can have multiple bills.

Cardinality: One-to-Many

Participation: Partial (a patient may not be billed)

Extension (Prerequisite / Billing):
Billing is modeled as a separate entity linked to Patient. Each billing record includes an amount, date, and payment status. It is one-to-many, meaning a patient can have multiple bills, but each bill belongs to only one patient.
```
Design Choices:
```
Each entity has a clear primary key to uniquely identify records.

Foreign keys like patient_id, doctor_id ensure referential integrity in relationships.

Normalization is followed—separating Inventory, Billing, and Appointments avoids redundancy.

The Inventory entity is essential for hospital resource tracking.

Using status in appointments helps manage active/cancelled/completed appointments.
```
✅ RESULT:
```
The design is normalized and maintains referential integrity. It is scalable for a hospital database system, efficiently linking patients, doctors, appointments, billing, and inventory. The relationships capture real-world constraints and provide a solid foundation for implementing the system in SQL or any relational database.****
