---
UID: NF:ntifs.RtlSetOwnerSecurityDescriptor
title: RtlSetOwnerSecurityDescriptor function (ntifs.h)
description: The RtlSetOwnerSecurityDescriptor routine sets the owner information of an absolute-format security descriptor. It replaces any owner information that is already present in the security descriptor.
old-location: ifsk\rtlsetownersecuritydescriptor.htm
tech.root: ifsk
ms.assetid: 43392c57-8fe9-4219-9f00-ac73c83c3abc
ms.date: 04/16/2018
ms.keywords: RtlSetOwnerSecurityDescriptor, RtlSetOwnerSecurityDescriptor routine [Installable File System Drivers], ifsk.rtlsetownersecuritydescriptor, ntifs/RtlSetOwnerSecurityDescriptor, rtlref_c8ec0e44-dadc-42ad-9947-2ecb5ec4aa57.xml
f1_keywords:
 - "ntifs/RtlSetOwnerSecurityDescriptor"
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlSetOwnerSecurityDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlSetOwnerSecurityDescriptor function


## -description


The <b>RtlSetOwnerSecurityDescriptor</b> routine sets the owner information of an absolute-format security descriptor. It replaces any owner information that is already present in the security descriptor. 


## -parameters




### -param SecurityDescriptor [in, out]

Pointer to the SECURITY_DESCRIPTOR structure whose owner is to be set. <b>RtlSetOwnerSecurityDescriptor</b> replaces any existing owner with the new owner. 


### -param Owner [in, optional]

Pointer to a security identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>) structure for the security descriptor's new primary owner. This pointer, not the SID structure itself, is copied into the security descriptor. If this parameter is <b>NULL</b>, <b>RtlSetOwnerSecurityDescriptor</b> clears the security descriptor's owner information. This marks the security descriptor as having no owner. 


### -param OwnerDefaulted [in, optional]

Set to <b>TRUE</b> if the owner information is derived from a default mechanism. If this value is <b>TRUE</b>, it is default information. <b>RtlSetOwnerSecurityDescriptor</b> sets the SE_OWNER_DEFAULTED flag in the security descriptor's SECURITY_DESCRIPTOR_CONTROL field. If this parameter is <b>FALSE</b>, the SE_OWNER_DEFAULTED flag is cleared. 


## -returns



<b>RtlSetOwnerSecurityDescriptor</b> can return one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The owner was successfully set or reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>
</td>
<td width="60%">
The given security descriptor's version is not recognized by this routine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_SECURITY_DESCR</b></dt>
</dl>
</td>
<td width="60%">
The given security descriptor is not a valid absolute security descriptor.

</td>
</tr>
</table>
 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcreatesecuritydescriptor">RtlCreateSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreatesecuritydescriptorrelative">RtlCreateSecurityDescriptorRelative</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtllengthsecuritydescriptor">RtlLengthSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlsetdaclsecuritydescriptor">RtlSetDaclSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlvalidsecuritydescriptor">RtlValidSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/security-descriptor-control">SECURITY_DESCRIPTOR_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-seassignsecurity">SeAssignSecurity</a>
 

 

