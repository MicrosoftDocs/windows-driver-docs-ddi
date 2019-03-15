---
UID: NF:ntifs.RtlGetOwnerSecurityDescriptor
title: RtlGetOwnerSecurityDescriptor function (ntifs.h)
description: The RtlGetOwnerSecurityDescriptor routine returns the owner information for a given security descriptor.
old-location: ifsk\rtlgetownersecuritydescriptor.htm
tech.root: ifsk
ms.assetid: 64c1b899-5737-474c-92ee-f18f7f2f06f5
ms.date: 04/16/2018
ms.keywords: RtlGetOwnerSecurityDescriptor, RtlGetOwnerSecurityDescriptor routine [Installable File System Drivers], ifsk.rtlgetownersecuritydescriptor, ntifs/RtlGetOwnerSecurityDescriptor, rtlref_7a3503c8-84ed-4ec7-9b69-5b93daaa6596.xml
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlGetOwnerSecurityDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlGetOwnerSecurityDescriptor function


## -description


The <b>RtlGetOwnerSecurityDescriptor</b> routine returns the owner information for a given security descriptor.


## -parameters




### -param SecurityDescriptor [in]

Pointer to the security descriptor.


### -param Owner [out]

Pointer to an address to receive a pointer to the owner security identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>). If the security descriptor does not currently contain an owner SID, <i>Owner</i> receives <b>NULL</b>.


### -param OwnerDefaulted [out]

Pointer to a Boolean variable that receives <b>TRUE</b> if the owner information is derived from a default mechanism, rather than by the original provider of the security descriptor explicitly, <b>FALSE</b> otherwise. Valid only if <i>Owner</i> receives a non-<b>NULL</b> value.


## -returns



<b>RtlGetOwnerSecurityDescriptor</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

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



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561827">RtlCreateSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562025">RtlLengthSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562781">RtlSetDaclSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553220">RtlSetOwnerSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563024">RtlValidSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>
 

 

