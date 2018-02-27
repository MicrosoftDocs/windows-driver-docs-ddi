---
UID: NS:ntddk._WHEA_XPF_CMC_DESCRIPTOR
title: "_WHEA_XPF_CMC_DESCRIPTOR"
author: windows-driver-content
description: The WHEA_XPF_CMC_DESCRIPTOR structure describes a corrected machine check (CMC) error source for an x86 or x64 processor.
old-location: whea\whea_xpf_cmc_descriptor.htm
old-project: whea
ms.assetid: d5eb2e20-9a11-4dae-9aa7-6e3799f0027f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_XPF_CMC_DESCRIPTOR, PWHEA_XPF_CMC_DESCRIPTOR, PWHEA_XPF_CMC_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_XPF_CMC_DESCRIPTOR, WHEA_XPF_CMC_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_XPF_CMC_DESCRIPTOR, ntddk/PWHEA_XPF_CMC_DESCRIPTOR, ntddk/WHEA_XPF_CMC_DESCRIPTOR, whea.whea_xpf_cmc_descriptor, whearef_a14dc817-f689-492c-8993-1a5c9869a6c6.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_XPF_CMC_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: WHEA_XPF_CMC_DESCRIPTOR, *PWHEA_XPF_CMC_DESCRIPTOR
---

# _WHEA_XPF_CMC_DESCRIPTOR structure


## -description


The WHEA_XPF_CMC_DESCRIPTOR structure describes a corrected machine check (CMC) error source for an x86 or x64 processor.


## -syntax


````
typedef struct _WHEA_XPF_CMC_DESCRIPTOR {
  USHORT                       Type;
  BOOLEAN                      Enabled;
  UCHAR                        NumberOfBanks;
  ULONG                        Reserved;
  WHEA_NOTIFICATION_DESCRIPTOR Notify;
  WHEA_XPF_MC_BANK_DESCRIPTOR  Banks[WHEA_MAX_MC_BANKS];
} WHEA_XPF_CMC_DESCRIPTOR, *PWHEA_XPF_CMC_DESCRIPTOR;
````


## -struct-fields




### -field Type

The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_XPFCMC.


### -field Enabled

A Boolean value that indicates if the error source is enabled.


### -field NumberOfBanks

The number of <a href="..\ntddk\ns-ntddk-_whea_xpf_mc_bank_descriptor.md">WHEA_XPF_MC_BANK_DESCRIPTOR</a> structures contained in the <b>Banks</b> member.


### -field Reserved

Reserved for system use.


### -field Notify

A <a href="..\ntddk\ns-ntddk-_whea_notification_descriptor.md">WHEA_NOTIFICATION_DESCRIPTOR</a> structure that describes the notification mechanism that is used by the error source.


### -field Banks

An array of <a href="..\ntddk\ns-ntddk-_whea_xpf_mc_bank_descriptor.md">WHEA_XPF_MC_BANK_DESCRIPTOR</a> structures that describe the banks of machine check registers.


## -remarks



A WHEA_XPF_CMC_DESCRIPTOR structure is contained within the <a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_source_descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a>



<a href="..\ntddk\ns-ntddk-_whea_notification_descriptor.md">WHEA_NOTIFICATION_DESCRIPTOR</a>



<a href="..\ntddk\ns-ntddk-_whea_xpf_mc_bank_descriptor.md">WHEA_XPF_MC_BANK_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_CMC_DESCRIPTOR structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

