# gcp-vm-troubleshooting-lab
Hands on GCP project simulating common cloud support incidents involving SSH, firewall rules, and IAM permissions.

# GCP VM Troubleshooting Lab

## Overview
This project was created to practice basic cloud support skills using Google Cloud Platform (GCP).  
I deployed a Linux virtual machine and then intentionally caused common problems that a technical support engineer might face, such as SSH connection issues and permission errors.

The goal of this lab was to learn how to troubleshoot cloud infrastructure issues step by step and understand how networking and access control work in GCP.

---

## What I Used
- Google Cloud Platform (GCP)
- Compute Engine (Virtual Machines)
- VPC Firewall Rules
- IAM (Identity and Access Management)
- Ubuntu Linux

---

## Scenario 1: SSH Connection Not Working

**What happened:**  
After creating the virtual machine, SSH access suddenly stopped working.

**What I noticed:**
- The VM was running
- SSH attempts were timing out
- SSH had worked earlier before the issue occurred

**What caused it:**  
A firewall rule was created that denied traffic on TCP port 22 (SSH).  
Because deny rules with higher priority override allow rules in GCP, SSH traffic was blocked.

**How I fixed it:**  
I reviewed the firewall rules, identified the deny rule, and removed it.  
After that, SSH access worked again.

**What I learned:**  
Firewall rule priority is very important, and deny rules can easily block access if not configured carefully.

---

## Scenario 2: Permission Denied Error (IAM Issue)

**What happened:**  
I was unable to view or manage the VM from the GCP console.

**What I noticed:**
- Permission denied errors appeared
- The VM itself was still running normally

**What caused it:**  
The user account was missing the required IAM role to access Compute Engine resources.

**How I fixed it:**  
I added the correct Compute Engine role to the user account while following least-privilege principles.

**What I learned:**  
Many cloud access issues are caused by IAM misconfigurations rather than system failures.

---

## Key Takeaways
- Learned how to deploy and manage a virtual machine in GCP
- Gained hands-on experience troubleshooting firewall and IAM issues
- Practiced thinking through problems like a technical support engineer
- Improved my ability to explain technical issues clearly and simply

---

## Screenshots
Screenshots showing the VM setup, errors, and fixes are included in the `screenshots` folder.
