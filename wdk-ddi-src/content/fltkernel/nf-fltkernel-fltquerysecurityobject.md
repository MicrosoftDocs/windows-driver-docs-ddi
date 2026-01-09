---
UID: NF:fltkernel.FltQuerySecurityObject
title: FltQuerySecurityObject function (fltkernel.h)
description: FltQuerySecurityObject retrieves a copy of an object's security descriptor.
old-location: ifsk\fltquerysecurityobject.htm
tech.root: ifsk
ms.date: 01/09/2026
keywords: ["FltQuerySecurityObject function"]
ms.keywords: FltApiRef_p_to_z_6fa8f026-1268-4a97-b1e3-a2773e0a1784.xml, FltQuerySecurityObject, FltQuerySecurityObject function [Installable File System Drivers], fltkernel/FltQuerySecurityObject, ifsk.fltquerysecurityobject
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltQuerySecurityObject
 - fltkernel/FltQuerySecurityObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltQuerySecurityObject
---

# FltQuerySecurityObject function

## -description

**FltQuerySecurityObject** retrieves a copy of an object's security descriptor.

## -parameters

### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be **NULL**.

### -param FileObject [in]

File object pointer for the object whose security descriptor is being queried. This parameter is required and cannot be **NULL**.

### -param SecurityInformation [in]

[SECURITY_INFORMATION](/windows-hardware/drivers/ifs/security-information) value. This parameter is required and must be one of the following:

| SecurityInformation Value | Meaning |
|---------------------------|---------|
| OWNER_SECURITY_INFORMATION | The owner identifier of the object is being queried. Requires **READ_CONTROL** access. |
| GROUP_SECURITY_INFORMATION | The primary group identifier of the object is being queried. Requires **READ_CONTROL** access. |
| DACL_SECURITY_INFORMATION | The discretionary access control list (DACL) of the object is being queried. Requires **READ_CONTROL** access. |
| SACL_SECURITY_INFORMATION | The system ACL (SACL) of the object is being queried. Requires **ACCESS_SYSTEM_SECURITY** access. |

### -param SecurityDescriptor [in, out]

Pointer to a caller-supplied output buffer that receives a copy of the security descriptor for the specified object. The [SECURITY_DESCRIPTOR](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor) structure is returned in self-relative format. This parameter is optional and can be **NULL**.

### -param Length [in]

Size, in bytes, of the *SecurityDescriptor* buffer.

### -param LengthNeeded [out, optional]

Pointer to a caller-allocated variable that receives the number of bytes required to store the copiedsecurity descriptor returned in the buffer pointed to by the *SecurityDescriptor* parameter. This parameter is optional and can be **NULL**. If *SecurityDescriptor* is **NULL**, this parameter receives the required buffer size when the function returns **STATUS_BUFFER_TOO_SMALL**.

## -returns

**FltQuerySecurityObject** returns **STATUS_SUCCESS** or an appropriate **NTSTATUS** value such as one of the following:

| Return code | Description |
|-------------|-------------|
| **STATUS_ACCESS_DENIED** | The caller did not have the required access. This is an error code. |
| **STATUS_BUFFER_TOO_SMALL** | The buffer is too small to contain the security descriptor. None of the security information was copied to the buffer. The required buffer size is returned in the *LengthNeeded* parameter. This is an error code. |

## -remarks

A security descriptor can be in absolute or self-relative form. In self-relative form, all members of the structure are located contiguously in memory. In absolute form, the structure contains only pointers to its members.

The NTFS file system imposes a 64-KB limit on the size of the security descriptor that is written to disk for a file. (The FAT file system does not support security descriptors for files.) Thus, a 64-KB buffer pointed to by the *SecurityDescriptor* parameter is guaranteed to be large enough to hold the returned [SECURITY_DESCRIPTOR](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor) structure.

The object that the *FileObject* parameter points to can represent a named data stream. For more information about named data streams, see [FILE_STREAM_INFORMATION](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_stream_information).

For more information about security and access control, see the Microsoft Windows SDK documentation.

### Two-Step query pattern

A common usage pattern involves two calls to **FltQuerySecurityObject** to dynamically determine the required buffer size:

#### Step 1: Query the required buffer size

Call the function with a NULL buffer and zero length to obtain the required buffer size:

```cpp
ULONG bytesNeeded;

status = FltQuerySecurityObject(
    instance,
    fileObj,
    securityInfo,
    NULL,           // SecurityDescriptor - NULL to query size
    0,              // Length - zero since no buffer provided
    &bytesNeeded);  // Receives required buffer size
```

This call returns **STATUS_BUFFER_TOO_SMALL** and populates *bytesNeeded* with the required buffer size.

#### Step 2: Allocate and retrieve the security descriptor

Allocate a buffer of the required size and call the function again:

```cpp
secDescriptor = ExAllocatePoolWithTag(PagedPool, bytesNeeded, 'cSeD');
if (secDescriptor != NULL) {
    status = FltQuerySecurityObject(
        instance,
        fileObj,
        securityInfo,
        secDescriptor,  // Allocated buffer
        bytesNeeded,    // Size from first call
        NULL);          // LengthNeeded - optional, can be NULL
}
```

The *LengthNeeded* parameter is optional and can be NULL on the second call when retry logic on failure is not needed.

## -see-also

- [FILE_STREAM_INFORMATION](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_stream_information)
- [SECURITY_DESCRIPTOR](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor)
- [SECURITY_INFORMATION](/windows-hardware/drivers/ifs/security-information)
