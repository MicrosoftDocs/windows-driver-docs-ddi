---
UID: NC:wdm.PFREE_ADAPTER_CHANNEL
title: PFREE_ADAPTER_CHANNEL
author: windows-driver-content
description: The FreeAdapterChannel routine releases the system DMA controller when a driver has completed all DMA operations necessary to satisfy the current IRP.
old-location: kernel\freeadapterchannel.htm
old-project: kernel
ms.assetid: 916531dd-4768-436a-910c-07d49924ac48
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: FreeAdapterChannel, FreeAdapterChannel callback function [Kernel-Mode Driver Architecture], PFREE_ADAPTER_CHANNEL, PFREE_ADAPTER_CHANNEL callback, kdma_f48025a6-96a2-4bdd-8b48-6c939bdf738b.xml, kernel.freeadapterchannel, wdm/FreeAdapterChannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
-	wdm.h
api_name:
-	FreeAdapterChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFREE_ADAPTER_CHANNEL callback function


## -description


The <b>FreeAdapterChannel</b> routine releases the system DMA controller when a driver has completed all DMA operations necessary to satisfy the current IRP.


## -parameters




### -param DmaAdapter [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>  structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


## -returns



None




## -remarks



<b>FreeAdapterChannel</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

After a driver has transferred all the data and called <a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>, it calls <b>FreeAdapterChannel</b> to release the system DMA controller that was previously allocated with a call to <b>AllocateAdapterChannel</b>.

<b>FreeAdapterChannel</b> frees any map registers that were allocated by an earlier call to <b>AllocateAdapterChannel</b>. A driver calls this routine only if its <a href="https://msdn.microsoft.com/library/windows/hardware/ff540504">AdapterControl</a> routine returns <b>KeepObject</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546513">FreeMapRegisters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554402">MapTransfer</a>
 

 

