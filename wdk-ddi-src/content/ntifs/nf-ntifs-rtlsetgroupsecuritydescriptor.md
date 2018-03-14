---
UID: NF:ntifs.RtlSetGroupSecurityDescriptor
title: RtlSetGroupSecurityDescriptor function
author: windows-driver-content
description: The RtlSetGroupSecurityDescriptor routine sets the primary group information of an absolute-format security descriptor. It replaces any primary group information that is already present in the security descriptor.
old-location: ifsk\rtlsetgroupsecuritydescriptor.htm
old-project: ifsk
ms.assetid: f0473975-7ab6-46ba-bdb7-eb227e6bc258
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlSetGroupSecurityDescriptor, RtlSetGroupSecurityDescriptor routine [Installable File System Drivers], ifsk.rtlsetgroupsecuritydescriptor, ntifs/RtlSetGroupSecurityDescriptor, rtlref_113e5ca7-5db3-4c93-a26f-c568e2164de9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlSetGroupSecurityDescriptor
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlSetGroupSecurityDescriptor function


## -description


The <b>RtlSetGroupSecurityDescriptor</b> routine sets the primary group information of an absolute-format security descriptor. It replaces any primary group information that is already present in the security descriptor. 


## -syntax


````
NTSTATUS RtlSetGroupSecurityDescriptor(
  _Inout_  PSECURITY_DESCRIPTOR SecurityDescriptor,
  _In_opt_ PSID                 Group,
  _In_opt_ BOOLEAN              GroupDefaulted
);
````


## -parameters




### -param SecurityDescriptor [in, out]

Pointer to the <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> structure whose primary group is to be set. <b>RtlSetGroupSecurityDescriptor</b> replaces any existing primary group with the new primary group. 


### -param Group [in, optional]

Pointer to a security identifier (<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>) structure for the security descriptor's new primary owner. This pointer, not the SID structure itself, is copied into the security descriptor. If <i>Group</i> is <b>NULL</b>, <b>RtlSetGroupSecurityDescriptor</b> clears the security descriptor's primary group information. This marks the security descriptor as having no primary group. 


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



To retrieve the primary group information for a security descriptor, use <a href="..\ntifs\nf-ntifs-rtlgetgroupsecuritydescriptor.md">RtlGetGroupSecurityDescriptor</a>. 

To set the owner information for a security descriptor, use <a href="..\ntifs\nf-ntifs-rtlsetownersecuritydescriptor.md">RtlSetOwnerSecurityDescriptor</a>. 

For more information about security and access control, see the Microsoft Windows SDK documentation. 




## -see-also

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556619">SECURITY_DESCRIPTOR_CONTROL</a>



<a href="..\ntifs\nf-ntifs-rtlgetgroupsecuritydescriptor.md">RtlGetGroupSecurityDescriptor</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\nf-ntifs-rtlsetownersecuritydescriptor.md">RtlSetOwnerSecurityDescriptor</a>



 

 


