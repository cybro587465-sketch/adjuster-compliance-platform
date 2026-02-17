# Adjuster Compliance Platform – MVP Demo Script

## Goal
Demonstrate automated compliance validation for independent adjusters.

---

## Demo Scenario

### Step 1 – Create Adjuster
Create new adjuster:
- Name: John Doe
- Status: Active
- Email: john@example.com

Expected result:
Adjuster appears in roster.

---

### Step 2 – Add License
Add Florida All Lines Adjuster license:
- Expiry: 12/31/2027
- Verified: Yes

Expected result:
License visible in profile.

---

### Step 3 – Upload Required Documents
Upload:
- W-9
- ID

Mark both Approved.

Expected result:
Documents show Approved.

---

### Step 4 – Create Requirement
Requirement:
- State: FL
- Claim Type: Property
- Required License: All Lines Adjuster
- Required Docs: W-9, ID
- Min Days to Expiry: 0

Expected result:
Requirement saved and active.

---

### Step 5 – Run Compliance Check
Run compliance for:
- Adjuster: John Doe
- State: FL
- Claim Type: Property
- As Of: Today

Expected result:
Compliant = TRUE
Reason Codes = []

---

### Step 6 – Introduce Failure
Change license expiry to yesterday.

Run compliance again.

Expected result:
Compliant = FALSE
Reason Codes = [LICENSE_EXPIRED]
Audit log entry created.
