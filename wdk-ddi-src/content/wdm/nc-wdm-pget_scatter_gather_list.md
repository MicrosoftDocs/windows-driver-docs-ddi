---
UID: NC:wdm.PGET_SCATTER_GATHER_LIST
title: PGET_SCATTER_GATHER_LIST
author: windows-driver-content
description: The GetScatterGatherList routine prepares the system for a DMA scatter/gather operation on behalf of the target device object, through either the system DMA controller or a bus-master adapter.
old-location: kernel\getscattergatherlist.htm
old-project: kernel
ms.assetid: 44c597ed-a41e-4170-b75b-dcd61aa70350
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.getscattergatherlist, GetScatterGatherList, GetScatterGatherList callback function [Kernel-Mode Driver Architecture], GetScatterGatherList, PGET_SCATTER_GATHER_LIST, PGET_SCATTER_GATHER_LIST, ntddk/GetScatterGatherList, kdma_b451cb34-7181-4272-a1ef-0c8fc233a7fd.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ntddk.h
apiname:
-	GetScatterGatherList
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PGET_SCATTER_GATHER_LIST callback


## -description


The <b>GetScatterGatherList</b> routine prepares the system for a DMA scatter/gather operation on behalf of the target device object, through either the system DMA controller or a bus-master adapter. 


## -prototype


````
PGET_SCATTER_GATHER_LIST GetScatterGatherList;

NTSTATUS GetScatterGatherList(
  _In_ PDMA_ADAPTER         DmaAdapter,
  _In_ PDEVICE_OBJECT       DeviceObject,
  _In_ PMDL                 Mdl,
  _In_ PVOID                CurrentVa,
  _In_ ULONG                Length,
  _In_ PDRIVER_LIST_CONTROL ExecutionRoutine,
  _In_ PVOID                Context,
  _In_ BOOLEAN              WriteToDevice
)
{ ... }
````


## -parameters




### -param DmaAdapter [in]

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


### -param DeviceObject [in]

Pointer to the device object that represents the target device for the DMA operation.


### -param Mdl [in]

Pointer to the MDL that describes the buffer at <i>MdlAddress</i> in the current IRP.


### -param CurrentVa [in]

Pointer to the current virtual address in the MDL for the buffer to be mapped for a DMA transfer operation.


### -param Length [in]

Specifies the length, in bytes, to be mapped. 


### -param ExecutionRoutine [in]

Pointer to a driver-supplied <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine, which is called at DISPATCH_LEVEL when the system DMA controller or bus-master adapter is available.


### -param Context [in]

Pointer to the driver-determined context passed to the driver's <i>AdapterListControl</i> routine when it is called. 


### -param WriteToDevice [in]

Indicates the direction of the DMA transfer: <b>TRUE</b> for a transfer from the buffer to the device, and <b>FALSE</b> otherwise. 


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
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The routine could not allocate sufficient memory or the number of map registers required for the transfer is larger than the value returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer is too small for the requested transfer.

</td>
</tr>
</table>
 




## -remarks



The <b>GetScatterGatherList</b> routine dynamically allocates a buffer to hold the scatter/gather list. For possible NTSTATUS values if the buffer allocation fails, see the return value.

<b>GetScatterGatherList</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>.

As soon as the appropriate DMA channel and any necessary map registers are available, <b>GetScatterGatherList</b> creates a scatter/gather list, initializes the map registers, and then calls the driver-supplied <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine to carry out the I/O operation.

<b>GetScatterGatherList</b> combines the actions of the <a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a> and <a href="..\wdm\nc-wdm-pmap_transfer.md">MapTransfer</a> routines for drivers that perform scatter/gather DMA. <b>GetScatterGatherList</b> determines how many map registers are required for the transfer, allocates the map registers, maps the buffers for DMA, and fills in the scatter/gather list. It then calls the supplied <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine, passing a pointer to the scatter/gather list in <i>ScatterGather</i>. The driver should retain this pointer for use when calling <a href="..\wdm\nc-wdm-pput_scatter_gather_list.md">PutScatterGatherList</a>. Note that <b>GetScatterGatherList</b> does not have the queuing restrictions that apply to <b>AllocateAdapterChannel</b>.

In its <i>AdapterListControl</i> routine, the driver should perform the I/O. On return from the driver-supplied routine, <b>GetScatterGatherList</b> keeps the map registers but frees the DMA adapter structure. The driver must call <b>PutScatterGatherList</b> (which flushes the buffers) before it can access the data in the buffer.

This routine can handle chained MDLs, provided that the total number of map registers required by all chained MDLs does not exceed the number of map registers that are available. 




## -see-also

<a href="..\wdm\nc-wdm-pput_scatter_gather_list.md">PutScatterGatherList</a>



<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



<a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>



<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>



<a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PGET_SCATTER_GATHER_LIST callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

