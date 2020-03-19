---
UID: NF:ntifs.RtlSetGroupSecurityDescriptor
title: RtlSetGroupSecurityDescriptor function (ntifs.h)
description: The RtlSetGroupSecurityDescriptor routine sets the primary group information of an absolute-format security descriptor. It replaces any primary group information that is already present in the security descriptor.
old-location: ifsk\rtlsetgroupsecuritydescriptor.htm
tech.root: ifsk
ms.assetid: f0473975-7ab6-46ba-bdb7-eb227e6bc258
ms.date: 04/16/2018
keywords: ["RtlSetGroupSecurityDescriptor function"]
ms.keywords: RtlSetGroupSecurityDescriptor, RtlSetGroupSecurityDescriptor routine [Installable File System Drivers], ifsk.rtlsetgroupsecuritydescriptor, ntifs/RtlSetGroupSecurityDescriptor, rtlref_113e5ca7-5db3-4c93-a26f-c568e2164de9.xml
f1_keywords:
 - "ntifs/RtlSetGroupSecurityDescriptor"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows Server 2003 SP1 and later.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlSetGroupSecurityDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlSetGroupSecurityDescriptor function


## -description


The <b>RtlSetGroupSecurityDescriptor</b> routine sets the primary group information of an absolute-format security descriptor. It replaces any primary group information that is already present in the security descriptor. 


## -parameters




### -param SecurityDescriptor [in, out]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> structure whose primary group is to be set. <b>RtlSetGroupSecurityDescriptor</b> replaces any existing primary group with the new primary group. 


### -param Group [in, optional]

Pointer to a security identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>) structure for the security descriptor's new primary owner. This pointer, not the SID structure itself, is copied into the security descriptor. If <i>Group</i> is <b>NULL</b>, <b>RtlSetGroupSecurityDescriptor</b> clears the security descriptor's primary group information. This marks the security descriptor as having no primary group. 


### -param GroupDefaulted [in, optional]

Set this Boolean variable to <b>TRUE</b> if the primary group information is derived from a default mechanism. If this parameter is <b>TRUE</b>, <b>RtlSetGroupSecurityDescriptor</b> sets the SE_GROUP_DEFAULTED flag in the security descriptor's SECURITY_DESCRIPTOR_CONTROL field. If this parameter is <b>FALSE</b>, <b>RtlSetGroupSecurityDescriptor</b> clears the SE_GROUP_DEFAULTED flag. 


## -returns



<b>RtlSetGroupSecurityDescriptor</b> returns STATUS_SUCCESS if the primary group was successfully set or reset. Otherwise, it returns an appropriate NTSTATUS value such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_SECURITY_DESCR</b></dt>
</dl>
</td>
<td width="60%">
The given security descriptor is not a valid absolute security descriptor. STATUS_INVALID_SECURITY_DESCR is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>
</td>
<td width="60%">
The given security descriptor's revision is not recognized by this routine. STATUS_UNKNOWN_REVISION is an error code. 

</td>
</tr>
</table>
 




## -remarks



To retrieve the primary group information for a security descriptor, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlgetgroupsecuritydescriptor">RtlGetGroupSecurityDescriptor</a>. 

To set the owner information for a security descriptor, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsetownersecuritydescriptor">RtlSetOwnerSecurityDescriptor</a>. 

For more information about security and access control, see the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlgetgroupsecuritydescriptor">RtlGetGroupSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsetownersecuritydescriptor">RtlSetOwnerSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/security-descriptor-control">SECURITY_DESCRIPTOR_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>
 

 

