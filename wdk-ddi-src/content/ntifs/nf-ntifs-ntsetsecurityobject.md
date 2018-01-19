---
UID: NF:ntifs.NtSetSecurityObject
title: NtSetSecurityObject function
author: windows-driver-content
description: The ZwSetSecurityObject routine sets an object's security state.
old-location: kernel\zwsetsecurityobject.htm
old-project: kernel
ms.assetid: fbf6291e-9602-45d7-a620-702491a1d7de
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: NtSetSecurityObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwSetSecurityObject,NtSetSecurityObject
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# NtSetSecurityObject function



## -description
The <b>ZwSetSecurityObject</b> routine sets an object's security state.



## -syntax

````
NTSTATUS ZwSetSecurityObject(
  _In_ HANDLE               Handle,
  _In_ SECURITY_INFORMATION SecurityInformation,
  _In_ PSECURITY_DESCRIPTOR SecurityDescriptor
);
````


## -parameters

### -param Handle [in]

Handle for the object whose security state is to be set. This handle must have the access specified in the Meaning column of the table shown in the description of the <i>SecurityInformation</i> parameter.


### -param SecurityInformation [in]


<a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a> value specifying the information to be set. Can be a combination of one or more of the following. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DACL_SECURITY_INFORMATION

</td>
<td>
Indicates the discretionary access control list (DACL) of the object is to be set. Requires WRITE_DAC access.

</td>
</tr>
<tr>
<td>
GROUP_SECURITY_INFORMATION

</td>
<td>
Indicates the primary group identifier of the object is to be set. Requires WRITE_OWNER access.

</td>
</tr>
<tr>
<td>
OWNER_SECURITY_INFORMATION

</td>
<td>
Indicates the owner identifier of the object is to be set. Requires WRITE_OWNER access.

</td>
</tr>
<tr>
<td>
SACL_SECURITY_INFORMATION

</td>
<td>
Indicates the system ACL (SACL) of the object is to be set. Requires ACCESS_SYSTEM_SECURITY access.

</td>
</tr>
</table>
 


### -param SecurityDescriptor [in]

Pointer to the security descriptor to be set for the object.


## -returns
<b>ZwSetSecurityObject</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl><i>Handle</i> does not have the required access rights.
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl><i>SecurityDescriptor</i> is a <b>NULL</b> pointer.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The object's security descriptor could not be captured.
<dl>
<dt><b>STATUS_INVALID_ACL</b></dt>
</dl>The object's security descriptor contains an invalid ACL.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl><i>Handle</i> is not a valid handle.
<dl>
<dt><b>STATUS_INVALID_SECURITY_DESCR</b></dt>
</dl><i>SecurityDescriptor</i> does not point to a valid security descriptor.
<dl>
<dt><b>STATUS_INVALID_SID</b></dt>
</dl>The object's security descriptor contains an invalid <b>SID</b>.
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl><i>Handle</i> is not a handle of the expected type.
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>The revision level of the object's security descriptor is unknown or is not supported.

 


## -remarks
A security descriptor can be in absolute or self-relative form. In self-relative form, all members of the structure are located contiguously in memory. In absolute form, the structure only contains pointers to the members. For more information, see "Absolute and Self-Relative Security Descriptors" in the Security section of the Windows SDK documentation.

For more information about security and access control, see the documentation on these topics in the Windows SDK.

Minifilters should use <a href="..\fltkernel\nf-fltkernel-fltsetsecurityobject.md">FltSetSecurityObject</a> instead of <b>ZwSetSecurityObject</b>. 

Callers of <b>ZwSetSecurityObject</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltsetsecurityobject.md">FltSetSecurityObject</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwquerysecurityobject.md">ZwQuerySecurityObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwSetSecurityObject routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

