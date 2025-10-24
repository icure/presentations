---
marp: true
theme: gaia
paginate: false
style: |
  section {
    font-size: 36px;
    background-color: #efefe4ff;
    background-image: url('logo.svg');
    background-position: calc(100% - 20px) 100%;
    background-size: 80px 80px;
    background-repeat: no-repeat;
  }
  section h1 {
    font-size: 72px;
  }
  section h2 {
    font-size: 48px;
  }
  section li {
    font-size: 24px;
  }
  section li em {
    font-size: 36px;
  }
  section li b {
    font-size: 36px;
  }
  section.lead h1 {
    font-size: 72px;
  }
  section.lead h2 {
    font-size: 48px;
  }
---

<!-- _class: lead -->

![width:300px](logo.svg)

# Building a Medical App
## What Could Go Wrong?

*Taming digital health Development*

**Antoine Duchâteau**

---

<!-- _class: lead -->

# The Startuper's Checklist ✓

**What you think you need:**

- 📱 A mobile/web app with a nice UI
- 🔐 Basic username/password login
- 💾 A database to store patient data
- ☁️ Cloud hosting (AWS, Azure, GCP)
- 🚀 Ship fast, iterate faster

**Easy, right?**

---

<!-- _class: lead -->

# Plot Twist

## Everything You've Overlooked

*Welcome to digital health development*

---

# 🔑 Advanced Login Scenarios

## Are you targetting the real world ?

---

# 🔑 Advanced Login Scenarios

**Beyond username/password:**

- **Multi-factor authentication (MFA)** - Required for healthcare professionals
- **Single Sign-On (SSO)** - Integration with hospital identity providers (SAML, OAuth)
- **Smart card authentication** - Medical professionals often use eID cards
- **Delegated access** - Temporary access for covering colleagues, emergency access

*Simple login? Not in healthcare.*

---

# 🛡️ Complex Authorization

## Everyone can see everything right ?
---

# 🛡️ Complex Authorization

**Not just "logged in" vs "logged out":**

- **Role-Based Access Control (RBAC)** - Doctors, nurses, patients, admins
- **Entity-Based Access Control (EBAC)** - Fine-grained access control to data
- **Hierarchical permissions** - Department, institution, care network levels
- **Data segmentation** - Mental health, HIV status, sensitive diagnoses

*"Can user A access resource B?" becomes incredibly complex.*

---

# 🔒 Privacy Through Encryption

## My patients data are safe, I use HTTPS

---

# 🔒 Privacy Through Encryption

**Not just HTTPS:**

- **End-to-end encryption** - Data encrypted at rest AND in transit
- **Patient-controlled keys** - Patients own their data cryptographically
- **Medical professional keys** - Each provider has unique encryption keys
- **Key exchange protocols** - Secure sharing between authorized parties
- **Zero-knowledge architecture** - Server can't decrypt patient data

*GDPR compliance requires cryptographic guarantees, not just promises.*

---

# 📚 Data Versioning

## I was sure I had saved that

---

# 📚 Data Versioning

**Medical records aren't just CRUD:**

- **Immutable audit trail** - Never delete, only append new versions
- **Complete history** - Every change, who made it, when, and why
- **Version comparison** - Diff between versions for legal/clinical purposes
- **Soft deletes** - Mark as deleted but preserve for legal retention
- **Conflicting updates** - Multiple practitioners updating simultaneously
- **Time-travel queries** - "What did we know about this patient on June 15?"

*In healthcare, the history is as important as current data.*

---

# 📋 Traceability

## Do you trust everybody ?

---

# 📋 Traceability

**Who did what, when, and why:**

- **Clinical audit logs** - Every data access and modification logged
- **User actions tracking** - Read, write, delete, export, print events
- **Chain of custody** - Complete provenance of medical data
- **Non-repudiation** - Cryptographic proof of actions taken
- **Tamper-proof logs** - Logs themselves must be immutable and verifiable
- **Legal evidence** - Audit logs must hold up in court

*If it's not logged, it didn't happen (and you're liable).* 

---

# 📊 Access Logging

## What we do not see cannot hurt us 🫣

---

# 📊 Access Logging

**Beyond traditional analytics:**

- **Healthcare-specific monitoring** - Who accessed which patient records?
- **Break-the-glass alerts** - Emergency access must be logged and justified
- **Suspicious pattern detection** - Unusual access patterns, bulk exports
- **Patient access reports** - Patients can see who viewed their data (GDPR right)
- **Regulatory reporting** - Breach notification, access reports for authorities
- **Real-time alerting** - Immediate notification of sensitive data access
- **Log retention** - Keep logs for 10-30 years depending on jurisdiction

*Privacy violations can shut you down overnight.*

---

# 🔍 Monitoring & Probing

## As long as it works, it works

---

# 🔍 Monitoring & Probing

**Healthcare SLAs are life-critical:**

- **Uptime requirements** - 99.99% isn't enough when lives depend on it
- **Outages prevention** - Minor faults detection prevents major outages
- **Performance monitoring** - Response times for critical clinical functions
- **Compliance monitoring** - Automated checks for regulatory requirements
- **Security probing** - Penetration testing, vulnerability scanning
- **Disaster recovery testing** - Regular drills, backup verification, failover tests

*Downtime in healthcare means delayed treatment or worse.*

---

# 🔗 Interoperability

## My data is in a database, what else would I need?

---

# 🔗 Interoperability

**Healthcare systems must talk to each other:**

- **Standard formats** - HL7 FHIR, CDA, DICOM for medical imaging
- **Terminology systems** - SNOMED CT, ICD-10, LOINC for lab results
- **National health networks** - Integration with eHealth platforms
- **Cross-border exchange** - European Patient Summary, IPS (International Patient Summary)
- **Laboratory integrations** - Bidirectional communication with lab systems
- **Hospital information systems** - ADT feeds, appointment scheduling

*Your app doesn't exist in isolation - it's part of a complex ecosystem.*

---

# ⚖️ Regulatory Compliance

## I read the nLPD once, I'm good

---

# ⚖️ Regulatory Compliance

**Welcome to the regulatory maze:**

- **GDPR** - European data protection (fines up to 4% of global revenue)
- **Medical Device Regulation (MDR)** - Is your app a medical device? Class I/IIa/IIb/III?
- **ISO certifications** - ISO 13485 (medical devices), ISO 27001 (security)
- **National regulations** - FDA (US), ANSM/HDS (France), national health authorities
- **Documentation requirements** - Risk management files, technical documentation
- **Post-market surveillance** - Continuous monitoring and incident reporting

*Regulatory compliance isn't a checkbox - it's an ongoing commitment.*

---

<!-- _class: lead -->

# The Reality

Building a medical app means:

🏗️ **Infrastructure** × 10 complexity  
⚖️ **Legal compliance** × 100 effort  
🔐 **Security** × 1000 diligence  

*But you're protecting the most sensitive data that exists: people's health.*

---

<!-- _class: lead -->

# Questions?

**The good news:** Solutions exist. Cardinal handle this complexity so you can focus on building great medical apps.

*Don't build it all yourself. Focus on what makes you special.*

cardinalsdk.com - ad@icure.com

**iCure certifications:** ISO 27001:2022, ISO 13485, HDS v2
