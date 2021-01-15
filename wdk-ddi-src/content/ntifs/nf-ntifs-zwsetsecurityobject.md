---
UID: NF:ntifs.ZwSetSecurityObject
title: ZwSetSecurityObject function (ntifs.h)
description: The ZwSetSecurityObject routine sets an object's security state.
old-location: kernel\zwsetsecurityobject.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ZwSetSecurityObject function"]
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
 - ZwSetSecurityObject
 - ntifs/ZwSetSecurityObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwSetSecurityObject
---

# ZwSetSecurityObject function


## -description

The <b>ZwSetSecurityObject</b> routine sets an object's security state.

## -parameters

### -param Handle 

[in]
Handle for the object whose security state is to be set. This handle must have the access specified in the Meaning column of the table shown in the description of the <i>SecurityInformation</i> parameter.

### -param SecurityInformation 

[in]

<a href="/windows-hardware/drivers/ifs/security-information">SECURITY_INFORMATION</a> value specifying the information to be set. Can be a combination of one or more of the following. 

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

### -param SecurityDescriptor 

[in]
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

Minifilters should use <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetsecurityobject">FltSetSecurityObject</a> instead of <b>ZwSetSecurityObject</b>. 

Callers of <b>ZwSetSecurityObject</b> must be running at IRQL = PASSIVE_LEVEL and <a href="/windows-hardware/drivers/kernel/disabling-apcs">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to the <b>ZwSetSecurityObject</b> function occurs in user mode, you should use the name "<a href="/previous-versions/ff567106(v=vs.85)">NtSetSecurityObject</a>" instead of "<b>ZwSetSecurityObject</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetsecurityobject">FltSetSecurityObject</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ifs/security-information">SECURITY_INFORMATION</a>



<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/previous-versions/ff567066(v=vs.85)">ZwQuerySecurityObject</a>

