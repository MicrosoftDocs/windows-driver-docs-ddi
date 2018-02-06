---
UID: NF:ntifs.RtlGetOwnerSecurityDescriptor
title: RtlGetOwnerSecurityDescriptor function
author: windows-driver-content
description: The RtlGetOwnerSecurityDescriptor routine returns the owner information for a given security descriptor.
old-location: ifsk\rtlgetownersecuritydescriptor.htm
old-project: ifsk
ms.assetid: 64c1b899-5737-474c-92ee-f18f7f2f06f5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: rtlref_7a3503c8-84ed-4ec7-9b69-5b93daaa6596.xml, ntifs/RtlGetOwnerSecurityDescriptor, RtlGetOwnerSecurityDescriptor, RtlGetOwnerSecurityDescriptor routine [Installable File System Drivers], ifsk.rtlgetownersecuritydescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlGetOwnerSecurityDescriptor
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlGetOwnerSecurityDescriptor function


## -description


The <b>RtlGetOwnerSecurityDescriptor</b> routine returns the owner information for a given security descriptor.


## -syntax


````
NTSTATUS RtlGetOwnerSecurityDescriptor(
  _In_  PSECURITY_DESCRIPTOR SecurityDescriptor,
  _Out_ PSID                 *Owner,
  _Out_ PBOOLEAN             OwnerDefaulted
);
````


## -parameters




### -param SecurityDescriptor [in]

Pointer to the security descriptor.


### -param Owner [out]

Pointer to an address to receive a pointer to the owner security identifier (<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>). If the security descriptor does not currently contain an owner SID, <i>Owner</i> receives <b>NULL</b>.


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

<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>

<a href="..\ntifs\nf-ntifs-rtlsetownersecuritydescriptor.md">RtlSetOwnerSecurityDescriptor</a>

<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>

<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>

<a href="..\wdm\nf-wdm-rtllengthsecuritydescriptor.md">RtlLengthSecurityDescriptor</a>

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>

<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlGetOwnerSecurityDescriptor routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

