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

---

### Interchangeable Terms

Appointment <=> Vip Darshan Booking <=> Vip Darshan Appointment

Customer <=> Client <=> Devoteee <=> User

---

### Devoteee

``devoteee_name`` ,``gender`` ,``dob``,**``phone``**,

``email``,``aadhar``,``location``, ``is_companion``,

``companion``(**Table**)

#### Api points

> **devoteee_login (Phone, otp)** 
>
> 1. Creates Devoteee record (if Not exist) with phone
> 2. Verifies and return jwt token

> **google_login(google_token)**
>
> 1. Creates Devoteee record (if Not exist) with email
> 2. Verifies and return jwt token

> **profile()**
>
> 1. returns the profile details

> **update_profile(field1, field2, ..)**
>
> 1. updates the profile and returns **profile()**
> 2. Does not update phone or email

> **update_cred(phone, email) **
>
> 1. updates phone and email after otp verification for each (**phone**, **email**)
> 2. returns **profile()**

> **companion() **
>
> 1. returns companion details **Table**

> **add_companion(companion_name, age, gender) **
>
> 1. add companion
> 2. returns **companion()**

> **remove_companion(companion_id) **
>
> 1. removes companion row which has **companion_id**
> 2. returns **companion()**

---

### Attender

***(Attender Will be created Using Frappe)***

``attender_name`` ,``gender`` ,``dob``,**``phone``**,

``email``,``aadhar``,``location``

#### Api points

> **attender_login (phone,otp)**
>
> 1. Verifies and return jwt token

> **profile()**
>
> 1. returns the profile details

> **update_profile(field1, field2, ..)**
>
> 1. updates the profile and returns **profile()**
> 2. Does not update phone or email

> **update_cred(phone, email) **
>
> 1. updates phone and email after otp verification for each (**phone**, **email**)
> 2. returns **profile()**

> **get_list_of_available_attender(slot_date, slot) **
>
> 1. returns list of unassigned attender on **slot_date**, **slot**

> **mark_exit(appointment_id)**
>
> 1. marks exit if appointment's devoteee have completed darshan

> **get_attender_appointment_details(appointment_id)**
>
> 1. returns basic details of appointment

> **get_attender_appointment_list(field1, field2, ...)**
>
> 1. returns list of appointment which assigned to attender

---

### Approver

***(Approver Will be created Using Frappe)***

``approver_name`` ,``gender`` ,``dob``,**``phone``**,

``email``,``aadhar``,``location``

#### Api points

> **approver_login (phone,otp)**
>
> 1. Verifies and return jwt token

> **profile()**
>
> 1. returns the profile details

> **update_profile(field1, field2, ..)**
>
> 1. updates the profile and returns **profile()**
> 2. Does not update phone or email

> **update_cred(phone, email) **
>
> 1. updates phone and email after otp verification for each (**phone**, **email**)
> 2. returns **profile()**

> **approve_vip_appointment(appointment_id, action ) **
>
> 1. applies action of appointment

> **list_of_vip_appointments(filter1, filter2, filter3, ...)**
>
> 1. returns list of appointment applying filter

---

### Companion Table

``companion_name`` ,``gender`` ,``age``,**``phone``**

---

### Vip Darshan Appointment

``devoteee_id`` ,``companion`` ,``slot``,``protocol`` ,

``state``, ``escort_person``, ``group_size``,``slot_date``

#### Api Points

> **create_appointment(slot_date, slot, protocol,state,companion devoteee_id ) **
>
> 1. create appointment and returns appointment name

---

### Vip Darshan Appointment Table

``appointment``

---

### Vip Darshan Slot Info

``slot_info``

> Single Doctype
>
> To configure slot for vip darshan like **capacity** and **slot ** (from Slot)

#### Api Points

> **get_static_vip_darshan_slot_info()**
>
> 1. returns the configuration of slot for vip darshan 

---

### Vip Protocol

``protocol_name``,``protocol_level``,``description``

#### Api Points

> **get_protocol_list()**
>
> 1. returns list of protocol along with other related details

---

### Slot

``slot_name``, ``slot_start_time``, ``slot_end_time``,``description``

#### Api Points

> **get_slot_info(slot_name)**
>
> 1. returns the details for that **slot_name**

---

### Slot Table

``slot_name``,``current_capacity``

---

### Vip Darshan Slot

``slot_date``,``slot_info``,``appointments``

#### Api Points

> **vip_darshan_slot_info(slot_date)**
>
> 1. returns map (slot => current_capacity) on that slot_date

---

