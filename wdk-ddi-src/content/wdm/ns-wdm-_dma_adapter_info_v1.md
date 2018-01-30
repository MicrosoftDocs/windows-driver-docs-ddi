---
UID: NS:wdm._DMA_ADAPTER_INFO_V1
title: "_DMA_ADAPTER_INFO_V1"
author: windows-driver-content
description: The DMA_ADAPTER_INFO_V1 structure describes the capabilities of the system DMA controller that is represented by an adapter object.
old-location: kernel\dma_adapter_info_v1.htm
old-project: kernel
ms.assetid: 5BB089B8-4384-450D-BC81-9D9D068CF4EB
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PDMA_ADAPTER_INFO_V1 structure pointer [Kernel-Mode Driver Architecture], _DMA_ADAPTER_INFO_V1, wdm/PDMA_ADAPTER_INFO_V1, PDMA_ADAPTER_INFO_V1, DMA_ADAPTER_INFO_V1 structure [Kernel-Mode Driver Architecture], wdm/DMA_ADAPTER_INFO_V1, DMA_ADAPTER_INFO_V1, *PDMA_ADAPTER_INFO_V1, kernel.dma_adapter_info_v1
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
-	DMA_ADAPTER_INFO_V1
product: Windows
targetos: Windows
req.typenames: DMA_ADAPTER_INFO_V1, *PDMA_ADAPTER_INFO_V1
req.product: Windows 10 or later.
---

# _DMA_ADAPTER_INFO_V1 structure


## -description



The <b>DMA_ADAPTER_INFO_V1</b> structure describes the capabilities of the system DMA controller that is represented by an adapter object.




## -syntax


````
typedef struct _DMA_ADAPTER_INFO_V1 {
  ULONG ReadDmaCounterAvailable;
  ULONG ScatterGatherLimit;
  ULONG DmaAddressWidth;
  ULONG Flags;
  ULONG MinimumTransferUnit;
} DMA_ADAPTER_INFO_V1, *PDMA_ADAPTER_INFO_V1;
````


## -struct-fields




### -field ReadDmaCounterAvailable

Whether the counter value in each DMA channel can be read. This member is <b>TRUE</b> if the counter can be read, and is <b>FALSE</b> if it cannot be read.


### -field ScatterGatherLimit

The maximum number of elements in a scatter/gather list that the DMA controller can process in a single scatter/gather DMA transfer.


### -field DmaAddressWidth

The memory address width, in bits, of the DMA controller. The width is expressed as the number of bits in a DMA address. If the DMA address width is less than the memory address width, the platform hardware drives the remaining, high-order memory address bits to zero during a DMA transfer.


### -field Flags

A set of flags that describe the capabilities of the DMA adapter. No flags are currently defined for this member.


### -field MinimumTransferUnit

The size, in bytes, of the minimum transfer unit. The number of bytes specified by an element in a scatter/gather list must be an integer multiple of the minimum transfer unit.


## -remarks


The <b>V1</b> member of the <a href="..\wdm\ns-wdm-_dma_adapter_info.md">DMA_ADAPTER_INFO</a> structure is a structure of type <b>DMA_ADAPTER_INFO_V1</b>.

A driver calls <a href="..\wdm\nc-wdm-pget_dma_adapter_info.md">GetDmaAdapterInfo</a> to obtain information about the hardware capabilities of a system DMA channel. <b>GetDmaAdapterInfo</b> writes this information into the <b>V1</b> member of a caller-supplied <b>DMA_ADAPTER_INFO</b> structure.



## -see-also

<a href="..\wdm\nc-wdm-pget_dma_adapter_info.md">GetDmaAdapterInfo</a>

<a href="..\wdm\ns-wdm-_dma_adapter_info.md">DMA_ADAPTER_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DMA_ADAPTER_INFO_V1 structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

