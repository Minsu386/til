## Device Management CheatSheet (Updated for Entra ID)

Device Management enables organizations to manage laptops, desktops, and mobile devices that access cloud resources. This is done through **Microsoft Entra ID** (formerly Azure Active Directory).

### Device Join Types

There are 3 main ways to enroll devices into Microsoft Entra ID:

- **Microsoft Entra Registered**
    - For **personally owned** or mobile devices.
    - Signed in with a **local or personal Microsoft account**.
    - Supports Windows 10+, iOS, Android, macOS, and Linux.
- **Microsoft Entra Joined**
    - For **organization-owned** devices.
    - Signed in with a **work account**.
    - Devices exist **only in the cloud** (Cloud Native).
    - Supported on Windows 10+ and Windows Server 2019+.
- **Hybrid Microsoft Entra Joined**
    - Devices are joined to both **on-premises AD** and registered with Microsoft Entra ID.
    - Enables coexistence between **on-premises and cloud environments**.
    - Works with Windows 7, 8.1, 10, and newer versions.

### Mobile Device Management (MDM)

- Manages the full device.
- Can **wipe or reset** it to factory settings.
- Enforces **device-level security and compliance** policies.

### Mobile Application Management (MAM)

- Controls only corporate apps — not the entire device.
- Allows you to **publish, configure, protect, monitor, and update** apps across devices.