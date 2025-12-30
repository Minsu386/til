## Use AzCopy to Copy Files to Storage Accounts (Updated for Entra ID)

### Reference

- [Get started with AzCopy](https://learn.microsoft.com/azure/storage/common/storage-use-azcopy-v10)
- [Authorize access to data with Microsoft Entra ID](https://learn.microsoft.com/azure/storage/common/storage-auth-aad)
- [Assign Azure roles for data access](https://learn.microsoft.com/azure/storage/blobs/assign-azure-role-data-access)

## Step 0: Ensure Cloud Shell Has a Mounted Storage

- If you don’t see `~/clouddrive` (only a `Microsoft` folder), you are in an **ephemeral session**.
- Mount a storage account so files persist:

```
clouddrive mount -s "<subscription>" -g "<resource-group>" -n "<storage-account>" -f "<file-share>"
```

- After mounting, verify with:

```
ls ~
# You should see clouddrive
```

## Step 1: Create Storage and Upload Files

- 1.1
    
    **Storage account**
    
- 1.2
    
    Create container: **kivasfajo**
    
- 1.3
    
    Upload test file (e.g., **kivas-fajo.jpg**) into your **file share** that backs Cloud Shell (or drag-drop using the Cloud Shell upload button).
    
- 1.4
    
    Confirm the file is present:
    

```
cd ~/clouddrive
ls
```

- 1.5
    
    Verify AzCopy is available:
    

```
azcopy --version
```

> **Note:** AzCopy v10 is preinstalled in Cloud Shell. You no longer need to download it manually unless you’re running locally.

## Step 2: Authenticate with Microsoft Entra ID

AzCopy can use **Microsoft Entra ID** for role-based access:

- 2.1
    
    Login:
    

```
azcopy login
```

This opens a device code flow → paste the code at [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin).

- 2.2
    
    If needed, specify tenant:
    

```
azcopy login --tenant-id <tenant-guid>
```

## Step 3: Assign Correct Entra Role

To upload blobs with AzCopy via Entra ID, your user must have **Storage Blob Data Contributor** on the storage account (or container).

- In **fajo → Access Control (IAM) → Add role assignment**
- Select **Storage Blob Data Contributor**
- Assign to yourself.

## Step 4: Copy a File

- 4.1
    
    Get the container URL:
    
- 4.2
    
    Copy the file:
    

```
azcopy copy "kivas-fajo.jpg" "https://fajo.blob.core.windows.net/kivasfajo/kivas-fajo.jpg"
```

(Always use quotes to avoid `&` parsing issues.)

## Step 5: Using a SAS Token (Alternative)

If you can’t use Entra ID roles, use a **SAS token**:

- 5.1
    
    In the **kivasfajo container**, generate SAS with **Read/Write** (or full) permissions.
    
- 5.2
    
    Copy file with SAS:
    

```
azcopy cp "kivas-fajo.jpg" "https://fajo.blob.core.windows.net/kivasfajo/kivas-fajo.jpg?<SAS_TOKEN>"
```

Or with full SAS URL:

```
azcopy cp "kivas-fajo.jpg" "<FULL_SAS_URL>"
```

## Troubleshooting

- **No `clouddrive`?** → Mount storage (see Step 0).
- **Permission denied?** → Ensure you have **Storage Blob Data Contributor** via Entra ID.
- **RBAC delay?** → Wait a few minutes for role propagation.
- **SAS not working?** → Verify expiry and permissions.

### Key Updates Made:

- Replaced **Azure AD** with **Microsoft Entra ID**.
- Clarified role: **Storage Blob Data Contributor** (not Owner).
- Noted that **AzCopy is preinstalled in Cloud Shell**.
- Added guidance for ephemeral sessions (no `clouddrive`).