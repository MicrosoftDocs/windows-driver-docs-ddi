---
UID: NC:wdm.PFREE_MAP_REGISTERS
title: PFREE_MAP_REGISTERS
author: windows-driver-content
description: The FreeMapRegisters routine releases a set of map registers that were saved from a call to AllocateAdapterChannel.
old-location: kernel\freemapregisters.htm
tech.root: kernel
ms.assetid: 0326229f-cf02-4368-bc32-7fbed118714b
ms.date: 4/30/2018
ms.keywords: FreeMapRegisters, FreeMapRegisters callback function [Kernel-Mode Driver Architecture], PFREE_MAP_REGISTERS, PFREE_MAP_REGISTERS callback, kdma_039f59c4-101e-40c2-bf2e-a0faa7c11032.xml, kernel.freemapregisters, wdm/FreeMapRegisters
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
-	FreeMapRegisters
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFREE_MAP_REGISTERS callback function


## -description


The <b>FreeMapRegisters</b> routine releases a set of map registers that were saved from a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>. 


## -parameters




### -param DmaAdapter [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


### -param MapRegisterBase [in]

Specifies the map registers allocated for the DMA operation.  The system passes this value  to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540504">AdapterControl</a> routine.


### -param NumberOfMapRegisters [in]

Specifies the number of map registers to be released. This value must match the number specified in an earlier call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>.


## -returns



None




## -remarks



<b>FreeMapRegisters</b>
           is not a system routine that can be called directly by name. This routine is only callable by pointer from the address returned in a 
          <a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

When the driver of a bus-master device has completed the current packet-based DMA transfer request, it calls <b>FreeMapRegisters</b> to release the map registers previously allocated by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a> and retained because its <i>AdapterControl</i> routine returned <b>DeallocateObjectKeepRegisters</b>. The driver must call <b>FreeMapRegisters</b> after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554402">MapTransfer</a>
 

 

