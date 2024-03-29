---
UID: NF:wdm.RtlLengthSecurityDescriptor
title: RtlLengthSecurityDescriptor function (wdm.h)
description: The RtlLengthSecurityDescriptor routine returns the size of a given security descriptor.
old-location: kernel\rtllengthsecuritydescriptor.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlLengthSecurityDescriptor function"]
ms.keywords: RtlLengthSecurityDescriptor, RtlLengthSecurityDescriptor routine [Kernel-Mode Driver Architecture], k109_ea245194-f36b-4b47-9d81-2d72fc19d5bc.xml, kernel.rtllengthsecuritydescriptor, wdm/RtlLengthSecurityDescriptor
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlLengthSecurityDescriptor
 - wdm/RtlLengthSecurityDescriptor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlLengthSecurityDescriptor
---

# RtlLengthSecurityDescriptor function


## -description

The <b>RtlLengthSecurityDescriptor</b> routine returns the size of a given security descriptor.

## -parameters

### -param SecurityDescriptor [in]


Pointer to a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>.

## -returns

<b>RtlLengthSecurityDescriptor</b> returns the size in bytes of the descriptor.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcreatesecuritydescriptor">RtlCreateSecurityDescriptor</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlsetdaclsecuritydescriptor">RtlSetDaclSecurityDescriptor</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlvalidsecuritydescriptor">RtlValidSecurityDescriptor</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>
