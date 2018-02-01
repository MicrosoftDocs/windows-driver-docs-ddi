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
ms.keywords: ZwSetSecurityObject, k111_38d4fa7c-4fc6-467c-9be2-ca997d739f44.xml, ntifs/ZwSetSecurityObject, ZwSetSecurityObject routine [Kernel-Mode Driver Architecture], ntifs/NtSetSecurityObject, NtSetSecurityObject, kernel.zwsetsecurityobject
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwSetSecurityObject
-	NtSetSecurityObject
product: Windows
targetos: Windows
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
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
<i>Handle</i> does not have the required access rights.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl>
</td>
<td width="60%">
<i>SecurityDescriptor</i> is a <b>NULL</b> pointer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The object's security descriptor could not be captured.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_ACL</b></dt>
</dl>
</td>
<td width="60%">
The object's security descriptor contains an invalid ACL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
<i>Handle</i> is not a valid handle.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_SECURITY_DESCR</b></dt>
</dl>
</td>
<td width="60%">
<i>SecurityDescriptor</i> does not point to a valid security descriptor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_SID</b></dt>
</dl>
</td>
<td width="60%">
The object's security descriptor contains an invalid <b>SID</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
<i>Handle</i> is not a handle of the expected type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>
</td>
<td width="60%">
The revision level of the object's security descriptor is unknown or is not supported.

</td>
</tr>
</table> 



## -remarks


A security descriptor can be in absolute or self-relative form. In self-relative form, all members of the structure are located contiguously in memory. In absolute form, the structure only contains pointers to the members. For more information, see "Absolute and Self-Relative Security Descriptors" in the Security section of the Windows SDK documentation.

For more information about security and access control, see the documentation on these topics in the Windows SDK.

Minifilters should use <a href="..\fltkernel\nf-fltkernel-fltsetsecurityobject.md">FltSetSecurityObject</a> instead of <b>ZwSetSecurityObject</b>. 

Callers of <b>ZwSetSecurityObject</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.
<div class="alert"><b>Note</b>  If the call to the <b>ZwSetSecurityObject</b> function occurs in user mode, you should use the name "<a href="https://msdn.microsoft.com/library/windows/hardware/ff557685">NtSetSecurityObject</a>" instead of "<b>ZwSetSecurityObject</b>".</div><div> </div>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.



## -see-also

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>

<a href="..\ntifs\nf-ntifs-zwquerysecurityobject.md">ZwQuerySecurityObject</a>

<a href="..\fltkernel\nf-fltkernel-fltsetsecurityobject.md">FltSetSecurityObject</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwSetSecurityObject routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

