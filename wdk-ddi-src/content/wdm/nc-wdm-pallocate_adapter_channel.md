---
UID: NC:wdm.PALLOCATE_ADAPTER_CHANNEL
title: PALLOCATE_ADAPTER_CHANNEL (wdm.h)
description: The AllocateAdapterChannel routine prepares the system for a DMA operation on behalf of the target device object, and then calls the driver-supplied AdapterControl routine to carry out the DMA operation.
old-location: kernel\allocateadapterchannel.htm
tech.root: kernel
ms.assetid: d3339754-1a54-48f0-90c8-6c7db59fb7cc
ms.date: 04/30/2018
ms.keywords: AllocateAdapterChannel, AllocateAdapterChannel callback function [Kernel-Mode Driver Architecture], PALLOCATE_ADAPTER_CHANNEL, PALLOCATE_ADAPTER_CHANNEL callback, kdma_b2d02da0-ab8f-4fc3-a7a5-a981920c071d.xml, kernel.allocateadapterchannel, wdm/AllocateAdapterChannel
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wdm.h
api_name:
- AllocateAdapterChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# PALLOCATE_ADAPTER_CHANNEL callback function


## -description


The <b>AllocateAdapterChannel</b> routine prepares the system for a DMA operation on behalf of the target device object, and then calls the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff540504">AdapterControl</a> routine to carry out the DMA operation. 


## -parameters




### -param DmaAdapter [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


### -param DeviceObject [in]

Pointer to the device object that represents the target device for a requested DMA operation.


### -param NumberOfMapRegisters [in]

Specifies the number of map registers to be used in the transfer. This value is the lesser of the number of map registers needed to satisfy the current transfer request, and the number of available map registers returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>. 


### -param ExecutionRoutine [in]

Pointer to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff540504">AdapterControl</a> routine. The routine is called when the system DMA controller or bus-master adapter becomes available.


### -param Context [in]

Pointer to the driver-determined context to be passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540504">AdapterControl</a> routine. 


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
          <a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

A driver calls the <b>AllocateAdapterControl</b> routine to register an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540504">AdapterControl</a> routine that performs a DMA operation for the driver. The <i>AdapterControl</i> routine carries out a DMA operation using either the system DMA controller or a bus-master adapter.

If the DMA operation can be performed immediately, the system immediately calls <i>AdapterControl</i>. If the system DMA controller or bus-master adapter is currently in use, <b>AllocateAdapterChannel</b> queues the <i>AdapterControl</i> until the adapter becomes available. In either case, <b>AllocateAdapterChannel</b> returns STATUS_SUCCESS.

If the system lacks the resources to perform the DMA operation, <b>AllocateAdapterChannel</b> returns STATUS_INSUFFICIENT_RESOURCES. In that case, <i>AdapterControl</i> is not queued, and the driver should complete the current IRP with the appropriate error code (such as STATUS_INSUFFICIENT_RESOURCES).

This routine reserves exclusive access to a DMA controller channel and map registers for the one or more DMA operations that are required to satisfy the current IRP's transfer request for the specified device.

Only one DMA request can be queued for a device object at any one time. Therefore, the driver should not call <b>AllocateAdapterChannel</b> again for another DMA operation on the same device object until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540504">AdapterControl</a> routine has completed execution. In addition, a driver must not call <b>AllocateAdapterChannel</b> from within its <i>AdapterControl</i> routine.

The system passes the value of the <b>CurrentIrp</b> member of <i>DeviceObject</i> as the <i>Irp</i> parameter of <i>AdapterControl</i>. If <b>AllocateAdapterChannel</b> is called from a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine, this is guaranteed to point to the IRP that <i>StartIo</i> was called to process. Otherwise, to use the <i>Irp</i> parameter of <i>AdapterControl</i>, the driver must set <b>CurrentIrp</b> to point to the current IRP before calling <b>AllocateAdapterChannel</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546507">FreeAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546513">FreeMapRegisters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554402">MapTransfer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560782">ReadDmaCounter</a>
 

 

