
# MEDIROZA GENERAL HOSPITAL
# Penetration Testing & Vulnerability Assessment Report

**Organization:** Networkwalks  
**Batch:** B083  
**Project:** Week 4 — Penetration Testing  
**Client:** Mediroza General Hospital  
**Target:** https://medirozahospital.com  
**Assessment Type:** Black-Box Web Application Penetration Testing  
**Duration:** 5 Days  
**Report Date:** 08 October 2026  
**Prepared By:** [Your Name]

---

# 1. EXECUTIVE SUMMARY

This penetration testing assessment was conducted as part of the Networkwalks Week 4 cybersecurity project.

The objective was to evaluate the security of the Mediroza General Hospital web application, identify vulnerabilities, assess their potential impact, and recommend appropriate remediation measures.

The engagement focused on the hospital's patient portal, authentication mechanisms, protected pathology documents, PDF security controls, and exposed server resources.

During the assessment, several security weaknesses were identified, including:

- Publicly accessible SQL database backup.
- Directory listing enabled on a legacy server directory.
- Disclosure of internal server information through PDF metadata.
- Verbose SQL error messages exposed through the login interface.
- Distinguishable authentication error responses.
- Recoverable passwords protecting confidential patient PDF reports.
- Exposure of sensitive employee and shareholder information.

The most significant finding was a publicly accessible SQL database backup containing confidential hospital information.

The backup contained 30 employee records and 10 shareholder records, demonstrating a serious confidentiality risk.

**Overall Security Risk: CRITICAL**

The hospital should prioritize restricting public access to database backups, securing confidential documents, strengthening authentication controls, and reviewing its data-protection practices.

---

# 2. SCOPE AND METHODOLOGY

## 2.1 Scope of Assessment

The penetration testing exercise focused on the following authorized target:

**Target Domain:** https://medirozahospital.com

The engagement was conducted as a black-box penetration test, meaning that the assessment began without privileged knowledge of the application's internal architecture.

The project brief specified the following testing restrictions:

- Testing limited to the authorized target.
- No social engineering.
- No denial-of-service attacks.
- No testing outside the agreed scope.
- Documentation of discovered vulnerabilities and their security impact.

## 2.2 Penetration Testing Methodology

The assessment followed these stages:

1. Reconnaissance and information gathering.
2. Web application enumeration.
3. Authentication behavior analysis.
4. Vulnerability identification.
5. Controlled validation of security weaknesses.
6. PDF password recovery and document analysis.
7. Metadata examination.
8. Sensitive data exposure assessment.
9. Risk classification.
10. Reporting and remediation recommendations.

## 2.3 Tools Used

| S/N | Tool | Function |
|---|---|---|
| 1 | Kali Linux | Security testing environment |
| 2 | WHOIS | Domain registration information gathering |
| 3 | WhatWeb | Website technology identification |
| 4 | NSLookup | DNS record enumeration |
| 5 | cURL | HTTP response and header inspection |
| 6 | WafW00f | Web application firewall detection |
| 7 | DNSRecon | DNS reconnaissance |
| 8 | Gobuster | Web directory enumeration |
| 9 | Web Browser | Application interaction and response inspection |
| 10 | Wget | HTTP resource retrieval and response validation |
| 11 | ExifTool | PDF metadata analysis |
| 12 | John the Ripper / Password Recovery Tools | Password recovery assessment |
| 13 | QPDF | PDF decryption and document inspection |
| 14 | Grep | Local SQL file structure inspection |

---

# 3. PROJECT MILESTONES

The project consisted of four major milestones.

| Milestone | Objective | Outcome |
|---|---|---|
| M1 | Access the patient portal and retrieve three confidential PDF reports | Three encrypted reports obtained |
| M2 | Recover the contents of the three protected PDF files | All three documents recovered |
| M3 | Identify exposed employee salary and shareholder information | SQL database exposure confirmed |
| M4 | Prepare a professional penetration testing report | Completed |

---

# 4. MILESTONE 1 — INITIAL ACCESS

## 4.1 Objective

The objective of Milestone 1 was to assess the hospital website, identify weaknesses in its authentication mechanisms, and retrieve three protected patient PDF laboratory reports.

## 4.2 Reconnaissance

Initial reconnaissance was performed to gather information about the target website.

The reconnaissance activities included:

- Domain registration investigation.
- DNS enumeration.
- Web server identification.
- HTTP response inspection.
- Web application firewall detection.
- Directory and resource enumeration.
- Examination of accessible authentication pages.

The reconnaissance identified LiteSpeed web server technology and the Mediroza CMS application.

These observations provided useful context for subsequent application security testing.

## 4.3 Authentication Testing

The hospital's patient login interface was examined to understand its behavior when processing authentication requests.

Testing revealed that the application displayed different responses depending on the submitted authentication information.

Observed responses included:

- Username not found.
- Incorrect password.
- Database syntax error messages.

These responses revealed information about the application's authentication behavior.

## 4.4 SQL Error Disclosure

During authentication testing, the application displayed a raw database error containing MySQL and `mysqli_query()` information.

This behavior indicates that internal database error details were being returned to the user interface.

Such error messages can reveal application implementation details and assist an attacker in understanding database interactions.

**Finding:** Verbose SQL error disclosure.

**Severity:** Medium.

**Important:** The observed database error does not independently prove successful SQL injection or authentication bypass.

## 4.5 Patient Portal Access

The supplied assessment evidence showed access to a patient portal containing three encrypted pathology PDF reports.

The reports were subsequently obtained for the authorized security assessment.

The evidence confirms the availability and retrieval of the documents, although the exact initial authentication-bypass mechanism is not fully established by the screenshots.

## 4.6 Milestone 1 Outcome

The following objectives were demonstrated:

- Patient login interface identified.
- Authentication responses examined.
- SQL error disclosure observed.
- Patient portal access documented.
- Three encrypted PDF reports retrieved.

**Milestone 1: Document retrieval objective achieved.**

---

# 5. MILESTONE 2 — PDF PASSWORD RECOVERY

## 5.1 Objective

The objective of Milestone 2 was to analyze the encryption protecting the three retrieved pathology reports and recover their readable contents.

## 5.2 PDF Security Analysis

The three PDF files were examined to identify their password-protection characteristics.

The assessment involved:

- Identifying password-protected documents.
- Extracting password-verification information.
- Examining supported password recovery methods.
- Testing wordlists against the protected documents.
- Validating recovered passwords.
- Opening the decrypted reports.
- Examining document metadata.

## 5.3 PDF 1 — Password Recovery

The first protected pathology report was analyzed using password recovery tools.

The supplied screenshots documented a successful password recovery result.

Following recovery, the document was opened and its contents became readable.

**Result:** Password successfully recovered.

**Status:** Completed.

## 5.4 PDF 2 — Password Recovery

The second PDF underwent a similar analysis.

Password recovery was performed using the available recovery tools and wordlists.

The supplied screenshots demonstrated successful recovery and subsequent access to the document.

**Result:** Password successfully recovered.

**Status:** Completed.

## 5.5 PDF 3 — Password Recovery

The third protected PDF required additional password recovery attempts.

The initial wordlist did not produce a successful match.

A larger wordlist was subsequently used, and the supplied screenshots documented successful password recovery.

The report was then opened successfully.

**Result:** Password successfully recovered.

**Status:** Completed.

## 5.6 Security Implications

The successful recovery of passwords protecting all three supplied PDF reports demonstrates weaknesses in the password protection used for those documents.

Potential security risks include:

- Unauthorized disclosure of confidential patient information.
- Exposure of sensitive medical records.
- Loss of patient privacy.
- Increased risk when protected files are accessible to unauthorized parties.

The results establish recoverability for the three tested documents, not necessarily for every PDF generated by the hospital.

## 5.7 Milestone 2 Outcome

All three protected PDF reports were successfully recovered and opened.

| Document | Password Recovery | Document Access |
|---|---|---|
| PDF 1 | Successful | Confirmed |
| PDF 2 | Successful | Confirmed |
| PDF 3 | Successful | Confirmed |

**Milestone 2: Completed.**

---

# 6. MILESTONE 3 — CRITICAL DATA EXPOSURE

## 6.1 Objective

The objective of Milestone 3 was to identify critical data exposure on the hospital server and determine whether confidential employee salary and shareholder information could be accessed.

## 6.2 PDF Metadata Investigation

Following successful recovery of the protected PDF reports, metadata analysis was performed using ExifTool.

The analysis identified document properties including:

- Author information.
- Document creator.
- PDF producer.
- Document title.
- Subject.
- Keywords.
- Internal comments.

The third PDF contained an internal comment referring to a database backup stored in a legacy server directory.

This disclosed internal operational information that should not have been included in a publicly distributed document.

**Finding:** Operational metadata disclosure.

**Severity:** Low.

## 6.3 Legacy Directory Exposure

The metadata clue led to examination of a legacy website directory.

The directory displayed an index of its contents, including a database backup filename.

This confirmed that directory listing was enabled and exposed information about server-side resources.

**Finding:** Legacy directory indexing.

**Severity:** Medium.

Directory listing can reveal filenames, application resources, and forgotten backup files.

Disabling directory listing alone is insufficient if sensitive files remain directly accessible.

## 6.4 SQL Database Backup Exposure

Further assessment confirmed that the SQL backup could be retrieved through a normal HTTPS request.

The server returned:

- HTTP Status: 200 OK.
- Content Type: text/x-sql.
- File Size: 6,346 bytes.
- Download Status: Successful.

The backup was subsequently examined locally.

**Finding:** Publicly accessible SQL database backup.

**Severity:** Critical.

This vulnerability allowed confidential information stored within the backup to be exposed without the intended access restrictions.

## 6.5 Database Structure Analysis

The SQL backup contained two principal tables:

```sql
CREATE TABLE `staff` (...);

CREATE TABLE `shareholders` (...);
```

The table structures and associated records were examined locally.

### Staff Table

The staff table contained 30 employee records.

Identified data categories included:

- Employee names.
- Job titles.
- Departments.
- Email addresses.
- Telephone numbers.
- National identification numbers.
- Monthly salaries.
- Employment dates.

The salary field was stored as `monthly_salary_zar`, indicating monthly salary values denominated in South African rand.

### Shareholders Table

The shareholders table contained 10 records.

Identified data categories included:

- Shareholder names.
- Ownership percentages.
- Number of shares held.
- Share classes.

The supplied records represented a total of 1,000,000 shares and ownership percentages totaling 100%.

## 6.6 Confidential Data Exposure Summary

| Data Category | Records Identified | Security Impact |
|---|---:|---|
| Employee information | 30 | Exposure of personal and employment data |
| Employee salaries | 30 staff records | Exposure of confidential financial information |
| Shareholder information | 10 | Exposure of ownership information |
| Total shares represented | 1,000,000 | Disclosure of corporate ownership structure |

The exposure of these records is a consequence of the publicly accessible database backup rather than a separate exploitation technique.

## 6.7 Security Impact

The exposed SQL database backup could result in:

- Unauthorized disclosure of employee information.
- Exposure of confidential salary records.
- Disclosure of government identification information.
- Exposure of shareholder ownership details.
- Privacy and regulatory compliance concerns.
- Reputational and operational damage.

## 6.8 Milestone 3 Outcome

The assessment successfully established the following:

1. PDF metadata disclosed an internal backup-location clue.
2. A legacy directory exposed a database backup filename.
3. The database backup was publicly downloadable.
4. Staff and shareholder tables were identified.
5. Thirty employee records were confirmed.
6. Ten shareholder records were confirmed.
7. Confidential salary and ownership information was present.

**Milestone 3: Completed.**

---

# 7. TECHNICAL FINDINGS AND RISK RATINGS

The following findings were established from the supplied assessment evidence.

| Finding ID | Vulnerability | Severity | Assessment |
|---|---|---|---|
| F-01 | Publicly Accessible SQL Database Backup | Critical | Confirmed |
| F-02 | Legacy Directory Indexing | Medium | Confirmed |
| F-03 | Operational Metadata Disclosure | Low | Confirmed |
| F-04 | Verbose Database Error Disclosure | Medium | Error confirmed; SQL injection unproven |
| F-05 | Distinguishable Authentication Responses | Low | Observed; enumeration not fully verified |
| F-06 | Recoverable PDF Password Protection | High | Confirmed for three reports |
| F-07 | Confidential Staff and Shareholder Data Exposure | High Impact | Confirmed consequence of F-01 |

## 7.1 Critical Risk

A Critical rating was assigned to the publicly accessible SQL database backup because it exposed sensitive employee and corporate information without appropriate access restrictions.

## 7.2 High Risk

A High rating was assigned to the recoverable PDF passwords because successful password recovery enabled access to confidential patient documents.

The exposure of staff and shareholder information also represents a high-impact confidentiality consequence of the database backup vulnerability.

## 7.3 Medium Risk

Medium-risk findings included:

- Directory listing enabled on a legacy server directory.
- Raw database errors exposed through the authentication interface.

## 7.4 Low Risk

Low-risk findings included:

- Internal operational information disclosed through PDF metadata.
- Authentication responses that may reveal account-existence information.

These ratings are qualitative assessments rather than calculated CVSS scores.

---

# 8. RECOMMENDATIONS AND REMEDIATION

Based on the identified vulnerabilities, the following security improvements are recommended.

## 8.1 Secure Database Backups

**Priority: Immediate**

- Remove database backups from publicly accessible directories.
- Store backups outside the website document root.
- Encrypt sensitive backup files.
- Restrict backup access to authorized administrators.
- Review server logs for unauthorized access.
- Investigate whether exposed records require breach notification.
- Verify that backup URLs cannot be accessed anonymously.

## 8.2 Disable Directory Listing

**Priority: Medium**

- Disable automatic directory indexing.
- Audit legacy and migration directories.
- Remove obsolete application files.
- Restrict direct access to backup file extensions.
- Regularly review publicly accessible server resources.

## 8.3 Improve Authentication Security

**Priority: High**

- Use secure, parameterized database queries.
- Validate user input appropriately.
- Avoid exposing internal database errors.
- Use generic authentication failure messages.
- Implement rate limiting.
- Monitor repeated failed authentication attempts.
- Enforce strong session management and access controls.

## 8.4 Strengthen PDF Security

**Priority: High**

- Use strong, unique passwords for protected documents.
- Avoid predictable or commonly used passwords.
- Use secure methods to distribute document access credentials.
- Review document access authorization.
- Consider authenticated document delivery instead of relying only on PDF passwords.
- Regularly assess document protection controls.

## 8.5 Remove Sensitive PDF Metadata

**Priority: Medium**

- Remove unnecessary author and operational comments.
- Avoid embedding internal server paths in documents.
- Review document metadata before publication.
- Implement automated metadata inspection.
- Ensure document-generation systems do not disclose internal infrastructure details.

## 8.6 Improve Sensitive Data Protection

**Priority: High**

- Apply least-privilege access controls.
- Protect employee and shareholder information.
- Encrypt sensitive data where appropriate.
- Review data retention policies.
- Monitor access to confidential records.
- Conduct periodic security assessments.

## 8.7 Conduct Security Retesting

After implementing the recommended fixes, the hospital should conduct a follow-up security assessment.

The retest should verify that:

- SQL backups are no longer publicly accessible.
- Legacy directories no longer expose sensitive resources.
- Authentication errors no longer reveal database details.
- Confidential PDF reports are protected appropriately.
- Sensitive information cannot be retrieved without authorization.

---

# 9. CONCLUSION

The Mediroza General Hospital penetration testing exercise identified significant weaknesses in the security of the hospital's web application and associated document-handling processes.

The assessment demonstrated access to three protected pathology PDF reports and successful recovery of their contents.

Further analysis of PDF metadata revealed information that assisted in identifying a publicly accessible database backup.

The database backup contained confidential employee salary information and shareholder ownership records.

The most serious finding was the exposure of sensitive data through a web-accessible SQL backup, representing a Critical security risk.

Additional weaknesses included directory indexing, operational metadata disclosure, verbose database errors, and recoverable document passwords.

These findings demonstrate the importance of implementing strong authentication controls, securing backup storage, protecting confidential documents, and preventing unnecessary disclosure of internal application information.

The hospital should prioritize remediation of the Critical and High-risk findings and perform follow-up testing to confirm that corrective actions are effective.

**Overall Assessment: CRITICAL RISK**

The engagement fulfilled the principal technical objectives of the Networkwalks Week 4 penetration testing project and documented actionable security improvements.

---

# 10. PROJECT COMPLETION SUMMARY

| Milestone | Description | Status |
|---|---|---|
| M1 | Initial Access and PDF Retrieval | Completed |
| M2 | PDF Password Recovery | Completed |
| M3 | Sensitive Database Exposure Assessment | Completed |
| M4 | Penetration Testing Report | Completed |

---

## PROJECT INFORMATION

**Project:** Mediroza General Hospital Penetration Testing  
**Training Organization:** Networkwalks  
**Batch:** B083  
**Week:** 4  
**Operating System:** Kali Linux  
**Assessment Type:** Black-Box Web Application Security Testing  

---

## DISCLAIMER

This penetration testing project was conducted for authorized educational security assessment purposes.

The findings presented in this README are based on evidence collected during the training exercise.

Confidential patient information, employee identification details, individual salary records, recovered passwords, and sensitive database contents have intentionally been excluded from this public documentation.

All security testing must be performed only against systems for which explicit authorization has been granted.

---

**END OF PENETRATION TESTING REPORT**

