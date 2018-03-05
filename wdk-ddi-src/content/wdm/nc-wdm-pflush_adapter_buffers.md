---
UID: NC:wdm.PFLUSH_ADAPTER_BUFFERS
title: PFLUSH_ADAPTER_BUFFERS
author: windows-driver-content
description: The FlushAdapterBuffers routine flushes any data remaining in the system DMA controller's internal cache or in a bus-master adapter's internal cache at the end of a DMA transfer operation.
old-location: kernel\flushadapterbuffers.htm
old-project: kernel
ms.assetid: cd6cf9af-c600-465c-b8f3-ca0f972780a5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: FlushAdapterBuffers, FlushAdapterBuffers callback function [Kernel-Mode Driver Architecture], PFLUSH_ADAPTER_BUFFERS, kdma_97ac2c04-7f7e-495d-b846-d4f0ea27bdac.xml, kernel.flushadapterbuffers, wdm/FlushAdapterBuffers
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
-	FlushAdapterBuffers
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PFLUSH_ADAPTER_BUFFERS callback


## -description


The <b>FlushAdapterBuffers</b> routine flushes any data remaining in the system DMA controller's internal cache or in a bus-master adapter's internal cache at the end of a DMA transfer operation.


## -prototype


````
PFLUSH_ADAPTER_BUFFERS FlushAdapterBuffers;

BOOLEAN FlushAdapterBuffers(
  _In_ PDMA_ADAPTER DmaAdapter,
  _In_ PMDL         Mdl,
  _In_ PVOID        MapRegisterBase,
  _In_ PVOID        CurrentVa,
  _In_ ULONG        Length,
  _In_ BOOLEAN      WriteToDevice
)
{ ... }
````


## -parameters




### -param DmaAdapter [in]

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


### -param Mdl [in]

Pointer to the MDL that describes the buffer previously passed in the driver's call to <b>MapTransfer</b>.


### -param MapRegisterBase [in]

Specifies the map registers allocated for the DMA operation.  The system passes this value  to the driver's <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine.


### -param CurrentVa [in]

Pointer to the current virtual address in the buffer, described by the <i>Mdl</i>, where the I/O operation occurred. This value must be the same as the initial <i>CurrentVa</i> value passed to <a href="..\wdm\nc-wdm-pmap_transfer.md">MapTransfer</a>.


### -param Length [in]

Specifies the length, in bytes, of the buffer.


### -param WriteToDevice [in]

Specifies the direction of the DMA transfer operation: <b>TRUE</b> for a transfer from a buffer in system memory to the driver's device.


## -returns



<b>FlushAdapterBuffers</b> returns <b>TRUE</b> if any data remaining in the DMA controller's or bus-master adapter's internal cache has been successfully flushed into system memory or out to the device.




## -remarks



<b>FlushAdapterBuffers</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>.

To ensure that a DMA transfer is complete, every driver that performs DMA operations must call <b>FlushAdapterBuffers</b> before completing the IRP that requested the DMA transfer and before freeing the map registers.

A driver can get the initial <i>CurrentVa</i> for the start of a packet-based DMA transfer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>. However, the value returned is an index into the <i>Mdl</i>, rather than a valid virtual address. If the driver must split a large transfer request into more than one DMA operation, it must update <i>CurrentVa</i> and <i>Length</i> for each DMA operation. 




## -see-also

<a href="..\wdm\nf-wdm-keflushiobuffers.md">KeFlushIoBuffers</a>



<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>



<a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>



<a href="..\wdm\nc-wdm-pmap_transfer.md">MapTransfer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>



<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>



<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PFLUSH_ADAPTER_BUFFERS callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

