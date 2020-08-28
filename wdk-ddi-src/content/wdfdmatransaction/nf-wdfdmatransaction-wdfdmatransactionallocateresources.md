---
UID: NF:wdfdmatransaction.WdfDmaTransactionAllocateResources
title: WdfDmaTransactionAllocateResources function (wdfdmatransaction.h)
description: The WdfDmaTransactionAllocateResources method reserves a single-packet or system-mode DMA enabler for exclusive (and repeated) use with the specified transaction object.
old-location: wdf\wdfdmatransactionallocateresources.htm
tech.root: wdf
ms.assetid: 69D251D9-1B33-49FD-8D48-EFCBD6640632
ms.date: 02/26/2018
keywords: ["WdfDmaTransactionAllocateResources function"]
ms.keywords: WdfDmaTransactionAllocateResources, WdfDmaTransactionAllocateResources method, kmdf.wdfdmatransactionallocateresources, wdf.wdfdmatransactionallocateresources, wdfdmatransaction/WdfDmaTransactionAllocateResources
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDmaTransactionAllocateResources
 - wdfdmatransaction/WdfDmaTransactionAllocateResources
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDmaTransactionAllocateResources
---

# WdfDmaTransactionAllocateResources function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>


   The <b>WdfDmaTransactionAllocateResources</b> method reserves a single-packet or system-mode DMA enabler for exclusive (and repeated) use with the specified transaction object. The driver can initialize and initiate the transaction multiple times while holding reserved resources.

## -parameters

### -param DmaTransaction 

[in]
A handle to the DMA transaction object for which DMA resources should be reserved.

### -param DmaDirection 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_direction">WDF_DMA_DIRECTION</a>-typed value specifying the DMA transfer direction for which the resources are being reserved. If the driver did not specify a duplex profile, the framework ignores this value.

### -param RequiredMapRegisters 

[in]
The number of map registers the driver wants to reserve. If zero, the framework derives the required number of map registers from the initialized transaction.

### -param EvtReserveDmaFunction 

[in]
A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_reserve_dma">EvtReserveDma</a> event callback function.

### -param EvtReserveDmaContext 

[in]
A pointer to a buffer containing the context to be provided to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_reserve_dma">EvtReserveDma</a> event callback function.

## -returns

<b>WdfDmaTransactionAllocateResources</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>DmaDirection</i> parameter contains an invalid value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The number of map register requests exceeds the number assigned to the enabler, or the driver previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetimmediateexecution">WdfDmaTransactionSetImmediateExecution</a> and the resources needed for the request are unavailable.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
DMA version 3 or later is not enabled, or the driver called this method for a scatter-gather DMA enabler.

</td>
</tr>
</table>

## -remarks

<b>WdfDmaTransactionAllocateResources</b> sends a request for map registers to the system DMA engine.  When the request has been fulfilled, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_reserve_dma">EvtReserveDma</a> event callback function. For more information about reserving resources, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reserving-dma-resources">Reserving DMA Resources</a>.

Framework-based drivers typically call <b>WdfDmaTransactionAllocateResources</b> from within an <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">I/O request handler</a>.  A driver can also call <b>WdfDmaTransactionAllocateResources</b> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function, after creating a DMA enabler object.

  When called with a scatter/gather DMA enabler, <b>WdfDmaTransactionAllocateResources</b> causes a verifier bug check.

The driver must create the transaction specified by <i>DmaTransaction</i> prior to calling <b>WdfDmaTransactionAllocateResources</b>. After calling <b>WdfDmaTransactionAllocateResources</b>, the driver initializes and initiates the transaction. The driver can reinitialize and reinitiate the same transaction object multiple times, avoiding the delay that would otherwise occur between transactions as map registers were freed back to the HAL and then reallocated.

A driver could call <b>WdfDmaTransactionAllocateResources</b> in the following situations:

<ul>
<li>The driver receives a set of DMA channels in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function.  In <i>EvtDevicePrepareHardware</i>, the driver initializes a DMA transaction and calls <b>WdfDmaTransactionAllocateResources</b> to reserve the enabler for exclusive use with this transaction. Alternatively, the driver can call <b>WdfDmaTransactionAllocateResources</b> from a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handler</a> and then initiate the transaction multiple times.</li>
<li>The driver needs to perform a series of transactions on the enabler. The driver reserves the enabler, initializes and initiates multiple transactions using the same transaction object, and then releases the enabler.</li>
</ul>
Before calling <b>WdfDmaTransactionAllocateResources</b>, the driver must determine the number of map registers needed for any transaction that it will initiate using this reservation. To do so, the driver can call either the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">ADDRESS_AND_SIZE_TO_SPAN_PAGES</a> macro or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactiongettransferinfo">WdfDmaTransactionGetTransferInfo</a>.

 When calling <b>WdfDmaTransactionAllocateResources</b>, the driver should not request more map registers than it requested when it created the enabler.

To call <b>WdfDmaTransactionAllocateResources</b> in a non-blocking manner, the driver should first call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetimmediateexecution">WdfDmaTransactionSetImmediateExecution</a>.

<b>WdfDmaTransactionAllocateResources</b> requires DMA version 3.
 To select DMA version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> to 3.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionexecute">WdfDmaTransactionExecute</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionfreeresources">WdfDmaTransactionFreeResources</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionsetimmediateexecution">WdfDmaTransactionSetImmediateExecution</a>

