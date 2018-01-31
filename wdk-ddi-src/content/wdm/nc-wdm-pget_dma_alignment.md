---
UID: NC:wdm.PGET_DMA_ALIGNMENT
title: PGET_DMA_ALIGNMENT
author: windows-driver-content
description: The GetDmaAlignment routine returns the alignment requirements of the DMA system.
old-location: kernel\getdmaalignment.htm
old-project: kernel
ms.assetid: c96ed5ad-34d8-4530-8d00-483e5aee7261
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.getdmaalignment, GetDmaAlignment, GetDmaAlignment callback function [Kernel-Mode Driver Architecture], GetDmaAlignment, PGET_DMA_ALIGNMENT, PGET_DMA_ALIGNMENT, wdm/GetDmaAlignment, kdma_3b830c2d-6c3d-477c-b781-c9d1a7dbe5bf.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with  Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch
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
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	GetDmaAlignment
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PGET_DMA_ALIGNMENT callback


## -description


The <b>GetDmaAlignment</b> routine returns the alignment requirements of the DMA system.


## -prototype


````
PGET_DMA_ALIGNMENT GetDmaAlignment;

ULONG GetDmaAlignment(
  _In_ PDMA_ADAPTER DmaAdapter
)
{ ... }
````


## -parameters




#### - DmaAdapter [in]

A pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller. 


## -returns


<b>GetDmaAlignment</b> returns the alignment requirements, in bytes, of the DMA system.  The starting address and length of DMA buffers must be a multiple of this value.



## -remarks


<b>GetDmaAlignment</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

A driver can call this routine to determine alignment requirements for DMA buffers it allocates. The returned value should be used to set the <b>AlignmentRequirement</b> field in the device object. A driver may need to increase this value because of additional hardware device restrictions.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547807">Initializing a Device Object</a>. 



## -see-also

<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>

<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PGET_DMA_ALIGNMENT callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

