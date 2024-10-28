# Conditional Access App Control

Conditional Access App Control is a feature that monitors and blocks user activities within cloud applications in real time. It allows for the management of access policies based on specific conditions, such as device type, location, and user identity. This helps protect sensitive data and prevent information leaks. With Conditional Access App Control, organizations can block access to applications or restrict certain actions, such as downloading sensitive files, if the user is on an unmanaged device or in a risky location.

---

## How It Works

Conditional Access App Control uses reverse proxy endpoints to track requests made to cloud applications. These endpoints are appended to the end of the domains of the applications.

![1](https://github.com/user-attachments/assets/012d0618-b07a-482a-bc90-e5bcbf583de3)

---

## Conditional Access App Control Tutorial

### Step 1: Create a Conditional Access Policy

To enable Conditional Access App Control, first, create a Conditional Access policy in Entra ID. Ensure that the **"Use Conditional Access App Control"** option is checked in the session category. This activates the transmission of information to the reverse proxy endpoints.

![2](https://github.com/user-attachments/assets/723dd908-0899-4bae-a167-0d140a72bc8a)

### Step 2: Log In to the Application

Log out and then log back into the application for which you are defining monitoring.

### Step 3: Verify the Application in the List

Check that the application appears in the list of Conditional Access App Control apps. You can find it in:

- **Microsoft Defender XDR**
- **Settings**
- **Cloud Apps**
- **Conditional Access App Control apps**

![3](https://github.com/user-attachments/assets/6b7d0488-577b-478e-8f0a-3e282475505e)

*If the application has SSO with Entra ID, it should automatically be added to this category.*

### Step 4: Remove Monitoring Notification

To remove the notification stating, **"Access to Microsoft OneDrive for Business is monitored,"** navigate to:

- **Microsoft Defender XDR**
- **Settings**
- **Cloud Apps**
- **User Monitoring**

Uncheck the option, **"Notify users that their activity is being monitored."**

![4](https://github.com/user-attachments/assets/55627a32-5127-4e52-9774-e925fafe4181)

![5](https://github.com/user-attachments/assets/3d67bc11-41f3-4ab9-abd6-dead99d9c0bb)

### Step 5: Define Monitoring Policy

Define a policy for what you want to monitor in:

- **Microsoft Defender for Cloud Apps**
- **Policies**
- **Policy Management**

Click the **"Create Policy"** button. In this case, create a **session policy** to monitor activities during the session.

You can use the policy templates provided by Microsoft:

![6](https://github.com/user-attachments/assets/c1fdc577-dc37-403a-931c-1c5a73fb891a)

---

And that’s it! From now on, anyone specified in the policy who logs into the application will be monitored, and they will be prevented from performing the actions defined in the policy.
