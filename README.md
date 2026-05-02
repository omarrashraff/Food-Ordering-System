**Food Ordering System — Project Documentation**
Developed in collaboration with @minshawi0 as part of the Cryptography course at Cairo University, Faculty of Engineering.

**Overview**

This project is a Food Ordering System built to handle customer registration, account management, order placement, feedback submission, and menu interaction. The underlying database is structured around several core entities: Customer, Order, Menu, Meal, Feedback, Restaurant, and Payment.
The sections below cover the implemented logic for the Customer and Feedback tables, specifically around insert, update, and delete operations and the validation rules governing each.

**Customer Table Operations**

Sign-up checks whether the submitted email already exists in the Customer table. If a match is found, the registration is blocked and the user is told the email is already registered and to log in instead. If no match is found, the new record is inserted.
Profile updates require the customer to supply their registered email. The system verifies that email against the Customer table before applying any changes to fields like name, phone number, or address. If the email is not found, the update is rejected.
Account deletion follows the same pattern. The customer must provide a valid, registered email. The system confirms the email exists before executing the deletion. If it does not match any record, an error is returned.

**Feedback Table Operations**

Adding feedback requires two conditions to be satisfied simultaneously: the customer's email must exist in the Customer table, and the referenced Meal ID must exist in the Meal table. Both are validated before insertion proceeds.
Editing feedback requires the same two-factor validation — correct email and correct Meal ID. If either check fails, the update is blocked.
Deleting a feedback record is restricted to the customer who originally submitted it. Email verification is required before any deletion is carried out.

**Tech Stack**

Database: MySQL. Backend: SQL with C#. Core entities: Customer, Order, Menu, Meal, Feedback, Restaurant, and Payment.
