---
UID: NC:wdm.PMAP_TRANSFER
title: PMAP_TRANSFER
author: windows-driver-content
description: The MapTransfer routine sets up map registers for an adapter object to map a DMA transfer from a locked-down buffer.
old-location: kernel\maptransfer.htm
old-project: kernel
ms.assetid: 50126ab8-3094-497e-96f8-e41255d275e3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.maptransfer, MapTransfer, MapTransfer callback function [Kernel-Mode Driver Architecture], MapTransfer, PMAP_TRANSFER, PMAP_TRANSFER, wdm/MapTransfer, kdma_4bc30c1d-1d83-424f-9c58-cd92c5e9d331.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wdm.h
apiname:
-	MapTransfer
product: Windows
targetos: Windows
req.typenames: "*PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME"
req.product: Windows 10 or later.
---

# PMAP_TRANSFER callback


## -description


The <b>MapTransfer</b> routine sets up map registers for an adapter object to map a DMA transfer from a locked-down buffer.


## -prototype


````
PMAP_TRANSFER MapTransfer;

PHYSICAL_ADDRESS MapTransfer(
  _In_    PDMA_ADAPTER DmaAdapter,
  _In_    PMDL         Mdl,
  _In_    PVOID        MapRegisterBase,
  _In_    PVOID        CurrentVa,
  _Inout_ PULONG       Length,
  _In_    BOOLEAN      WriteToDevice
)
{ ... }
````


## -parameters




### -param DmaAdapter [in]

Pointer to the DMA adapter object returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> and previously passed to <a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a> for the current IRP's transfer request. 


### -param Mdl [in]

Pointer to one of the following: the MDL that describes the buffer at <b>MdlAddress</b> in the current IRP or the MDL that describes the common buffer set up by the driver of a subordinate device (auto-initialize mode).


### -param MapRegisterBase [in]

Specifies the map registers allocated for the DMA operation.  The system passes this value  to the driver's <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine. 


### -param CurrentVa [in]

Pointer to the current virtual address of the data to be transferred for a DMA transfer operation.


### -param Length [in, out]

Specifies the length, in bytes, to be mapped. If the driver indicated that its device was a bus master with scatter/gather support when it called <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>, the value of <i>Length</i> on return from <b>MapTransfer</b> indicates how many bytes were mapped. Otherwise, the input and output values of <i>Length</i> are identical. 


### -param WriteToDevice [in]

Indicates the direction of the transfer operation: <b>TRUE</b> for a transfer from the locked-down buffer to the device. 


## -returns



<b>MapTransfer</b> returns the logical address of the region mapped, which the driver of a bus-master adapter can use. Drivers of devices that use a system DMA controller cannot use this value and should ignore it. 




## -remarks



<b>MapTransfer</b><u> is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          </u><a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a><u> structure</u>. Drivers obtain the address of this routine by calling <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>. 

The <i>DmaAdapter</i> must have already been allocated as a result of the driver's preceding call to <a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>.

The number of map registers that can be set up cannot exceed the maximum returned when the driver called <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>.

A driver can get the initial <i>CurrentVa</i> for the start of a packet-based DMA transfer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>. However, the value returned is an index into the <i>Mdl</i>, rather than a valid virtual address. If the driver must split a large transfer request into more than one DMA operation, it must update <i>CurrentVa</i> and <i>Length</i> for each DMA operation.

The driver of a bus-master device with scatter/gather support can use the returned logical address and updated <i>Length</i> value to build a scatter/gather list, calling <b>MapTransfer</b> repeatedly until it has used all available map registers for the transfer operation. However, such a driver could more simply use the <a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a> routine. 




## -see-also

<a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>



<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>





<a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>



<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>



<a href="..\wdm\nc-wdm-pfree_map_registers.md">FreeMapRegisters</a>



<a href="..\wdm\nc-wdm-pfree_adapter_channel.md">FreeAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540562">ADDRESS_AND_SIZE_TO_SPAN_PAGES</a>







<a href="..\wdm\nf-wdm-keflushiobuffers.md">KeFlushIoBuffers</a>



<a href="..\wdm\nc-wdm-pflush_adapter_buffers.md">FlushAdapterBuffers</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PMAP_TRANSFER callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

