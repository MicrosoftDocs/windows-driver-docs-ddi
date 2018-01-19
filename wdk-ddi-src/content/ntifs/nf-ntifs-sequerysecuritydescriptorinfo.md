---
UID: NF:ntifs.SeQuerySecurityDescriptorInfo
title: SeQuerySecurityDescriptorInfo function
author: windows-driver-content
description: The SeQuerySecurityDescriptorInfo routine retrieves a copy of an object's security descriptor.
old-location: ifsk\sequerysecuritydescriptorinfo.htm
old-project: ifsk
ms.assetid: 4803e816-c59a-42b2-adc1-7a197ae16d42
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: SeQuerySecurityDescriptorInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SeQuerySecurityDescriptorInfo
req.alt-loc: NtosKrnl.exe
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
req.typenames: TOKEN_TYPE
---

# SeQuerySecurityDescriptorInfo function



## -description
The <b>SeQuerySecurityDescriptorInfo</b> routine retrieves a copy of an object's security descriptor.



## -syntax

````
NTSTATUS SeQuerySecurityDescriptorInfo(
  _In_    PSECURITY_INFORMATION SecurityInformation,
  _Out_   PSECURITY_DESCRIPTOR  SecurityDescriptor,
  _Inout_ PULONG                Length,
  _Inout_ PSECURITY_DESCRIPTOR  *ObjectsSecurityDescriptor
);
````


## -parameters

### -param SecurityInformation [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a> value specifying which security information is being queried. 

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
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The call to <b>SeQuerySecurityDescriptorInfo</b> succeeded.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer is too small for the security descriptor. None of the security information was copied to the buffer.

 


## -remarks
A security descriptor can be in absolute or self-relative format. A security descriptor in absolute format contains pointers to the information it contains, rather than containing the information itself. A security descriptor in self-relative format contains the information in a contiguous block of memory. In a self-relative security descriptor, a <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> structure always starts the information, but the security descriptor's other components can follow the SECURITY_DESCRIPTOR structure in any order. Instead of using memory addresses, the components of the security descriptor are identified by offsets from the beginning of the security descriptor. This format is useful when a security descriptor must be stored on a disk or transmitted by means of a communications protocol. 

Because the security descriptor is returned in self-relative format, the caller of <b>SeQuerySecurityDescriptorInfo</b> should cast the value returned in the <i>SecurityDescriptor</i> parameter to type PISECURITY_DESCRIPTOR_RELATIVE. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_acl.md">ACL</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlabsolutetoselfrelativesd.md">RtlAbsoluteToSelfRelativeSD</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlcreatesecuritydescriptorrelative.md">RtlCreateSecurityDescriptorRelative</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlgetownersecuritydescriptor.md">RtlGetOwnerSecurityDescriptor</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtllengthsecuritydescriptor.md">RtlLengthSecurityDescriptor</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlsetownersecuritydescriptor.md">RtlSetOwnerSecurityDescriptor</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeQuerySecurityDescriptorInfo routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

