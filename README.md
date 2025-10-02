# Privacy-Impact-Assessment
PIA
# Privacy Impact Assessment (PIA) – HealthTrack App

## 📌 Project Information
- **Project Name:** HealthTrack App  
- **Date:** March 2025  
- **Prepared by:** LA-cmd-prompt (Privacy Compliance Professional)  
- **Reviewed by:** [Privacy Officer – Fictional Startup Inc.]  

---

## 1. Project Overview
**Description:**  
HealthTrack is a Canadian mobile app designed to help users track fitness and dietary data. The app collects health-related personal information (steps, calories, food logs) and, optionally, geolocation and photos.  

**Purpose:**  
- Provide users with personalized fitness insights.  
- Allow optional integration with wearable devices (Apple Watch, Fitbit).  

---

## 2. Legal and Regulatory Framework
- **Primary Law:** PIPEDA (Personal Information Protection and Electronic Documents Act).  
- **Relevant Principles:** Accountability, Consent, Limiting Collection, Safeguards, Openness, Individual Access.  
- **Provincial Considerations:** Quebec Act respecting the protection of personal information (if app expands to Quebec users).  
- **Forthcoming Reform:** Bill C-27 (CPPA) — stronger enforcement + data mobility requirements.  

---

## 3. Data Inventory

| Data Type            | Purpose                          | Sensitivity | Storage Location | Retention Period |
|----------------------|----------------------------------|-------------|-----------------|------------------|
| Email & Password     | Account creation                 | Medium      | Encrypted in AWS Canada | Until user deletes account |
| Steps & Calories     | Core functionality               | Medium      | Local device + AWS Canada | Rolling 12 months |
| Geolocation (opt-in) | Route tracking                   | High        | AWS Canada       | 30 days unless user extends |
| Food Photos (opt-in) | Diet logging                     | High        | AWS Canada       | 90 days |
| Device Info          | Debug, crash logs                | Low         | AWS Canada       | 6 months |
| Support Chat Logs    | Customer support                 | Medium      | AWS Canada       | 12 months |

---

## 4. Risk Assessment

| Risk Category         | Description | Likelihood | Impact | Mitigation |
|-----------------------|-------------|------------|--------|------------|
| Over-collection       | Collecting more health data than necessary | Medium | High | Default settings = minimal data. Extra features opt-in only. |
| Consent Clarity       | Users may not understand consent choices | Medium | High | Layered consent prompts, plain language. |
| Data Breach           | Unauthorized access to health data | Low | High | AES-256 encryption, access controls, 2FA for admin. |
| Retention Creep       | Data stored longer than needed | Medium | Medium | Auto-deletion after 12 months inactivity. |
| Cross-Border Transfer | Risk if using non-Canadian servers | Low | High | Store data exclusively in Canada (AWS Canada). |

---

## 5. Mitigation Strategies
- **Minimization:** Collect only essential data by default.  
- **Transparency:** Clear consent prompts and plain-language privacy policy.  
- **Security:** End-to-end encryption (TLS in transit, AES-256 at rest).  
- **Retention Controls:** Automated deletion scripts tied to retention schedule.  
- **User Rights:** In-app options to download or delete all data.  
- **Vendor Management:** Contracts with cloud vendors include PIPEDA-compliant Data Processing Agreements (DPAs).  

---

## 6. Privacy by Design Integration
- Privacy embedded into **design sprints** (privacy sign-off required before feature release).  
- Optional features **OFF by default**.  
- Privacy team participates in **threat modeling** with engineers.  
- User-friendly **settings & consent dashboards** built into app.  

---

## 7. Residual Risks
Despite mitigation, residual risks include:  
- User misunderstanding of consent prompts (to be reduced via A/B testing of wording).  
- Potential re-identification of anonymized datasets if combined with external sources (to be mitigated with differential privacy techniques in future).  

---

## 8. Recommendations
- Conduct annual privacy audit of HealthTrack systems.  
- Update privacy notices in line with **Bill C-27** once enacted.  
- Engage third-party penetration testing annually.  
- Establish formal breach response tabletop exercises with staff.  

---

## ✅ Sign-Off
- **Project Owner:** [Fictional Startup Inc. CTO]  
- **Privacy Lead:** LA-cmd-prompt (Privacy Compliance Professional)  
- **Date Approved:** March 2025  
