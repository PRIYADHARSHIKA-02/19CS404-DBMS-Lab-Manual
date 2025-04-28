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

# ER Diagram Submission - Priyadharshika L

## Scenario Chosen
Hospital database

## ER Diagram:
![Screenshot 2025-04-28 141534](https://github.com/user-attachments/assets/eedd26dd-6677-4757-8ef2-10d773f5f320)


## Entities and Attributes:

Patient: Patient_ID (implicitly needed), Fullname, DOB, Address, Phone_No, Insurance_Details, Email

Doctor: Doctor_ID, Fullname, Specialization, Work_Schedule

Appointment: Appointment_ID, Appointment_Date_and_Time, Doctor_ID, Patient_ID, Reason

Medical_Records: Record_ID, Patient_ID, Doctor_ID, Prescribed_Medicine, Diagnoses

Department: Dept_ID, Dept_Name, Dept_Head

## Relationships and Constraints:

TREATS (Doctor → Patient) (Cardinality: Many-to-Many, Participation: Partial)

HAVE (Patient/Doctor → Medical_Records) (Cardinality: One-to-Many, Participation: Total for Medical_Records)

HAVE (Doctor/Patient → Appointment) (Cardinality: One-to-Many, Participation: Partial)

ASSIGNED_TO (Doctor → Department) (Cardinality: Many-to-One, Participation: Partial)


## RESULT:
The hospital database ER diagram models patients, doctors, appointments, medical records, and departments with their attributes and relationships. It captures key interactions like treatments, appointments, and departmental assignments clearly and efficiently.
