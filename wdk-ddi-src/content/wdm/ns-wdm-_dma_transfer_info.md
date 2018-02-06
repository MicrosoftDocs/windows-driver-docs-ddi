---
UID: NS:wdm._DMA_TRANSFER_INFO
title: "_DMA_TRANSFER_INFO"
author: windows-driver-content
description: The DMA_TRANSFER_INFO structure is a container for a DMA_TRANSFER_INFO_XXX structure that describes the allocation requirements for a scatter/gather list.
old-location: kernel\dma_transfer_info.htm
old-project: kernel
ms.assetid: 1CD5CE6F-5179-40D5-BCD9-3587914C8139
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/DMA_TRANSFER_INFO, DMA_TRANSFER_INFO structure [Kernel-Mode Driver Architecture], wdm/PDMA_TRANSFER_INFO, kernel.dma_transfer_info, _DMA_TRANSFER_INFO, PDMA_TRANSFER_INFO, PDMA_TRANSFER_INFO structure pointer [Kernel-Mode Driver Architecture], DMA_TRANSFER_INFO, *PDMA_TRANSFER_INFO
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	DMA_TRANSFER_INFO
product: Windows
targetos: Windows
req.typenames: "*PDMA_TRANSFER_INFO, DMA_TRANSFER_INFO"
req.product: Windows 10 or later.
---

# _DMA_TRANSFER_INFO structure


## -description


The <b>DMA_TRANSFER_INFO</b> structure is a container for a <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure that describes the allocation requirements for a scatter/gather list.


## -syntax


````
typedef struct _DMA_TRANSFER_INFO {
  ULONG  Version;
  union {
    DMA_TRANSFER_INFO_V1 V1;
  };
} DMA_TRANSFER_INFO, *PDMA_TRANSFER_INFO;
````


## -struct-fields




### -field V1

The allocation requirements for a scatter/gather list. For more information, see <a href="..\wdm\ns-wdm-_dma_transfer_info_v1.md">DMA_TRANSFER_INFO_V1</a>.


### -field Version

The version number of the <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure that follows this member. For a <a href="..\wdm\ns-wdm-_dma_transfer_info_v1.md">DMA_TRANSFER_INFO_V1</a> structure, set this member to DMA_TRANSFER_INFO_VERSION1 before calling the <a href="..\wdm\nc-wdm-pget_dma_transfer_info.md">GetDmaTransferInfo</a> routine.


## -remarks


A device driver calls the <a href="..\wdm\nc-wdm-pget_dma_transfer_info.md">GetDmaTransferInfo</a> routine to obtain a <b>DMA_TRANSFER_INFO</b> structure that describes the allocation requirements for the scatter/gather list to use in a DMA transfer.

The unnamed union in this structure contains a <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure. The <b>Version</b> member indicates which version of the <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure is contained in the union. Currently, only version 1 is supported.



## -see-also

<a href="..\wdm\nc-wdm-pget_dma_transfer_info.md">GetDmaTransferInfo</a>

<a href="..\wdm\ns-wdm-_dma_transfer_info_v1.md">DMA_TRANSFER_INFO_V1</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DMA_TRANSFER_INFO structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

