---
UID: NS:wdm._DMA_ADAPTER_INFO
title: _DMA_ADAPTER_INFO
author: windows-driver-content
description: The DMA_ADAPTER_INFO structure is a container for a DMA_ADAPTER_INFO_XXX structure that describes the capabilities of a system DMA controller.
old-location: kernel\dma_adapter_info.htm
old-project: kernel
ms.assetid: 181C3421-85D1-457E-85A5-42C84AE41BD6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _DMA_ADAPTER_INFO, DMA_ADAPTER_INFO, *PDMA_ADAPTER_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DMA_ADAPTER_INFO
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.typenames: DMA_ADAPTER_INFO, *PDMA_ADAPTER_INFO
req.product: Windows 10 or later.
---

# _DMA_ADAPTER_INFO structure



## -description
The <b>DMA_ADAPTER_INFO</b> structure is a container for a <b>DMA_ADAPTER_INFO_</b><i>XXX</i> structure that describes the capabilities of a system DMA controller.



## -syntax

````
typedef struct _DMA_ADAPTER_INFO {
  ULONG Version;
  union {
    DMA_ADAPTER_INFO_V1 V1;
  };
} DMA_ADAPTER_INFO, *PDMA_ADAPTER_INFO;
````


## -struct-fields

### -field Version

The version number of the <b>DMA_ADAPTER_INFO_</b><i>XXX</i> structure that follows this member. For a <a href="..\wdm\ns-wdm-_dma_adapter_info_v1.md">DMA_ADAPTER_INFO_V1</a> structure, set this member to DMA_ADAPTER_INFO_VERSION1 before calling the <a href="..\wdm\nc-wdm-pget_dma_adapter_info.md">GetDmaAdapterInfo</a> routine.


### -field V1

The capabilities of the bus-master DMA device or the system DMA controller. For more information, see <a href="..\wdm\ns-wdm-_dma_adapter_info_v1.md">DMA_ADAPTER_INFO_V1</a>.


## -remarks
A device driver calls the <a href="..\wdm\nc-wdm-pget_dma_adapter_info.md">GetDmaAdapterInfo</a> routine to obtain a <b>DMA_ADAPTER_INFO</b> structure that describes the capabilities of a DMA controller.

The unnamed union in this structure contains a <b>DMA_ADAPTER_INFO_</b><i>XXX</i> structure. The <b>Version</b> member indicates which version of the <b>DMA_ADAPTER_INFO_</b><i>XXX</i> structure is contained in the union. Currently, only version 1 is supported.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_dma_adapter_info_v1.md">DMA_ADAPTER_INFO_V1</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pget_dma_adapter_info.md">GetDmaAdapterInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DMA_ADAPTER_INFO structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

