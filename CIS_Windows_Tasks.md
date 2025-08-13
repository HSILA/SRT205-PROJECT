# CIS Task Examples

1. **Enforce Password History – Prevent Reuse of Previous Passwords**

   - **Description**: Configures Windows to remember the last 24 passwords used to prevent reuse.
   - **Importance**: Reduces the risk of credential compromise by preventing users from cycling through old passwords.
   - **Considerations**: Ensure minimum password age is configured to prevent rapid password changes.
   - **CIS Reference**: Section 1.1.1 - Set 'Enforce password history' to '24 or more password(s)'.

2. **Set Maximum Password Age – Force Regular Password Changes**

   - **Description**: Requires users to change their passwords every 60 days or less.
   - **Importance**: Prevents long-term use of potentially compromised passwords.
   - **Considerations**: Ensure users are notified before password expiration.
   - **CIS Reference**: Section 1.1.2 - Set 'Maximum password age' to '60 or fewer days'.

3. **Disable Root Login Over Remote Desktop**

   - **Description**: Restricts remote access for the built-in Administrator account.
   - **Importance**: Prevents direct remote access to highly privileged accounts.
   - **Considerations**: Ensure another administrative account is available for remote access.
   - **CIS Reference**: Section 2.2.7 - Set 'Allow log on through Remote Desktop Services' to 'Administrators' only.

4. **Configure Account Lockout Policy**

   - **Description**: Locks user accounts after a number of failed login attempts to prevent brute-force attacks.
   - **Importance**: Helps mitigate unauthorized access attempts.
   - **Considerations**: Set lockout threshold appropriately to balance security and usability.
   - **CIS Reference**: Section 1.2.2 - Set 'Account lockout threshold' to '5 or fewer invalid attempts'.

5. **Set 'Windows Firewall: Private: Outbound connections' to 'Allow (default)'**

   - **Description**: Configures the firewall to allow all outbound connections unless explicitly blocked.
   - **Importance**: Ensures that legitimate outbound traffic is not unintentionally restricted.
   - **Considerations**: Review firewall rules to ensure necessary security policies are in place while allowing essential outbound connections.
   - **CIS Reference**: Section 9.2.3 - Set 'Windows Firewall: Private: Outbound connections' to 'Allow (default)'.

6. **Set 'Reset account lockout counter after' to '15 or more minute(s)'**

   - **Description**: Configures the system to reset the account lockout counter after a specified time.
   - **Importance**: Prevents potential brute-force attacks while ensuring legitimate users are not locked out indefinitely.
   - **Considerations**: Ensure the value aligns with organizational security policies and user convenience.
   - **CIS Reference**: Section 1.2.3 - Set 'Reset account lockout counter after' to '15 or more minute(s)'.

7. **Enable Time Synchronization with a Reliable NTP Server**

   - **Description**: Configures Windows to sync time with a trusted external time server.
   - **Importance**: Ensures accurate timestamps for logging and authentication.
   - **Considerations**: Use a domain controller or an external time server.
   - **CIS Reference**: Section 2.2.9 - Change the system time.

8. **Set 'Accounts: Limit local account use of blank passwords to console logon only' to 'Enabled'**

   - **Description**: Restricts the use of blank passwords so that they can only be used for local console logins and not for remote access.
   - **Importance**: Enhances security by preventing remote authentication with accounts that do not have a password.
   - **Considerations**: Ensure all remote access accounts are properly secured with strong passwords.
   - **CIS Reference**: Section 2.3.1.1 - Set 'Accounts: Limit local account use of blank passwords to console logon only' to 'Enabled'.

9. **Set 'Accounts: Guest account status' to 'Disabled'**

   - **Description**: Disables the built-in Guest account to prevent unauthorized access.
   - **Importance**: Eliminates a common attack vector by ensuring the Guest account cannot be used for login.
   - **Considerations**: Ensure that no legitimate processes depend on the Guest account before disabling.
   - **CIS Reference**: Section 2.3.1.2 - Set 'Accounts: Guest account status' to 'Disabled'.

10. **Set 'Accounts: Administrator account status' to 'Disabled'**

- **Description**: Disables the built-in Administrator account to reduce risk from brute-force attacks.
- **Importance**: Prevents attackers from targeting a well-known account name for privilege escalation.
- **Considerations**: Ensure at least one other administrative account exists before disabling.
- **CIS Reference**: Section 2.3.1.3 - Set 'Accounts: Administrator account status' to 'Disabled'.

11. **Set 'Domain controller: Refuse machine account password changes' to 'Disabled'**

- **Description**: Ensures that domain controllers allow machine account password changes.
- **Importance**: Prevents security risks associated with outdated or compromised machine account passwords.
- **Considerations**: Ensure this setting aligns with domain security policies and operational requirements.
- **CIS Reference**: Section 2.3.5.3 - Set 'Domain controller: Refuse machine account password changes' to 'Disabled' (Scored).

12. **Set 'Interactive logon: Do not display last user name' to 'Enabled'**

- **Description**: Prevents the last logged-in username from being displayed on the login screen.
- **Importance**: Enhances security by reducing the likelihood of targeted brute-force attacks.
- **Considerations**: Users will need to manually enter their username when logging in.
- **CIS Reference**: Section 2.3.7.1 - Set 'Interactive logon: Do not display last user name' to 'Enabled'.

13. **Set 'Interactive logon: Do not require CTRL+ALT+DEL' to 'Disabled'**

- **Description**: Ensures that users must press CTRL+ALT+DEL before logging in.
- **Importance**: Prevents malicious programs from simulating the login screen and capturing user credentials.
- **Considerations**: Users must be aware of this security feature to avoid confusion.
- **CIS Reference**: Section 2.3.7.2 - Set 'Interactive logon: Do not require CTRL+ALT+DEL' to 'Disabled'.

14. **Set 'Interactive logon: Machine inactivity limit' to '900 or fewer seconds'**

- **Description**: Configures the system to lock the workstation after a period of inactivity.
- **Importance**: Enhances security by reducing the risk of unauthorized access to unattended systems.
- **Considerations**: Ensure the timeout duration aligns with user workflow and security policies.
- **CIS Reference**: Section 2.3.7.3 - Set 'Interactive logon: Machine inactivity limit' to '900 or fewer seconds'.

15. **Configure 'Interactive logon: Message text for users attempting to log on'**

- **Description**: Displays a security message to users before they log in.
- **Importance**: Helps enforce security policies by informing users of legal and acceptable use policies.
- **Considerations**: Ensure the message text aligns with organizational compliance requirements.
- **CIS Reference**: Section 2.3.7.4 - Configure 'Interactive logon: Message text for users attempting to log on'.

16. **Set 'Interactive logon: Number of previous logons to cache (in case domain controller is not available)' to '4 or fewer logon(s)'**

- **Description**: Limits the number of cached logons when a domain controller is unavailable.
- **Importance**: Reduces the risk of unauthorized access by limiting cached credentials.
- **Considerations**: Ensure users who need offline access are aware of the limitation.
- **CIS Reference**: Section 2.3.7.6 - Set 'Interactive logon: Number of previous logons to cache (in case domain controller is not available)' to '4 or fewer logon(s)'.

17. **Set 'Interactive logon: Prompt user to change password before expiration' to 'between 5 and 14 days'**

- **Description**: Notifies users to change their password before expiration.
- **Importance**: Ensures users update their passwords in a timely manner to avoid account lockouts.
- **Considerations**: Choose an appropriate notification period based on user policy and security guidelines.
- **CIS Reference**: Section 2.3.7.7 - Set 'Interactive logon: Prompt user to change password before expiration' to 'between 5 and 14 days'.

18. **Set 'Microsoft network server: Amount of idle time required before suspending session' to '15 or fewer minute(s)'**

- **Description**: Specifies the maximum idle time before an active network session is suspended.
- **Importance**: Helps mitigate security risks by disconnecting inactive network sessions to prevent unauthorized access.
- **Considerations**: Ensure this setting does not interfere with critical background processes or workflows.
- **CIS Reference**: Section 2.3.9.1 - Set 'Microsoft network server: Amount of idle time required before suspending session' to '15 or fewer minute(s)'.

19. **Set 'Windows Firewall: Private: Firewall state' to 'On (recommended)'**

- **Description**: Ensures that the Windows Firewall is enabled for private networks.
- **Importance**: Protects systems from unauthorized access within private networks.
- **Considerations**: Ensure necessary applications and services are allowed through the firewall as needed.
- **CIS Reference**: Section 9.2.1 - Set 'Windows Firewall: Private: Firewall state' to 'On (recommended)'.

20. **Set 'Windows Firewall: Private: Inbound connections' to 'Block (default)'**

- **Description**: Configures the firewall to block all inbound connections unless explicitly allowed.
- **Importance**: Prevents unauthorized access by ensuring that only necessary inbound connections are permitted.
- **Considerations**: Review firewall rules to allow required services while maintaining security.
- **CIS Reference**: Section 9.2.2 - Set 'Windows Firewall: Private: Inbound connections' to 'Block (default)'.
