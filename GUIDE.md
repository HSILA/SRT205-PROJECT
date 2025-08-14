# Project Guide

This repository contains an Ansible-based approach for applying a subset of CIS hardening controls to Ubuntu and Windows hosts.

## Checklist Overview

- **Ansible Roles**: `cis_ubuntu`, `cis_windows`, and `audit_compliance`.
- **CIS Controls**: Example tasks including password policies, SSH hardening, automatic updates, and firewall configuration.
- **Reporting**: The `audit_compliance` role generates a simple text report summarizing task outcomes for each host.

## Approach

1. **Role-Based Structure**: Each operating system has its own role with idempotent tasks that configure CIS recommendations.
2. **Result Aggregation**: Roles publish their results as facts which are merged by `audit_compliance` to build a report using a Jinja2 template.
3. **Extensibility**: Additional CIS controls can be added by appending tasks to the respective role and updating the results dictionary.

## Running the Playbook

1. Copy `inventory.example.ini` to `inventory.ini` and update it with the addresses and credentials of your test VMs. Use Ansible Vault to store any sensitive information.
2. Execute the playbook:

   ```bash
   ansible-playbook -i inventory.ini main.yml
   ```

3. After execution, a `compliance_report_<hostname>.txt` file will be created in the playbook directory for each host.

## Testing

- **Syntax Check**:

  ```bash
  ansible-playbook --syntax-check -i inventory.ini main.yml
  ```

- **Dry Run**:

  ```bash
  ansible-playbook -i inventory.ini main.yml --check
  ```

These steps help verify that tasks are structured correctly before applying changes to target machines.
