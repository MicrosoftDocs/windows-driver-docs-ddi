---
UID: NF:fltkernel.FltSetSecurityObject
title: FltSetSecurityObject function (fltkernel.h)
description: FltSetSecurityObject sets an object's security state.
old-location: ifsk\fltsetsecurityobject.htm
tech.root: ifsk
ms.assetid: 3276dff3-d12a-4a30-bbdc-a582a2228df3
ms.date: 04/16/2018
keywords: ["FltSetSecurityObject function"]
ms.keywords: FltApiRef_p_to_z_1174281c-5ba7-489b-8b8a-c0a4697ce678.xml, FltSetSecurityObject, FltSetSecurityObject function [Installable File System Drivers], fltkernel/FltSetSecurityObject, ifsk.fltsetsecurityobject
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
 - FltSetSecurityObject
 - fltkernel/FltSetSecurityObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltSetSecurityObject
---

# FltSetSecurityObject function


## -description

**FltSetSecurityObject** sets an object's security state.

## -parameters

### -param Instance 

[in]
Opaque instance pointer for the caller. This parameter is required and cannot be **NULL**.

### -param FileObject 

[in]
File object pointer for the object whose security state is to be set. The caller must have the access specified in the Meaning column of the table shown in the description of the *SecurityInformation* parameter. This parameter is required and cannot be **NULL**.

### -param SecurityInformation 

[in]
[SECURITY_INFORMATION](/windows-hardware/drivers/ifs/security-information) value specifying the information to be set as a combination of one or more of the following. 

|Value|Meaning|
|:-|:-|
|OWNER_SECURITY_INFORMATION|Indicates the owner identifier of the object is to be set. Requires WRITE_OWNER access.|
|GROUP_SECURITY_INFORMATION|Indicates the primary group identifier of the object is to be set. Requires WRITE_OWNER access.|
|DACL_SECURITY_INFORMATION|Indicates the discretionary access control list (DACL) of the object is to be set. Requires WRITE_DAC access.|
|SACL_SECURITY_INFORMATION|Indicates the system ACL (SACL) of the object is to be set. Requires ACCESS_SYSTEM_SECURITY access. |


### -param SecurityDescriptor 

[in]
Pointer to the security descriptor to be set for the object.

## -returns

**FltSetSecurityObject** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

|Return code|Description|
|:-|:-|
|**STATUS_ACCESS_DENIED**|The caller did not have the required access. This is an error code.|
|**STATUS_ACCESS_VIOLATION**|*SecurityDescriptor* was a **NULL** pointer. This is an error code.|
|**STATUS_INSUFFICIENT_RESOURCES**|The object's security descriptor could not be captured. This is an error code.|
|**STATUS_INVALID_ACL**|The object's security descriptor contained an invalid ACL. This is an error code.|
|**STATUS_INVALID_SECURITY_DESCR**|*SecurityDescriptor* did not point to a valid security descriptor. This is an error code.|
|**STATUS_INVALID_SID**|The object's security descriptor contained an invalid SID. This is an error code.|
|**STATUS_UNKNOWN_REVISION**|The revision level of the object's security descriptor was unknown or not supported. This is an error code.|
|**STATUS_NOT_IMPLEMENTED**|The **FltSetSecurityObject** routine is present but not supported in the operating system environment in which it was called.|


## -remarks

The **FltSetSecurityObject** routine is present and supported starting with Windows Vista.  In Windows 2000, Windows XP, and Server 2003 SP1, the routine is present but not supported, and will return STATUS_NOT_IMPLEMENTED if called in any of these environments.

A security descriptor can be in absolute or self-relative form. In self-relative form, all members of the structure are located contiguously in memory. In absolute form, the structure only contains pointers to the members. For more information, see [Absolute and Self-Relative Security Descriptors](/windows/win32/secauthz/absolute-and-self-relative-security-descriptors). 

For more information about security and access control, see the documentation on these topics in the Windows SDK.

## -see-also

[SECURITY_DESCRIPTOR](../ntifs/ns-ntifs-_security_descriptor.md)



[SECURITY_INFORMATION](/windows-hardware/drivers/ifs/security-information)



[ZwQuerySecurityObject](../ntifs/nf-ntifs-zwquerysecurityobject.md)



[ZwSetSecurityObject](../ntifs/nf-ntifs-zwsetsecurityobject.md)



[FltQuerySecurityObject](./nf-fltkernel-fltquerysecurityobject.md)
