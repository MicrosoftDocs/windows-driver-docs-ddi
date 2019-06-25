---
UID: NF:sercx.SerCx2SystemDmaTransmitCreate
title: SerCx2SystemDmaTransmitCreate function (sercx.h)
description: The SerCx2SystemDmaTransmitCreate method creates a SerCx2 system-DMA-transmit object, which version 2 of the serial framework extension (SerCx2) uses to perform system-DMA-transmit transactions.
old-location: serports\sercx2systemdmatransmitcreate.htm
tech.root: serports
ms.assetid: CD0FA4A2-9E09-4F76-A332-858CC5D61651
ms.date: 04/23/2018
ms.keywords: 2/SerCx2SystemDmaTransmitCreate, SerCx2SystemDmaTransmitCreate, SerCx2SystemDmaTransmitCreate method [Serial Ports], serports.sercx2systemdmatransmitcreate
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- 2.0\Sercx.h
api_name:
- SerCx2SystemDmaTransmitCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCx2SystemDmaTransmitCreate function


## -description


The <b>SerCx2SystemDmaTransmitCreate</b> method creates a SerCx2 system-DMA-transmit object, which version 2 of the serial framework extension (SerCx2) uses to perform system-DMA-transmit transactions.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>.


### -param SystemDmaTransmitConfig [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a> structure. Before calling this method, the caller must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2_system_dma_transmit_config_init">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</a> function to initialize the structure. This structure contains pointers to a set of event callback routines that are implemented by the serial controller driver. SerCx2 calls these functions to perform system-DMA-transmit transactions.


### -param Attributes [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes to assign to the new system-DMA-transmit object. Before calling this method, the caller must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize the structure. This parameter is optional and can be specified as WDF_NO_OBJECT_ATTRIBUTES if the serial controller driver does not need to assign attributes to the object. For more information, see Remarks.


### -param SystemDmaTransmit [out]

A pointer to a location to which this method writes a <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to the newly created system-DMA-transmit object. SerCx2 and the serial controller driver use this handle in subsequent calls to refer to this object.


## -returns



This method returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
A system-DMA-transmit object already exists from a previous <b>SerCx2SystemDmaTransmitCreate</b> call; or a custom-transmit object exists from a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2customtransmitcreate">SerCx2CustomTransmitCreate</a> method; or a custom-receive object exists from a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2customreceivecreate">SerCx2CustomReceiveCreate</a> method; or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> has not yet been called to create a PIO-transmit object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <i>Config</i>-><b>Size</b> value does not equal <b>sizeof</b>(<b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</b>).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A parameter value is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient resources are available to create the system-DMA-transmit object.

</td>
</tr>
</table>
 




## -remarks



Your serial controller driver can this method to create a system-DMA-transmit object. SerCx2 uses this object to perform system-DMA-transmit transactions, which are transactions that use the system DMA controller to write data to the serial controller to be transmitted.

Typically, a serial controller driver calls <b>SerCx2SystemDmaTransmitCreate</b> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function. This function receives a list of hardware resources, which can include system DMA channels.

The serial controller driver must successfully call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> methods before calling <b>SerCx2SystemDmaTransmitCreate</b>.

Before calling <b>SerCx2SystemDmaTransmitCreate</b>, the serial controller driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2_system_dma_transmit_config_init">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</a> function to initialize the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a> structure pointed to by <i>SystemDmaTransmitConfig</i>. This function sets the following members of the structure to zero:

<ul>
<li><b>MaximumScatterGatherFragments</b></li>
<li><b>MinimumTransferUnitOverride</b></li>
<li><b>DmaAlignment</b></li>
<li><b>MinimumTransactionLength</b></li>
<li><b>Exclusive</b></li>
</ul>
If necessary, the serial controller driver can set any of these members to nonzero values after the initialization function returns. However, for convenience, <b>SerCx2SystemDmaTransmitCreate</b> uses the following default values if these members are zero:

<ul>
<li>If <b>MaximumScatterGatherFragments</b> is zero, SerCx2 sets the maximum number of elements in a scatter/gather list to ((ULONG)-1).</li>
<li>If <b>MinimumTransferUnitOverride</b> is zero, SerCx2 sets the minimum transfer unit to its default value, which is specified in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure for the system DMA controller. For more information about this structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablerwdmgetdmaadapter">WdfDmaEnablerWdmGetDmaAdapter</a>.</li>
<li>If <b>DmaAlignment</b> is zero, SerCx2 sets the alignment value to the minimum transfer unit. If <b>MinimumTransferUnitOverride</b> is zero, the default minimum transfer unit is used.</li>
<li>If <b>MinimumTransactionLength</b> is zero, SerCx2 sets the minimum transaction length to one byte.</li>
<li>If <b>Exclusive</b> is zero (<b>FALSE</b>), exclusive mode is disabled.</li>
</ul>
If the calling driver sets <b>Exclusive</b> to <b>TRUE</b>, the <b>MinimumTransferUnitOverride</b>, <b>DmaAlignment</b>, and <b>MinimumTransactionLength</b> members must be zero. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>.

If the specified combination of implemented callback functions is not valid, <b>SerCx2SystemDmaTransmitCreate</b> fails and returns STATUS_INVALID_PARAMETER. The driver must implement either all three or none of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo">EvtSerCx2SystemDmaTransmitDrainFifo</a>,  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo">EvtSerCx2SystemDmaTransmitPurgeFifo</a> functions.

As an option, a serial controller driver can use the <i>Attributes</i> parameter to create a context for the system-DMA-transmit object, and to supply pointers to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> functions that are called to prepare the object for deletion. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>.

If the <i>Attributes</i> parameter points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure, the caller must not overwrite the values that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> initialization function writes to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure.

For more information about creating system-DMA-transmit objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>. For more information about system-DMA-transmit transactions, see <a href="https://docs.microsoft.com/previous-versions/dn265338(v=vs.85)">SerCx2 System-DMA-Transmit Transactions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_transmit_cleanup_transaction">EvtSerCx2SystemDmaTransmitCleanupTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo">EvtSerCx2SystemDmaTransmitDrainFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_transmit_initialize_transaction">EvtSerCx2SystemDmaTransmitInitializeTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo">EvtSerCx2SystemDmaTransmitPurgeFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2_system_dma_transmit_config_init">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablerwdmgetdmaadapter">WdfDmaEnablerWdmGetDmaAdapter</a>
 

 

