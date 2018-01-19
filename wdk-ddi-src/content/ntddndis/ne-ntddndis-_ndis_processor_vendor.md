---
UID: NE:ntddndis._NDIS_PROCESSOR_VENDOR
title: _NDIS_PROCESSOR_VENDOR
author: windows-driver-content
description: The NDIS_PROCESSOR_VENDOR enumeration identifies a processor vendor.
old-location: netvista\ndis_processor_vendor.htm
old-project: netvista
ms.assetid: c2d1b967-32fb-437a-a0bd-e0028acee022
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_PROCESSOR_VENDOR, *PNDIS_PROCESSOR_VENDOR, NDIS_PROCESSOR_VENDOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_PROCESSOR_VENDOR
req.alt-loc: ntddndis.h
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
req.typenames: *PNDIS_PROCESSOR_VENDOR, NDIS_PROCESSOR_VENDOR
---

# _NDIS_PROCESSOR_VENDOR enumeration



## -description
The NDIS_PROCESSOR_VENDOR enumeration identifies a processor vendor.



## -syntax

````
typedef enum _NDIS_PROCESSOR_VENDOR { 
  NdisProcessorVendorUnknown,
  NdisProcessorVendorGenuinIntel,
  NdisProcessorVendorAuthenticAMD
} NDIS_PROCESSOR_VENDOR, *PNDIS_PROCESSOR_VENDOR;
````


## -enum-fields

### -field NdisProcessorVendorUnknown

The processor vendor is unknown.


### -field NdisProcessorVendorGenuinIntel

The processor vendor is Intel.


### -field NdisProcessorVendorAuthenticAMD

The processor vendor is AMD.


## -remarks
The NDIS_PROCESSOR_VENDOR enumeration is used in the 
    <a href="..\ndis\ns-ndis-_ndis_system_processor_info.md">
    NDIS_SYSTEM_PROCESSOR_INFO</a> structure.


## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_ndis_system_processor_info.md">NDIS_SYSTEM_PROCESSOR_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PROCESSOR_VENDOR enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

