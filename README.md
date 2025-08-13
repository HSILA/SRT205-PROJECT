# **SRT205 Automation Project**

---

## **Overview of CIS Compliance**

The **Center for Internet Security (CIS)** provides best practices for securing systems against cyber threats. These **CIS benchmarks** help organizations improve their security posture by ensuring that systems are securely configured to reduce vulnerabilities and exposure to attacks.

### **Why is CIS Compliance Important?**

- **Enhanced Security** – Reduces attack surfaces by applying secure configurations.
- **Industry Standards** – Aligns with security frameworks and regulatory requirements.
- **Risk Reduction** – Minimizes security misconfigurations and improves resilience.
- **Audit & Compliance Readiness** – Facilitates security audits and regulatory compliance.

---

## **Project Objective**

This project utilizes **Ansible** to automate **CIS compliance tasks** on **Windows, Ubuntu, and Amazon Linux 2 systems**. Students will:

- Develop **Ansible Playbooks** to implement security controls.
- Structure configurations using **Ansible Roles**.
- Secure sensitive data using **Ansible Vault**.
- Generate **dynamic compliance reports** using **Jinja2**.
- Implement **error handling mechanisms** for reliability.
- **Utilize GitHub** for collaboration and version control.

---

## **Project Deliverables**

### **1️⃣ CIS Compliance Implementation**

- Implement **at least 10 CIS compliance tasks** for each assigned operating system.
- Ensure configurations follow **Ansible best practices**.

### **2️⃣ Modular Ansible Role Implementation**

- Organize automation tasks into **Ansible Roles**:
  - `cis_ubuntu`: Manages CIS compliance for Ubuntu.
  - `cis_windows`: Manages CIS compliance for Windows.
  - `cis_amazon`: Manages CIS compliance for Amazon Linux 2. (**for 4 member team only**)
  - `audit_compliance`: Implements security auditing and reporting.

### **3️⃣ Secure Credential Management**

- Use **Ansible Vault** to protect sensitive credentials (e.g., SSH keys, passwords).

### **4️⃣ Automated Compliance Reporting**

- Use **Jinja2 templates** to generate **dynamic compliance reports**.

### **5️⃣ Complete Playbook Execution**

- Develop a **main playbook (`main.yml`)** that integrates all roles.

### **6️⃣ Robust Error Handling**

- Implement mechanisms like `assert`, `fail`, `block`, and `rescue` for fault tolerance.

### **7️⃣ Version Control & Documentation**

- Maintain a well-structured **GitHub repository**:
  - Meaningful **commit messages**.
  - Organized **project directory**.
  - Clear **README.md documentation** with setup and execution instructions.

### **8️⃣ Final Project Presentation**

- Deliver a **10-minute presentation** detailed in [Presentation_Instruction](Presentation_Instruction.md)

---

## **Work Options: Individual or Team-Based**

Students may complete this project **individually** or as part of a **team (up to 4 members)**.

### **Option 1: Team Collaboration (Recommended)**

Each team member will take on a specialized role:

- **Ubuntu Specialist**: Develops the `cis_ubuntu` role.
- **Windows Specialist**: Develops the `cis_windows` role.
- **Amazon Linux 2 Specialist**: Develops the `cis_amazon` role. (**for 4 member team only**)
- **Team Lead**: Manages `audit_compliance`, security reporting, and project coordination.

### **Option 2: Individual Work**

If working alone, the student must:

- Select **one OS role** (`cis_ubuntu`, `cis_windows`, or `cis_amazon`).
- Develop and test the **`audit_compliance` role**.
- Provide a **detailed final report**.
- Ensure all deliverables meet security and best practice standards.

---

## **Grading Rubric (22% of Total Course Grade)**

| **Criteria**                         | **Weight**        | **Details**                                                        |
| ------------------------------------ | ----------------- | ------------------------------------------------------------------ |
| **CIS Compliance Implementation**    | 20% + (Bonus 10%) | Secure configurations for Ubuntu, Windows, and Amazon Linux 2.     |
| **Ansible Role Structure**           | 15%               | Proper modularization and well-structured tasks.                   |
| **Security Best Practices**          | 10%               | Use of Ansible Vault to secure sensitive information.              |
| **Automated Compliance Reporting**   | 10%               | Jinja2-generated reports for CIS compliance.                       |
| **Error Handling & Debugging**       | 15%               | Use of structured error handling techniques.                       |
| **GitHub Collaboration & Structure** | 15%               | Organized repository, meaningful commits, and clear documentation. |
| **Final Presentation**               | 15%               | Clear, structured, and effective communication of the project.     |

---

## **Submission Guidelines**

### **📌 Required Submissions**

1. **GitHub Repository** – Submit the repository URL with:

   - **README.md** with project details and execution instructions.
   - Well-structured **Ansible roles and playbooks**.
   - **Meaningful commit messages** to track progress.

2. **Screenshots & Evidence**:

   - Execution logs of playbooks.
   - Generated **compliance reports**.
   - Commit history for tracking development.

3. **Final Presentation**:
   - A **10-minute presentation** that covers:
     - **Project design & implementation**.
     - **Demonstration of playbook execution**.
     - **Challenges encountered & solutions applied**.
     - **Lessons learned & possible improvements**.

---

## **Why This Project Matters**

This project provides **hands-on experience** with **Ansible in a cybersecurity context**, fostering:

✅ **Automation skills for security compliance**.  
✅ **Experience securing IT infrastructure**.  
✅ **Collaboration and version control best practices**.  
✅ **Technical documentation and reporting abilities**.
