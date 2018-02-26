---
UID: NF:ntifs.RtlSetOwnerSecurityDescriptor
title: RtlSetOwnerSecurityDescriptor function
author: windows-driver-content
description: The RtlSetOwnerSecurityDescriptor routine sets the owner information of an absolute-format security descriptor. It replaces any owner information that is already present in the security descriptor.
old-location: ifsk\rtlsetownersecuritydescriptor.htm
old-project: ifsk
ms.assetid: 43392c57-8fe9-4219-9f00-ac73c83c3abc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , D, O, R, RtlSetOwnerSecurityDescriptor, RtlSetOwnerSecurityDescriptor routine [Installable File System Drivers], S, c, e, i, ifsk.rtlsetownersecuritydescriptor, l, n, ntifs/RtlSetOwnerSecurityDescriptor, o, p, r, rtlref_c8ec0e44-dadc-42ad-9947-2ecb5ec4aa57.xml, s, t, u, w, y"
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlSetOwnerSecurityDescriptor
product: Windows
targetos: Windows
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

<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556619">SECURITY_DESCRIPTOR_CONTROL</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-seassignsecurity.md">SeAssignSecurity</a>



<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



<a href="..\ntifs\nf-ntifs-rtlcreatesecuritydescriptorrelative.md">RtlCreateSecurityDescriptorRelative</a>



<a href="..\wdm\nf-wdm-rtllengthsecuritydescriptor.md">RtlLengthSecurityDescriptor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlSetOwnerSecurityDescriptor routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

