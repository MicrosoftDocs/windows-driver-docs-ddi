---
UID: NF:wdm.RtlValidSecurityDescriptor
title: RtlValidSecurityDescriptor function (wdm.h)
description: The RtlValidSecurityDescriptor routine checks a given security descriptor's validity.
old-location: kernel\rtlvalidsecuritydescriptor.htm
tech.root: kernel
ms.assetid: 50d07154-a6d2-4b95-822f-33c0f37ece2f
ms.date: 04/30/2018
ms.keywords: RtlValidSecurityDescriptor, RtlValidSecurityDescriptor routine [Kernel-Mode Driver Architecture], k109_59b52650-028b-4e7a-8a00-234f40e354f2.xml, kernel.rtlvalidsecuritydescriptor, wdm/RtlValidSecurityDescriptor
f1_keywords:
 - "wdm/RtlValidSecurityDescriptor"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
- RtlValidSecurityDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlValidSecurityDescriptor function


## -description


The <b>RtlValidSecurityDescriptor</b> routine checks a given security descriptor's validity.


## -parameters




### -param SecurityDescriptor [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> to be checked.


## -returns



<b>RtlValidSecurityDescriptor</b> returns <b>TRUE</b> if the given descriptor is valid.




## -remarks



The routine checks the validity of an absolute-format security descriptor. To check the validity of a self-relative security descriptor, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlvalidrelativesecuritydescriptor">RtlValidRelativeSecurityDescriptor</a> routine instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcreatesecuritydescriptor">RtlCreateSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtllengthsecuritydescriptor">RtlLengthSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlsetdaclsecuritydescriptor">RtlSetDaclSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlvalidrelativesecuritydescriptor">RtlValidRelativeSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>
 

 

