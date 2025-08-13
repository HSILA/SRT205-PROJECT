# CIS Ubuntu Task Examples

1. **Ensure Password Expiration is Set – Enforce Password Rotation via /etc/login.defs**  
  - **Description**: Configures password expiration settings to force users to change passwords periodically.
  - **Importance**: Reduces the risk of compromised credentials being exploited indefinitely.
  - **Considerations**: Ensure users are notified before expiration. CIS benchmarks recommend setting a maximum password age and enforcing history.
  - **CIS Reference**: Section 5.4.1.1 - Ensure password expiration is configured.

2. **Disable Root Login Over SSH**  
  - **Description**: Prevents direct root login via SSH to reduce attack vectors.
  - **Importance**: Enhances security by enforcing non-root user access and privilege escalation.
  - **Considerations**: Ensure at least one sudo-enabled user exists before implementing. 
  - **CIS Reference**: Section 5.1.20 - Ensure sshd PermitRootLogin is disabled.

3. **Ensure ptrace_scope is Restricted**  
  - **Description**: Restricts the use of the `ptrace` system call, which allows one process to attach to and manipulate another.
  - **Importance**: Prevents compromised applications from attaching to other running processes and extracting sensitive data.
  - **Considerations**: Debugging tools such as `gdb` and `strace` rely on `ptrace`, so ensure developers have the necessary privileges.
  - **CIS Reference**: Section 1.5.2 - Ensure ptrace_scope is restricted【50:0†CIS_Ubuntu_Linux_22.04_LTS_Benchmark_v2.0.0.pdf】.

4. **Configure Automatic Security Updates**  
  - **Description**: Ensures security updates are automatically applied.
  - **Importance**: Reduces risk of known vulnerabilities being exploited.
  - **Considerations**: Ensure updates do not break critical applications.
  - **CIS Reference**: Section 1.2.2.1 - Ensure updates, patches, and additional security software are installed.

5. **Ensure Firewall is Enabled and Configured**  
  - **Description**: Enables and configures `ufw` (Uncomplicated Firewall) to filter network traffic.
  - **Importance**: Reduces attack surface by blocking unauthorized access.
  - **Considerations**: Ensure required services (e.g., SSH) are allowed.
  - **CIS Reference**: Section 4.1.3 - Ensure ufw service is enabled.

6. **Configure Client Services**  
  - **Description**: Ensures that unnecessary or insecure client services are not installed on the system.
  - **Importance**: Disabling or removing unused client services reduces the attack surface and mitigates potential vulnerabilities.
  - **Considerations**: Some client services may be required for specific applications, so ensure dependencies are considered before removal.
  - **CIS Reference**: Section 2.2 - Configure Client Services.

7. **Restrict Access to Cron Jobs**  
  - **Description**: Limits cron job access to authorized users.
  - **Importance**: Prevents unauthorized task scheduling.
  - **Considerations**: Ensure required jobs remain accessible to necessary users.
  - **CIS Reference**: Section 2.4.1.8 - Ensure crontab is restricted to authorized users.

8. **Ensure /tmp is Mounted with noexec and nosuid**  
  - **Description**: Prevents execution of binaries in `/tmp`.
  - **Importance**: Mitigates execution of malicious scripts.
  - **Considerations**: Ensure compatibility with legitimate processes.
  - **CIS Reference**: Section 1.1.2.1.3 & 1.1.2.1.4 - Ensure nosuid & noexec option set on /tmp partition.

9. **Enforce Strong Password Policies**  
  - **Description**: Enforces password complexity requirements.
  - **Importance**: Reduces risk of weak passwords being compromised.
  - **Considerations**: Ensure users are aware of new policies.
  - **CIS Reference**: Section 5.3.3.2 - Ensure password complexity is configured.

10. **Disable IPv6 If Not Needed**  
  - **Description**: Disables IPv6 if the environment does not require it.
  - **Importance**: Reduces attack vectors related to IPv6.
  - **Considerations**: Ensure it is not required for network services.
  - **CIS Reference**: Section 3.1.1 - Ensure IPv6 status is identified.

11. **Ensure a Single Time Synchronization Daemon is in Use**  
  - **Description**: Ensures that only one time synchronization daemon (either `chrony` or `systemd-timesyncd`) is active on the system.
  - **Importance**: Prevents conflicts and ensures reliable time synchronization, which is crucial for security mechanisms and forensic investigations.
  - **Considerations**: If running in a virtualized environment, verify whether host-based time synchronization is being used before applying changes.
  - **CIS Reference**: Section 2.3.1.1 - Ensure a single time synchronization daemon is in use.

12. **Ensure sudoers file is properly configured**  
  - **Description**: Ensures only authorized users can execute administrative commands.
  - **Importance**: Prevents privilege escalation through misconfigured sudo permissions.
  - **Considerations**: Audit sudoers file for excessive privileges.
  - **CIS Reference**: Section 5.2.3 - Ensure sudo log file exists.

13. **Ensure Password Failed Attempts Lockout and unlock time is Configured**  
  - **Description**: Configures the system to lock user accounts after a defined number of failed login attempts.
  - **Importance**: Helps mitigate brute force attacks by preventing unlimited authentication attempts.
  - **Considerations**: Setting the lockout threshold too low may lead to legitimate users getting locked out frequently, causing administrative overhead.
  - **CIS Reference**: Section 5.3.3.1.1 & 5.3.3.1.2 - Ensure Password Failed Attempts Lockout and unlock time is Configured.

14. **Ensure AppArmor is Installed and Enforced**  
  - **Description**: Enforces mandatory access control policies.
  - **Importance**: Provides an additional layer of security.
  - **Considerations**: Ensure required services are not blocked unintentionally.
  - **CIS Reference**: Section 1.3.1.1 - Ensure AppArmor is installed.

15. **Ensure at is Restricted to Authorized Users**
  - **Description**: Limits at command access to authorized users.
  - **Importance**: Prevents unauthorized scheduling of tasks.
  - **Considerations**: Ensure required jobs remain accessible to necessary users.
  - **CIS Reference**: Section 2.4.2 - Ensure at is restricted to authorized users.

16. **Ensure System Integrity is Regularly Checked**  
  - **Description**: Uses tools like AIDE to detect unauthorized modifications.
  - **Importance**: Helps identify potential security breaches.
  - **Considerations**: Schedule integrity checks appropriately.
  - **CIS Reference**: Section 6.1.1 & 6.1.2 - Ensure filesystem integrity is regularly checked.

17. **Restrict Access to Sensitive Files and Directories**  
  - **Description**: Prevents unauthorized users from accessing security-sensitive files.
  - **Importance**: Reduces the risk of credential or key exposure.
  - **Considerations**: Ensure legitimate access is maintained.
  - **CIS Reference**: Section 7.1 - System File Permissions.

18. **Enable System-Wide ASLR**  
  - **Description**: Protects against memory corruption attacks.
  - **Importance**: Increases security against buffer overflow exploits.
  - **Considerations**: Verify compatibility with legacy applications.
  - **CIS Reference**: Section 1.5.1 - Ensure address space layout randomization is enabled.

19. **Configure auditd Service**  
  - **Description**: Ensures auditd is installed and enabled.
  - **Importance**: Maintains system forensic capabilities.
  - **Considerations**: Also consider implementations listed in the rest of 6.3.
  - **CIS Reference**: Section 6.3.2 - Configure auditd Service.

20. **Ensure SSH Idle Timeout is Set**  
  - **Description**: Terminates inactive SSH sessions automatically.
  - **Importance**: Reduces risk of unattended active sessions.
  - **Considerations**: Balance security with usability.
  - **CIS Reference**: Section 5.1.7 - Ensure sshd ClientAliveInterval and ClientAliveCountMax are configured.