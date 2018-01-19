---
UID: NF:wdm.SeValidSecurityDescriptor
title: SeValidSecurityDescriptor function
author: windows-driver-content
description: The SeValidSecurityDescriptor routine returns whether a given security descriptor is structurally valid.
old-location: kernel\sevalidsecuritydescriptor.htm
old-project: kernel
ms.assetid: 14657843-bd48-4cab-b913-c95aeb6a6083
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: SeValidSecurityDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SeValidSecurityDescriptor
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# SeValidSecurityDescriptor function



## -description

   The <b>SeValidSecurityDescriptor</b> routine returns whether a given security descriptor is structurally valid. 



## -syntax

````
BOOLEAN SeValidSecurityDescriptor(
  _In_ ULONG                Length,
  _In_ PSECURITY_DESCRIPTOR SecurityDescriptor
);
````


## -parameters

### -param Length [in]

Specifies the size in bytes of the given security descriptor.


### -param SecurityDescriptor [in]

Pointer to the self-relative <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>, which must be buffered somewhere in system space.


## -returns
<b>SeValidSecurityDescriptor</b> returns <b>TRUE</b> if the buffered security descriptor is structurally valid.


## -remarks
<b>SeValidSecurityDescriptor</b> does not enforce policy. It simply checks that the given security descriptor data is formatted correctly. In particular, it checks the revision information, self relativity, owner, alignment, and, if available, SID, group, DACL, ACL, and/or SACL do not overflow the given <i>Length</i>. Consequently, callers of <b>SeValidSecurityDescriptor</b> cannot assume that a returned <b>TRUE</b> implies that the given security descriptor necessarily has valid contents.

If <b>SeValidSecurityDescriptor</b> returns <b>TRUE</b>, the given security descriptor can be passed on to another kernel-mode component because it is structurally valid. Otherwise, passing a structurally invalid security descriptor to be manipulated by another kernel-mode component can cause undefined results or even a system bug check.

To validate a security descriptor that was passed in from user mode, call <b>RtlValidSecurityDescriptor</b> rather than <b>SeValidSecurityDescriptor</b>. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SeValidSecurityDescriptor routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

