---
UID: NF:ntifs.RtlSetOwnerSecurityDescriptor
title: RtlSetOwnerSecurityDescriptor function
author: windows-driver-content
description: The RtlSetOwnerSecurityDescriptor routine sets the owner information of an absolute-format security descriptor. It replaces any owner information that is already present in the security descriptor.
old-location: ifsk\rtlsetownersecuritydescriptor.htm
old-project: ifsk
ms.assetid: 43392c57-8fe9-4219-9f00-ac73c83c3abc
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlSetOwnerSecurityDescriptor
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
req.alt-api: RtlSetOwnerSecurityDescriptor
req.alt-loc: NtosKrnl.exe,Ntdll.dll
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
req.typenames: TOKEN_TYPE
---

# RtlSetOwnerSecurityDescriptor function



## -description
The <b>RtlSetOwnerSecurityDescriptor</b> routine sets the owner information of an absolute-format security descriptor. It replaces any owner information that is already present in the security descriptor. 



## -syntax

````
NTSTATUS RtlSetOwnerSecurityDescriptor(
  _Inout_  PSECURITY_DESCRIPTOR SecurityDescriptor,
  _In_opt_ PSID                 Owner,
  _In_opt_ BOOLEAN              OwnerDefaulted
);
````


## -parameters

### -param SecurityDescriptor [in, out]

Pointer to the SECURITY_DESCRIPTOR structure whose owner is to be set. <b>RtlSetOwnerSecurityDescriptor</b> replaces any existing owner with the new owner. 


### -param Owner [in, optional]

Pointer to a security identifier (<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>) structure for the security descriptor's new primary owner. This pointer, not the SID structure itself, is copied into the security descriptor. If this parameter is <b>NULL</b>, <b>RtlSetOwnerSecurityDescriptor</b> clears the security descriptor's owner information. This marks the security descriptor as having no owner. 


### -param OwnerDefaulted [in, optional]

Set to <b>TRUE</b> if the owner information is derived from a default mechanism. If this value is <b>TRUE</b>, it is default information. <b>RtlSetOwnerSecurityDescriptor</b> sets the SE_OWNER_DEFAULTED flag in the security descriptor's SECURITY_DESCRIPTOR_CONTROL field. If this parameter is <b>FALSE</b>, the SE_OWNER_DEFAULTED flag is cleared. 


## -returns
<b>RtlSetOwnerSecurityDescriptor</b> can return one of the following status codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The owner was successfully set or reset.
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>The given security descriptor's version is not recognized by this routine.
<dl>
<dt><b>STATUS_INVALID_SECURITY_DESCR</b></dt>
</dl>The given security descriptor is not a valid absolute security descriptor.

 


## -remarks
For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlcreatesecuritydescriptorrelative.md">RtlCreateSecurityDescriptorRelative</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtllengthsecuritydescriptor.md">RtlLengthSecurityDescriptor</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-seassignsecurity.md">SeAssignSecurity</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556619">SECURITY_DESCRIPTOR_CONTROL</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlSetOwnerSecurityDescriptor routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

