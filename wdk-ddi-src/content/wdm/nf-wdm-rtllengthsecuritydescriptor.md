---
UID: NF:wdm.RtlLengthSecurityDescriptor
title: RtlLengthSecurityDescriptor function (wdm.h)
description: The RtlLengthSecurityDescriptor routine returns the size of a given security descriptor.
old-location: kernel\rtllengthsecuritydescriptor.htm
tech.root: kernel
ms.assetid: e06888eb-2ced-46c0-bdbf-3bad57020bf7
ms.date: 04/30/2018
keywords: ["RtlLengthSecurityDescriptor function"]
ms.keywords: RtlLengthSecurityDescriptor, RtlLengthSecurityDescriptor routine [Kernel-Mode Driver Architecture], k109_ea245194-f36b-4b47-9d81-2d72fc19d5bc.xml, kernel.rtllengthsecuritydescriptor, wdm/RtlLengthSecurityDescriptor
f1_keywords:
 - "wdm/RtlLengthSecurityDescriptor"
 - "RtlLengthSecurityDescriptor"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
- RtlLengthSecurityDescriptor
targetos: Windows
req.typenames: 
---

# RtlLengthSecurityDescriptor function


## -description


The <b>RtlLengthSecurityDescriptor</b> routine returns the size of a given security descriptor.


## -parameters




### -param SecurityDescriptor [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>. 


## -returns



<b>RtlLengthSecurityDescriptor</b> returns the size in bytes of the descriptor. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcreatesecuritydescriptor">RtlCreateSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlsetdaclsecuritydescriptor">RtlSetDaclSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlvalidsecuritydescriptor">RtlValidSecurityDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>
 

 

