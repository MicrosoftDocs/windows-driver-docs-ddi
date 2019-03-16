---
UID: NF:ntifs.RtlGetGroupSecurityDescriptor
title: RtlGetGroupSecurityDescriptor function (ntifs.h)
description: The RtlGetGroupSecurityDescriptor routine returns the primary group information for a given security descriptor.
old-location: ifsk\rtlgetgroupsecuritydescriptor.htm
tech.root: ifsk
ms.assetid: a2fbb125-42cf-4c33-83bb-3fc875712be3
ms.date: 04/16/2018
ms.keywords: RtlGetGroupSecurityDescriptor, RtlGetGroupSecurityDescriptor routine [Installable File System Drivers], ifsk.rtlgetgroupsecuritydescriptor, ntifs/RtlGetGroupSecurityDescriptor, rtlref_6ff72a5f-d1ef-4fac-bdd0-4a612c0018ca.xml
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
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlGetGroupSecurityDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlGetGroupSecurityDescriptor function


## -description


The <b>RtlGetGroupSecurityDescriptor</b> routine returns the primary group information for a given security descriptor.


## -parameters




### -param SecurityDescriptor [in]

Pointer to the security descriptor whose primary group information is to be returned.


### -param Group [out]

Pointer to a variable that receives a pointer to the security identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>) for the primary group. If the security descriptor does not contain a primary group, <i>*Group</i> receives <b>NULL</b>.


### -param GroupDefaulted [out]

Pointer to a Boolean variable that receives the value of the SE_GROUP_DEFAULTED flag in the security descriptor's SECURITY_DESCRIPTOR_CONTROL structure. This value is valid only if <i>*Group</i> receives a non-<b>NULL</b> value.


## -returns



<b>RtlGetGroupSecurityDescriptor</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>
</td>
<td width="60%">
The security descriptor's revision level is not known or is not supported. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



If the security descriptor pointed to by <i>SecurityDescriptor</i> contains a primary group, <b>RtlGetGroupSecurityDescriptor</b> sets the pointer pointed to by <i>Group</i> to the address of the security descriptor's group SID and sets the variable pointed to by <i>GroupDefaulted</i> to a valid value. 

If the security descriptor pointed to by <i>SecurityDescriptor</i> does not contain a primary group, <b>RtlGetGroupSecurityDescriptor</b> sets the pointer pointed to by <i>Group</i> to <b>NULL</b> and ignores the remaining output parameter, <i>GroupDefaulted</i>. 

To set the primary group information for a security descriptor, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553218">RtlSetGroupSecurityDescriptor</a>. 

To retrieve the owner information for a security descriptor, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff552976">RtlGetOwnerSecurityDescriptor</a>. 

For more information about security and access control, see the Microsoft Windows SDK documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552976">RtlGetOwnerSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553218">RtlSetGroupSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>
 

 

