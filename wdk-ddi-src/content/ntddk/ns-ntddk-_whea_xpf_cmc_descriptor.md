---
UID: NS:ntddk._WHEA_XPF_CMC_DESCRIPTOR
title: "_WHEA_XPF_CMC_DESCRIPTOR" (ntddk.h)
description: The WHEA_XPF_CMC_DESCRIPTOR structure describes a corrected machine check (CMC) error source for an x86 or x64 processor.
old-location: whea\whea_xpf_cmc_descriptor.htm
tech.root: whea
ms.assetid: d5eb2e20-9a11-4dae-9aa7-6e3799f0027f
ms.date: 02/20/2018
ms.keywords: "*PWHEA_XPF_CMC_DESCRIPTOR, PWHEA_XPF_CMC_DESCRIPTOR, PWHEA_XPF_CMC_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_XPF_CMC_DESCRIPTOR, WHEA_XPF_CMC_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_XPF_CMC_DESCRIPTOR, ntddk/PWHEA_XPF_CMC_DESCRIPTOR, ntddk/WHEA_XPF_CMC_DESCRIPTOR, whea.whea_xpf_cmc_descriptor, whearef_a14dc817-f689-492c-8993-1a5c9869a6c6.xml"
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_XPF_CMC_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: WHEA_XPF_CMC_DESCRIPTOR, *PWHEA_XPF_CMC_DESCRIPTOR
---

# _WHEA_XPF_CMC_DESCRIPTOR structure


## -description


The WHEA_XPF_CMC_DESCRIPTOR structure describes a corrected machine check (CMC) error source for an x86 or x64 processor.


## -struct-fields




### -field Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_XPFCMC.


### -field Enabled

A Boolean value that indicates if the error source is enabled.


### -field NumberOfBanks

The number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560651">WHEA_XPF_MC_BANK_DESCRIPTOR</a> structures contained in the <b>Banks</b> member.


### -field Reserved

Reserved for system use.


### -field Notify

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560574">WHEA_NOTIFICATION_DESCRIPTOR</a> structure that describes the notification mechanism that is used by the error source.


### -field Banks

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560651">WHEA_XPF_MC_BANK_DESCRIPTOR</a> structures that describe the banks of machine check registers.


## -remarks



A WHEA_XPF_CMC_DESCRIPTOR structure is contained within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560574">WHEA_NOTIFICATION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560651">WHEA_XPF_MC_BANK_DESCRIPTOR</a>
 

 

