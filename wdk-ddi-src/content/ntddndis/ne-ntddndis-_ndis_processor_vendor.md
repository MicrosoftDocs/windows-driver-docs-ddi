---
UID: NE:ntddndis._NDIS_PROCESSOR_VENDOR
title: _NDIS_PROCESSOR_VENDOR (ntddndis.h)
description: The NDIS_PROCESSOR_VENDOR enumeration identifies a processor vendor.
old-location: netvista\ndis_processor_vendor.htm
tech.root: netvista
ms.assetid: c2d1b967-32fb-437a-a0bd-e0028acee022
ms.date: 05/02/2018
ms.keywords: "*PNDIS_PROCESSOR_VENDOR, NDIS_PROCESSOR_VENDOR, NDIS_PROCESSOR_VENDOR enumeration [Network Drivers Starting with Windows Vista], NdisProcessorVendorAuthenticAMD, NdisProcessorVendorGenuinIntel, NdisProcessorVendorUnknown, PNDIS_PROCESSOR_VENDOR, PNDIS_PROCESSOR_VENDOR enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_PROCESSOR_VENDOR, ndis_sysinfo_ref_7037b548-2ccc-4f39-9b34-33002f811bf1.xml, netvista.ndis_processor_vendor, ntddndis/NDIS_PROCESSOR_VENDOR, ntddndis/NdisProcessorVendorAuthenticAMD, ntddndis/NdisProcessorVendorGenuinIntel, ntddndis/NdisProcessorVendorUnknown, ntddndis/PNDIS_PROCESSOR_VENDOR"
ms.topic: enum
f1_keywords:
 - "ntddndis/NDIS_PROCESSOR_VENDOR"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddndis.h
api_name:
- NDIS_PROCESSOR_VENDOR
product:
- Windows
targetos: Windows
req.typenames: NDIS_PROCESSOR_VENDOR, *PNDIS_PROCESSOR_VENDOR
---

# _NDIS_PROCESSOR_VENDOR enumeration


## -description


The NDIS_PROCESSOR_VENDOR enumeration identifies a processor vendor.


## -enum-fields




### -field NdisProcessorVendorUnknown

The processor vendor is unknown.


### -field NdisProcessorVendorGenuinIntel

The processor vendor is Intel.


### -field NdisProcessorVendorGenuineIntel


### -field NdisProcessorVendorAuthenticAMD

The processor vendor is AMD.


## -remarks



The NDIS_PROCESSOR_VENDOR enumeration is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_system_processor_info">
    NDIS_SYSTEM_PROCESSOR_INFO</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_system_processor_info">NDIS_SYSTEM_PROCESSOR_INFO</a>
 

 

