---
UID: NC:wdm.PMAP_TRANSFER
title: PMAP_TRANSFER
author: windows-driver-content
description: The MapTransfer routine sets up map registers for an adapter object to map a DMA transfer from a locked-down buffer.
old-location: kernel\maptransfer.htm
old-project: kernel
ms.assetid: 50126ab8-3094-497e-96f8-e41255d275e3
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: MapTransfer, MapTransfer callback function [Kernel-Mode Driver Architecture], PMAP_TRANSFER, kdma_4bc30c1d-1d83-424f-9c58-cd92c5e9d331.xml, kernel.maptransfer, wdm/MapTransfer
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
req.ddi-compliance: IrqlDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdm.h
api_name:
-	MapTransfer
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PMAP_TRANSFER callback


## -description


The <b>MapTransfer</b> routine sets up map registers for an adapter object to map a DMA transfer from a locked-down buffer.


## -parameters




### -param DmaAdapter [in]

Pointer to the DMA adapter object returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> and previously passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a> for the current IRP's transfer request. 


### -param Mdl [in]

Pointer to one of the following: the MDL that describes the buffer at <b>MdlAddress</b> in the current IRP or the MDL that describes the common buffer set up by the driver of a subordinate device (auto-initialize mode).


### -param MapRegisterBase [in]

Specifies the map registers allocated for the DMA operation.  The system passes this value  to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540504">AdapterControl</a> routine. 


### -param CurrentVa [in]

Pointer to the current virtual address of the data to be transferred for a DMA transfer operation.


### -param Length [in, out]

Specifies the length, in bytes, to be mapped. If the driver indicated that its device was a bus master with scatter/gather support when it called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>, the value of <i>Length</i> on return from <b>MapTransfer</b> indicates how many bytes were mapped. Otherwise, the input and output values of <i>Length</i> are identical. 


### -param WriteToDevice [in]

Indicates the direction of the transfer operation: <b>TRUE</b> for a transfer from the locked-down buffer to the device. 


## -returns



<b>MapTransfer</b> returns the logical address of the region mapped, which the driver of a bus-master adapter can use. Drivers of devices that use a system DMA controller cannot use this value and should ignore it. 




## -remarks



<b>MapTransfer</b><u> is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          </u><a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a><u> structure</u>. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>. 

The <i>DmaAdapter</i> must have already been allocated as a result of the driver's preceding call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>.

The number of map registers that can be set up cannot exceed the maximum returned when the driver called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

A driver can get the initial <i>CurrentVa</i> for the start of a packet-based DMA transfer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>. However, the value returned is an index into the <i>Mdl</i>, rather than a valid virtual address. If the driver must split a large transfer request into more than one DMA operation, it must update <i>CurrentVa</i> and <i>Length</i> for each DMA operation.

The driver of a bus-master device with scatter/gather support can use the returned logical address and updated <i>Length</i> value to build a scatter/gather list, calling <b>MapTransfer</b> repeatedly until it has used all available map registers for the transfer operation. However, such a driver could more simply use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546531">GetScatterGatherList</a> routine. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540562">ADDRESS_AND_SIZE_TO_SPAN_PAGES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540575">AllocateCommonBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546507">FreeAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546513">FreeMapRegisters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552041">KeFlushIoBuffers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>
 

 

