---
UID: NC:wdm.PALLOCATE_ADAPTER_CHANNEL
title: PALLOCATE_ADAPTER_CHANNEL
author: windows-driver-content
description: The AllocateAdapterChannel routine prepares the system for a DMA operation on behalf of the target device object, and then calls the driver-supplied AdapterControl routine to carry out the DMA operation.
old-location: kernel\allocateadapterchannel.htm
old-project: kernel
ms.assetid: d3339754-1a54-48f0-90c8-6c7db59fb7cc
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: AllocateAdapterChannel, AllocateAdapterChannel callback function [Kernel-Mode Driver Architecture], PALLOCATE_ADAPTER_CHANNEL, kdma_b2d02da0-ab8f-4fc3-a7a5-a981920c071d.xml, kernel.allocateadapterchannel, wdm/AllocateAdapterChannel
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
-	AllocateAdapterChannel
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PALLOCATE_ADAPTER_CHANNEL callback


## -description


The <b>AllocateAdapterChannel</b> routine prepares the system for a DMA operation on behalf of the target device object, and then calls the driver-supplied <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine to carry out the DMA operation. 


## -prototype


````
PALLOCATE_ADAPTER_CHANNEL AllocateAdapterChannel;

NTSTATUS AllocateAdapterChannel(
  _In_ PDMA_ADAPTER    DmaAdapter,
  _In_ PDEVICE_OBJECT  DeviceObject,
  _In_ ULONG           NumberOfMapRegisters,
  _In_ PDRIVER_CONTROL ExecutionRoutine,
  _In_ PVOID           Context
)
{ ... }
````


## -parameters




### -param DmaAdapter [in]

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


### -param DeviceObject [in]

Pointer to the device object that represents the target device for a requested DMA operation.


### -param NumberOfMapRegisters [in]

Specifies the number of map registers to be used in the transfer. This value is the lesser of the number of map registers needed to satisfy the current transfer request, and the number of available map registers returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>. 


### -param ExecutionRoutine [in]

Pointer to a driver-supplied <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine. The routine is called when the system DMA controller or bus-master adapter becomes available.


### -param Context [in]

Pointer to the driver-determined context to be passed to the <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine. 


## -returns



This routine can return one of the following NTSTATUS values. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The adapter channel has been allocated. The system will call the <i>AdapterControl</i> routine once the DMA operation can begin.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The <i>NumberOfMapRegisters</i> is larger than the value returned by <b>IoGetDmaAdapter</b>. The <i>AdapterControl</i> routine will not be called.

</td>
</tr>
</table>
 




## -remarks



<b>AllocateAdapterChannel</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>.

A driver calls the <b>AllocateAdapterControl</b> routine to register an <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine that performs a DMA operation for the driver. The <i>AdapterControl</i> routine carries out a DMA operation using either the system DMA controller or a bus-master adapter.

If the DMA operation can be performed immediately, the system immediately calls <i>AdapterControl</i>. If the system DMA controller or bus-master adapter is currently in use, <b>AllocateAdapterChannel</b> queues the <i>AdapterControl</i> until the adapter becomes available. In either case, <b>AllocateAdapterChannel</b> returns STATUS_SUCCESS.

If the system lacks the resources to perform the DMA operation, <b>AllocateAdapterChannel</b> returns STATUS_INSUFFICIENT_RESOURCES. In that case, <i>AdapterControl</i> is not queued, and the driver should complete the current IRP with the appropriate error code (such as STATUS_INSUFFICIENT_RESOURCES).

This routine reserves exclusive access to a DMA controller channel and map registers for the one or more DMA operations that are required to satisfy the current IRP's transfer request for the specified device.

Only one DMA request can be queued for a device object at any one time. Therefore, the driver should not call <b>AllocateAdapterChannel</b> again for another DMA operation on the same device object until the <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine has completed execution. In addition, a driver must not call <b>AllocateAdapterChannel</b> from within its <i>AdapterControl</i> routine.

The system passes the value of the <b>CurrentIrp</b> member of <i>DeviceObject</i> as the <i>Irp</i> parameter of <i>AdapterControl</i>. If <b>AllocateAdapterChannel</b> is called from a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine, this is guaranteed to point to the IRP that <i>StartIo</i> was called to process. Otherwise, to use the <i>Irp</i> parameter of <i>AdapterControl</i>, the driver must set <b>CurrentIrp</b> to point to the current IRP before calling <b>AllocateAdapterChannel</b>. 




## -see-also

<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



<a href="..\wdm\nc-wdm-pflush_adapter_buffers.md">FlushAdapterBuffers</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>



<a href="..\wdm\nc-wdm-pfree_adapter_channel.md">FreeAdapterChannel</a>



<a href="..\wdm\nc-wdm-pmap_transfer.md">MapTransfer</a>



<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>



<a href="..\wdm\nc-wdm-pread_dma_counter.md">ReadDmaCounter</a>



<a href="..\wdm\nc-wdm-pfree_map_registers.md">FreeMapRegisters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PALLOCATE_ADAPTER_CHANNEL callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

