# Conditional Access (CA)

**Conditional Access** (CA) is a feature that enables access to resources through policies. These policies define conditions—such as group membership and specific locations—and specify the actions (decisions) that will occur, like blocking, granting, or limiting access.

---

## Creating a Conditional Access Policy

This guide is based on Microsoft’s official documentation. For a more detailed explanation of each value, please refer to the specific guidelines provided.

### Step 1: Navigate to Conditional Access

1. Go to the **Security** category in **Entra ID**.
2. Select **Conditional Access**.
3. Click the **"Create New Policy"** button and fill in the required details.

![Create New Policy](https://github.com/user-attachments/assets/00fdb544-172b-4f70-a73a-f7340187b1a0)

---

### Assignments: Applies to

- **Users**: Specify which users the policy applies to.
- **Target Resources**: Define the cloud applications affected by this policy.

The policy consists of **Include** and **Exclude** options, determining which users and applications are covered.

![Assignments](https://github.com/user-attachments/assets/8f27acc6-fb76-44d3-bddf-1293fb33086a)

---

### Users

- **None**: No users are included.
- **All Users**: Applies to every user in the tenant. *Note: Exclude Global Admins to prevent lockout.*
- **Select Users and Groups**: 
  - **All Guest and External Users**: All guest users.
  - **Directory Roles**: Use roles defined by Microsoft.
  - **Users and Groups**: Manually select specific users or groups.

---

### Target Resources

Specify the applications to which the policy will apply:

![Target Resources](https://github.com/user-attachments/assets/67dd4a63-8d2d-409c-80f7-b208e2a2ef69)

- **Cloud Apps**: List of applications.
- **User Actions**: Monitor activities (e.g., significant data changes).
- **Authentication Context**: Limit access to specific content (e.g., SharePoint documents).

---

### Conditions

Conditions that will trigger the policy:

![Conditions](https://github.com/user-attachments/assets/e54ef6aa-d133-4915-896a-975f5b6f9ea7)

- **User Risk**: Likelihood of user compromise.
- **Sign-in Risk**: Suspicion about the legitimacy of an authentication request.
- **Insider Risk**: Monitors suspicious internal behaviors using Purview.
- **Device Platforms**: Based on the operating system type.
- **Locations**: Geographical conditions.
- **Client Apps**: Type of application in use.
- **Filter for Devices**: Specific device criteria (e.g., manufacturer).

---

### Grant / Block Actions

Specify actions for blocking or granting access based on the defined conditions:

![Grant/Block](https://github.com/user-attachments/assets/5ef63e26-6ff4-4864-a9ce-7863858de56c)

- **Require Multifactor Authentication**: Mandates MFA for access.
- **Require Authentication Strength**: Choose from various authentication methods.
- **Require Device Compliance**: Integrates with Intune for device compliance.
- **Require Microsoft Entra Hybrid Joined Device**: Only allows devices that have completed the hybrid join process.
- **Require Approved Client App**: Limits access to authorized applications.
- **Require App Protection Policy**: Requires an Intune policy for access.
- **Require Password Change**: Forces users to update their passwords.

---

### Session Controls

Control actions within user sessions:

- **Use Application Enforced Restrictions**: Limit access to Microsoft applications.
- **Use Conditional Access App Control**: Activates monitoring and control features with Defender for Cloud Apps:
  - **Use Custom Policy**: For specific monitoring and blocking.
  - **Monitor Only**: For monitoring without blocking.
  - **Block Downloads**: Prevents downloads.
  - **Sign-in Frequency**: Determines session disconnection intervals.
  - **Persistent Browser Session**: Keeps sessions active even when the browser is closed.
  - **Customize Continuous Access Evaluation**: Re-authenticates if unusual activity is detected.
  - **Disable Resilience Default**: Implements disaster recovery options.

---

### Enable Policy

Choose from the following options:

- **Yes**: Enable the policy.
- **No**: Disable the policy.
- **Reporting Only**: Monitor without enforcement.

---

By following these guidelines, you can effectively create and manage Conditional Access policies in Microsoft Entra ID, enhancing security and compliance across your organization.
