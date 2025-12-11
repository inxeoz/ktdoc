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
> * Creates Devoteee record (if Not exist) with phone
>
> * Verifies and return jwt token

> **google_login(google_token)**
>
> * Creates Devoteee record (if Not exist) with email
>
> * Verifies and return jwt token

> **profile()**
>
> * returns the profile details

> **update_profile(field1, field2, ..)**
>
> * updates the profile and returns **profile()**
>
> * Does not update phone or email

> **update_cred(phone, email) **
>
> * updates phone and email after otp verification for each (**phone**, **email**)
>
> * returns **profile()**

> **companion() **
>
> * returns companion details **Table**

> **add_companion(companion_name, age, gender) **
>
> * add companion
>
> * returns **companion()**

> **remove_companion(companion_id) **
>
> * removes companion row which has **companion_id**
>
> * returns **companion()**

---

### Attender

***(Attender Will be created Using Frappe)***

``attender_name`` ,``gender`` ,``dob``,**``phone``**,

``email``,``aadhar``,``location``

#### Api points

> **attender_login (phone,otp)**
>
> * Verifies and return jwt token

> **profile()**
>
> * returns the profile details

> **update_profile(field1, field2, ..)**
>
> * updates the profile and returns **profile()**
>
> * Does not update phone or email

> **update_cred( email) **
>
> * updates phone and email after otp verification (**email**)
>
> * returns **profile()**

> **get_list_of_available_attender(slot_date, slot) **
>
> * returns list of unassigned attender on **slot_date**, **slot**

> **mark_exit(appointment_id)**
>
> * marks exit if appointment's devoteee have completed darshan

> **get_appointment_details(appointment_id)**
>
> * returns basic details of appointment

> **get_appointment_list(field1, field2, ...)**
>
> * returns list of appointment which assigned to attender

---

### Approver

***(Approver Will be created Using Frappe)***

``approver_name`` ,``gender`` ,``dob``,**``phone``**,

``email``,``aadhar``,``location``

#### Api points

> **approver_login (phone,otp)**
>
> * Verifies and return jwt token

> **profile()**
>
> * returns the profile details

> **update_profile(field1, field2, ..)**
>
> * updates the profile and returns **profile()**
>
> * Does not update phone or email

> **update_cred(email) **
>
> * updates phone and email after otp verification for (**email**)
>
> * returns **profile()**

> **approve_vip_appointment(appointment_id, action ) **
>
> * applies action of appointment

> **list_of_vip_appointments(filter1, filter2, filter3, ...)**
>
> * returns list of appointment applying filter

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
> * create appointment and returns appointment name

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
> * returns list of protocol along with other related details

---

### Slot

``slot_name``, ``slot_start_time``, ``slot_end_time``,``description``

#### Api Points

> **get_slot_info(slot_name)**
>
> * returns the details for that **slot_name**

---

### Slot Table

``slot_name``,``current_capacity``

---

### Vip Darshan Slot

``slot_date``,``slot_info``,``appointments``

#### Api Points

> **vip_darshan_slot_info(slot_date)**
>
> * returns map (slot => current_capacity) on that slot_date

---

