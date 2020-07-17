---
UID: NF:ntifs.SeQuerySecurityDescriptorInfo
title: SeQuerySecurityDescriptorInfo function (ntifs.h)
description: The SeQuerySecurityDescriptorInfo routine retrieves a copy of an object's security descriptor.
old-location: ifsk\sequerysecuritydescriptorinfo.htm
tech.root: ifsk
ms.assetid: 4803e816-c59a-42b2-adc1-7a197ae16d42
ms.date: 04/16/2018
keywords: ["SeQuerySecurityDescriptorInfo function"]
ms.keywords: SeQuerySecurityDescriptorInfo, SeQuerySecurityDescriptorInfo routine [Installable File System Drivers], ifsk.sequerysecuritydescriptorinfo, ntifs/SeQuerySecurityDescriptorInfo, seref_c8ecba25-bc67-4314-a262-3dbae1407205.xml
f1_keywords:
 - "ntifs/SeQuerySecurityDescriptorInfo"
 - "SeQuerySecurityDescriptorInfo"
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
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SeQuerySecurityDescriptorInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeQuerySecurityDescriptorInfo function


## -description


The <b>SeQuerySecurityDescriptorInfo</b> routine retrieves a copy of an object's security descriptor.


## -parameters




### -param SecurityInformation [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/security-information">SECURITY_INFORMATION</a> value specifying which security information is being queried. 

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
Indicates the discretionary access control list (DACL) of the object is being queried. Requires READ_CONTROL access. 

</td>
</tr>
<tr>
<td>
GROUP_SECURITY_INFORMATION

</td>
<td>
Indicates the primary group identifier of the object is being queried. Requires READ_CONTROL access. 

</td>
</tr>
<tr>
<td>
OWNER_SECURITY_INFORMATION

</td>
<td>
Indicates the owner identifier of the object is being queried. Requires READ_CONTROL access. 

</td>
</tr>
<tr>
<td>
SACL_SECURITY_INFORMATION

</td>
<td>
Indicates the system ACL (SACL) of the object is being queried. Requires ACCESS_SYSTEM_SECURITY access. 

</td>
</tr>
</table>
 


### -param SecurityDescriptor [out]

Caller-allocated user buffer that <b>SeQuerySecurityDescriptorInfo</b> fills with a copy of the specified security descriptor in self-relative format. 


### -param Length [in, out]

Pointer to a variable that specifies the size, in bytes, of the buffer pointed to by <i>SecurityDescriptor</i>. Upon return, <b>SeQuerySecurityDescriptorInfo</b> sets this variable to the number of bytes required to store the requested information.


### -param ObjectsSecurityDescriptor [in, out]

Pointer to a pointer to an object's security descriptor. The security descriptor must be in self-relative format.


## -returns



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
The call to <b>SeQuerySecurityDescriptorInfo</b> succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer is too small for the security descriptor. None of the security information was copied to the buffer.

</td>
</tr>
</table>
 




## -remarks



A security descriptor can be in absolute or self-relative format. A security descriptor in absolute format contains pointers to the information it contains, rather than containing the information itself. A security descriptor in self-relative format contains the information in a contiguous block of memory. In a self-relative security descriptor, a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> structure always starts the information, but the security descriptor's other components can follow the SECURITY_DESCRIPTOR structure in any order. Instead of using memory addresses, the components of the security descriptor are identified by offsets from the beginning of the security descriptor. This format is useful when a security descriptor must be stored on a disk or transmitted by means of a communications protocol. 

Because the security descriptor is returned in self-relative format, the caller of <b>SeQuerySecurityDescriptorInfo</b> should cast the value returned in the <i>SecurityDescriptor</i> parameter to type PISECURITY_DESCRIPTOR_RELATIVE. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">ACL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlabsolutetoselfrelativesd">RtlAbsoluteToSelfRelativeSD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcreatesecuritydescriptor">RtlCreateSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreatesecuritydescriptorrelative">RtlCreateSecurityDescriptorRelative</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlgetownersecuritydescriptor">RtlGetOwnerSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtllengthsecuritydescriptor">RtlLengthSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlsetdaclsecuritydescriptor">RtlSetDaclSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsetownersecuritydescriptor">RtlSetOwnerSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlvalidsecuritydescriptor">RtlValidSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>
 

 

