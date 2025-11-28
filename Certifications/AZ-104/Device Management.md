Device Management enables organizations to manage laptops, desktops, and mobile devices that access cloud resources. This is done through **Microsoft Entra ID**

## Device Join Types
There are 3 main ways to enroll devices into Entra ID:
1) Microsoft Entra Registered
    - For **Personally owned** or mobile devices
    - Signed in with a **local or personal Microsoft account**
    - Supports Windows 10+, iOS, Android, macOS, and Linux
2) Microsoft Entra Joined
    - For **Organization-Owned** devices
    - Signed in with a **work account**
    - Devices exist **only in the cloud** (cloud native)
    - Supported on Win 10+ and Win Server 2019+
3) Hybrid Microsoft Entra joined
    - Devices are joined to both **on-premises AD** and registered with Microsoft Entra ID
    - Enables coexistence between **on-premises and cloud environments**
    - Works with Win 7, 8.1, 10, and newer

## MDM
- Manages the full device
- Can **wipe or reset** it to factory settings.
- Enforces **Device-level security and compliance policies**

## MAM 
- Controls only corporate apps -- not the entire device
- Allows you 