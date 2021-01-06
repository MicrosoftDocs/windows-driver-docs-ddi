---
UID: NF:ntifs.NtSetSecurityObject
title: NtSetSecurityObject function (ntifs.h)
description: The ZwSetSecurityObject routine sets an object's security state.
old-location: kernel\zwsetsecurityobject.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["NtSetSecurityObject function"]
ms.keywords: NtSetSecurityObject, ZwSetSecurityObject, ZwSetSecurityObject routine [Kernel-Mode Driver Architecture], k111_38d4fa7c-4fc6-467c-9be2-ca997d739f44.xml, kernel.zwsetsecurityobject, ntifs/NtSetSecurityObject, ntifs/ZwSetSecurityObject
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - NtSetSecurityObject
 - ntifs/NtSetSecurityObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwSetSecurityObject
 - NtSetSecurityObject
---

# NtSetSecurityObject function


## -description

The **NtSetSecurityObject** routine sets an object's security state.

## -parameters

### -param Handle 

[in] Handle for the object whose security state is to be set. This handle must have the access specified in the Meaning column of the table shown in the description of the **SecurityInformation** parameter.

### -param SecurityInformation 

[in] [**SECURITY_INFORMATION**](/windows-hardware/drivers/ifs/security-information) value specifying the information to be set as a combination of one or more of the following. 

| Value | Meaning |
| ----- | ------- |
| OWNER_SECURITY_INFORMATION | Indicates the owner identifier of the object is to be set. Requires WRITE_OWNER access. |
| GROUP_SECURITY_INFORMATION | Indicates the primary group identifier of the object is to be set. Requires WRITE_OWNER access. |
| SACL_SECURITY_INFORMATION | Indicates the system ACL (SACL) of the object is to be set. Requires ACCESS_SYSTEM_SECURITY access. |
| DACL_SECURITY_INFORMATION | Indicates the discretionary access control list (DACL) of the object is to be set. Requires WRITE_DAC access. |

### -param SecurityDescriptor 

[in] Pointer to the security descriptor to be set for the object.

## -returns

**NtSetSecurityObject** returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_ACCESS_DENIED | The caller did not have the required access. |
| STATUS_ACCESS_VIOLATION| **SecurityDescriptor** was a **NULL** pointer. |
| STATUS_INSUFFICIENT_RESOURCES | The object's security descriptor could not be captured. |
| STATUS_INVALID_ACL | The object's security descriptor contained an invalid ACL. |
| STATUS_INVALID_HANDLE | **Handle** is not a valid handle. |
| STATUS_INVALID_SECURITY_DESCR | **SecurityDescriptor** did not point to a valid security descriptor. |
| STATUS_INVALID_SID | The object's security descriptor contained an invalid SID. |
| STATUS_OBJECT_TYPE_MISMATCH | **Handle** is not a handle of the expected type.|
| STATUS_UNKNOWN_REVISION | The revision level of the object's security descriptor was unknown or not supported. |



## -remarks

A security descriptor can be in absolute or self-relative form. In self-relative form, all members of the structure are located contiguously in memory. In absolute form, the structure only contains pointers to the members. For more information, see [Absolute and Self-Relative Security Descriptors](/windows/win32/secauthz/absolute-and-self-relative-security-descriptors). 

For more information about security and access control, see the documentation on these topics in the Windows SDK.

Minifilters should use [**FltSetSecurityObject**](../fltkernel/nf-fltkernel-fltsetsecurityobject.md) instead of **NtSetSecurityObject**. 

Callers of **NtSetSecurityObject** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](/windows-hardware/drivers/kernel/disabling-apcs).

> [!NOTE]
> If the call to the **NtSetSecurityObject** function occurs in user mode, you should use the name "**NtSetSecurityObject**" instead of "**ZwSetSecurityObject**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**FltSetSecurityObject**](../fltkernel/nf-fltkernel-fltsetsecurityobject.md)

[**SECURITY_DESCRIPTOR**](ns-ntifs-_security_descriptor.md)

[**SECURITY_INFORMATION**](/windows-hardware/drivers/ifs/security-information)

[**Using Nt and Zw Versions of the Native System Services Routines**](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[**NtQuerySecurityObject**](nf-ntifs-ntquerysecurityobject.md)

[**ZwSetSecurityObject**](nf-ntifs-zwsetsecurityobject.md)
