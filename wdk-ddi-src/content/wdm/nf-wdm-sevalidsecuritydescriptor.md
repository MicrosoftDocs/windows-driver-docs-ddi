---
UID: NF:wdm.SeValidSecurityDescriptor
title: SeValidSecurityDescriptor function (wdm.h)
description: The SeValidSecurityDescriptor routine returns whether a given security descriptor is structurally valid.
old-location: kernel\sevalidsecuritydescriptor.htm
tech.root: kernel
ms.assetid: 14657843-bd48-4cab-b913-c95aeb6a6083
ms.date: 04/30/2018
keywords: ["SeValidSecurityDescriptor function"]
ms.keywords: SeValidSecurityDescriptor, SeValidSecurityDescriptor routine [Kernel-Mode Driver Architecture], k110_f193d746-c75f-4003-a2b3-a6b752652f9b.xml, kernel.sevalidsecuritydescriptor, wdm/SeValidSecurityDescriptor
f1_keywords:
 - "wdm/SeValidSecurityDescriptor"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- SeValidSecurityDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeValidSecurityDescriptor function


## -description



   The <b>SeValidSecurityDescriptor</b> routine returns whether a given security descriptor is structurally valid. 


## -parameters




### -param Length [in]

Specifies the size in bytes of the given security descriptor.


### -param SecurityDescriptor [in]

Pointer to the self-relative <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>, which must be buffered somewhere in system space.


## -returns



<b>SeValidSecurityDescriptor</b> returns <b>TRUE</b> if the buffered security descriptor is structurally valid.




## -remarks



<b>SeValidSecurityDescriptor</b> does not enforce policy. It simply checks that the given security descriptor data is formatted correctly. In particular, it checks the revision information, self relativity, owner, alignment, and, if available, SID, group, DACL, ACL, and/or SACL do not overflow the given <i>Length</i>. Consequently, callers of <b>SeValidSecurityDescriptor</b> cannot assume that a returned <b>TRUE</b> implies that the given security descriptor necessarily has valid contents.

If <b>SeValidSecurityDescriptor</b> returns <b>TRUE</b>, the given security descriptor can be passed on to another kernel-mode component because it is structurally valid. Otherwise, passing a structurally invalid security descriptor to be manipulated by another kernel-mode component can cause undefined results or even a system bug check.

To validate a security descriptor that was passed in from user mode, call <b>RtlValidSecurityDescriptor</b> rather than <b>SeValidSecurityDescriptor</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlvalidsecuritydescriptor">RtlValidSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>
 

 

