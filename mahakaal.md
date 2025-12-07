# Mahakaal Darshan Booking

Booking System for Mahakaal Darshan and similar entity (i.e **Omkareshwar Temple**)

**Mahakaal Darshan Booking Features** 

> provide easy booking of darshan slots

> Role Management (Devoteee, Attender, Approver)

> Integration with erpnext modules ( i.e Hrms , Non_profit, CRM)

> Allows Vip Darshan Booking

> Login With Mobile and Google Auth

> integration with payment system

> Devoteee's Companion



## Darshan Booking Module

### Doctypes 

On Dir ```apps/custom_booking/custom_booking/custom_booking/doctype```

1. Devoteee
2. Attender
3. Approver
4. Companion Table
5. Vip Darshan Appointment
6. Vip Darshan Appointment Table
7. Vip Darshan Slot Info
8. Vip Protocol
9. Slot
10. Slot Table
11. Vip Darshan Slot

### Roles

1. **Devoteee** Client / Customer
2. **Attender** Escort Person
3. **Approver** Verifies Details Of Vip Darshan Appointment

### Workflow (Darshan Flow)

```workflow not reflected code directory``` ***import and exported using fixtures***

Apply On **Darshan Appointment** Doctype

>  **Devoteeee** => Submit => Pending

>**Approver** => Approve => Pending => Approved (assigned attender)

> **Approver** => Reject => Pending => Rejected

> **Attender** => Mark Exit => Approved => Completed

