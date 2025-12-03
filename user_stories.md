# User Story Template

**Title:**
_As a [user role], I want [feature/goal], so that [reason]._

**Acceptance Criteria:**
1. [Criteria 1]
2. [Criteria 2]
3. [Criteria 3]

**Priority:** [High/Medium/Low]
**Story Points:** [Estimated Effort in Points]
**Notes:**
- [Additional information or edge cases]

## Admin User Stories

### **User Story 1 — Admin Login**
**Title:** *As an admin, I want to log into the portal with my username and password, so that I can manage the platform securely.*

**Acceptance Criteria:**
1. Admin must enter a valid username and password.  
2. System verifies credentials against stored admin records.  
3. Admin is redirected to the admin dashboard upon successful login.

**Priority:** High  
**Story Points:** 3  
**Notes:** Show error message on invalid login.

---

### **User Story 2 — Admin Logout**
**Title:** *As an admin, I want to log out of the portal, so that I can protect system access.*

**Acceptance Criteria:**
1. Logout button must end the current admin session.  
2. Admin is redirected to the login page.  
3. Session cookies or tokens are invalidated.

**Priority:** High  
**Story Points:** 2  
**Notes:** Auto-logout after inactivity (optional).

---

### **User Story 3 — Add Doctor**
**Title:** *As an admin, I want to add doctors to the portal, so that they can be available for patient appointments.*

**Acceptance Criteria:**
- Admin can fill out a form with doctor details.  
- System validates required fields (name, specialization, email, etc.).  
- Doctor record is saved in the MySQL database.

**Priority:** High  
**Story Points:** 5  
**Notes:** Prevent duplicate doctor accounts based on email.

---

### **User Story 4 — Delete Doctor**
**Title:** *As an admin, I want to delete a doctor’s profile from the portal, so that outdated or incorrect profiles can be removed.*

**Acceptance Criteria:**
- Admin can select a doctor to delete.  
- System confirms the action before deletion.  
- Doctor record is removed from MySQL.

**Priority:** Medium  
**Story Points:** 3  
**Notes:** Prevent deletion if the doctor has active appointments (optional rule).

---

### **User Story 5 — Run MySQL Stored Procedure**
**Title:** *As an admin, I want to run a stored procedure in the MySQL CLI to get monthly appointment counts, so that I can track usage statistics.*

**Acceptance Criteria:**
- Admin executes stored procedure from MySQL CLI.  
- System returns appointment counts grouped by month.  
- Data is accurate and reflects current database content.

**Priority:** Low  
**Story Points:** 2  
**Notes:** Technical/admin-only task.

---

## Patient User Stories

### **User Story 6 — View Doctors (Public Access)**
**Title:** *As a patient, I want to view a list of doctors without logging in, so that I can explore options before registering.*

**Acceptance Criteria:**
- Public endpoint or page displays all doctors.  
- Basic doctor info is shown (name, specialization).  
- No login required.

**Priority:** High  
**Story Points:** 2  
**Notes:** Pagination recommended for large doctor lists.

---

### **User Story 7 — Patient Signup**
**Title:** *As a patient, I want to sign up using my email and password, so that I can book appointments.*

**Acceptance Criteria:**
- Registration form collects email, password, and basic info.  
- System validates unique email.  
- Account is created and stored in MySQL.

**Priority:** High  
**Story Points:** 3  
**Notes:** Password must follow security rules.

---

### **User Story 8 — Patient Login**
**Title:** *As a patient, I want to log into the portal, so that I can manage my bookings.*

**Acceptance Criteria:**
- Valid credentials allow access to patient dashboard.  
- Invalid login returns an error.  
- Session begins after successful login.

**Priority:** High  
**Story Points:** 2  
**Notes:** Future MFA support (optional).

---

### **User Story 9 — Patient Logout**
**Title:** *As a patient, I want to log out of the portal, so that I can secure my account.*

**Acceptance Criteria:**
- Logout button ends active session.  
- User is redirected to the home or login page.  
- Tokens or cookies are cleared.

**Priority:** Medium  
**Story Points:** 1  
**Notes:** Consider auto-logout settings.

---

### **User Story 10 — Book Appointment**
**Title:** *As a patient, I want to book an hour-long appointment with a doctor, so that I can receive medical consultation.*

**Acceptance Criteria:**
- Patient selects a doctor and chooses an available one-hour slot.  
- System prevents booking overlapping appointments.  
- Appointment is saved and confirmed.

**Priority:** High  
**Story Points:** 5  
**Notes:** Send confirmation email (optional).

---

### **User Story 11 — View Upcoming Appointments**
**Title:** *As a patient, I want to view my upcoming appointments, so that I can prepare accordingly.*

**Acceptance Criteria:**
- Patient dashboard displays a list of future appointments.  
- Each appointment shows date, time, and doctor.  
- Past appointments are excluded.

**Priority:** Medium  
**Story Points:** 3  
**Notes:** Sorting by date recommended.

---

## Doctor User Stories

### **User Story 12 — Doctor Login**
**Title:** *As a doctor, I want to log into the portal, so that I can manage my appointments.*

**Acceptance Criteria:**
- Doctor enters valid login credentials.  
- System validates and redirects to doctor dashboard.  
- Invalid login shows error.

**Priority:** High  
**Story Points:** 3  
**Notes:** Doctors must use accounts created by Admin.

---

### **User Story 13 — Doctor Logout**
**Title:** *As a doctor, I want to log out of the portal, so that I can protect my data.*

**Acceptance Criteria:**
- Logout ends the doctor session.  
- User is redirected to login page.  
- Session is fully invalidated.

**Priority:** Medium  
**Story Points:** 1  
**Notes:** Auto-logout recommended.

---

### **User Story 14 — View Appointment Calendar**
**Title:** *As a doctor, I want to view my appointment calendar, so that I can stay organized.*

**Acceptance Criteria:**
- Calendar shows scheduled appointments by day and time.  
- Appointments display patient names and appointment types (if applicable).  
- System highlights free and booked slots.

**Priority:** High  
**Story Points:** 5  
**Notes:** Consider color-coding availability.

---

### **User Story 15 — Mark Unavailable Slots**
**Title:** *As a doctor, I want to mark my unavailability, so that patients can book only available slots.*

**Acceptance Criteria:**
- Doctor selects date/time ranges when they are unavailable.  
- System blocks these periods from patient bookings.  
- Changes persist in the database.

**Priority:** Medium  
**Story Points:** 3  
**Notes:** Allow recurring unavailability (optional).

---

### **User Story 16 — Update Doctor Profile**
**Title:** *As a doctor, I want to update my profile with specialization and contact information, so that patients have up-to-date information.*

**Acceptance Criteria:**
- Doctor can edit profile fields (specialization, phone, email).  
- System validates required fields.  
- Changes are saved to the database.

**Priority:** Medium  
**Story Points:** 4  
**Notes:** Optional profile picture upload.

---

### **User Story 17 — View Patient Details**
**Title:** *As a doctor, I want to view patient details for upcoming appointments, so that I can be prepared.*

**Acceptance Criteria:**
- Doctor can open an appointment to view patient details.  
- System displays patient name, history, and contact info (where allowed).  
- Data is retrieved securely.

**Priority:** Medium  
**Story Points:** 4  
**Notes:** Ensure compliance with patient privacy rules.
