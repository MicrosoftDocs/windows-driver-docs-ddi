---
UID: NC:wdm.PPUT_SCATTER_GATHER_LIST
title: PPUT_SCATTER_GATHER_LIST
author: windows-driver-content
description: The PutScatterGatherList routine frees the previously allocated map registers and scatter/gather list used in scatter/gather DMA.
old-location: kernel\putscattergatherlist.htm
old-project: kernel
ms.assetid: e10091c0-0da6-4acd-8104-9d353262836a
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PPUT_SCATTER_GATHER_LIST, PutScatterGatherList, PutScatterGatherList callback function [Kernel-Mode Driver Architecture], kdma_0f73e6d3-bf6c-4f2b-aff9-ae783b2130c5.xml, kernel.putscattergatherlist, ntddk/PutScatterGatherList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows. Not supported in Windows 98 or Windows Me.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch, IrqlDispatch(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ntddk.h
api_name:
-	PutScatterGatherList
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PPUT_SCATTER_GATHER_LIST callback


## -description


The <b>PutScatterGatherList</b> routine frees the previously allocated map registers and scatter/gather list used in scatter/gather DMA. 


## -parameters




### -param DmaAdapter [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


### -param ScatterGather [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563664">SCATTER_GATHER_LIST</a> structure previously returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff546531">GetScatterGatherList</a>. 


### -param WriteToDevice [in]

Indicates the direction of the DMA transfer: specify <b>TRUE</b> for a transfer from the buffer to the device, and <b>FALSE</b> otherwise. 


## -returns



None




## -remarks



<b>PutScatterGatherList</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

Drivers should call <b>PutScatterGatherList</b> after completing scatter/gather I/O. This routine flushes the adapter buffers, frees the map registers, and unmaps and frees the associated MDLs. Additionally, the routine frees the scatter/gather list if it was previously allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff546531">GetScatterGatherList</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546531">GetScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563664">SCATTER_GATHER_LIST</a>
 

 

