---
UID: NF:sercx.SerCx2SystemDmaTransmitCreate
title: SerCx2SystemDmaTransmitCreate function
author: windows-driver-content
description: The SerCx2SystemDmaTransmitCreate method creates a SerCx2 system-DMA-transmit object, which version 2 of the serial framework extension (SerCx2) uses to perform system-DMA-transmit transactions.
old-location: serports\sercx2systemdmatransmitcreate.htm
old-project: serports
ms.assetid: CD0FA4A2-9E09-4F76-A332-858CC5D61651
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/SerCx2SystemDmaTransmitCreate, SerCx2SystemDmaTransmitCreate, SerCx2SystemDmaTransmitCreate method [Serial Ports], serports.sercx2systemdmatransmitcreate
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	2.0\Sercx.h
api_name:
-	SerCx2SystemDmaTransmitCreate
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2SystemDmaTransmitCreate function


## -description


The <b>SerCx2SystemDmaTransmitCreate</b> method creates a SerCx2 system-DMA-transmit object, which version 2 of the serial framework extension (SerCx2) uses to perform system-DMA-transmit transactions.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a>.


### -param SystemDmaTransmitConfig [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265344">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a> structure. Before calling this method, the caller must call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265345">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</a> function to initialize the structure. This structure contains pointers to a set of event callback routines that are implemented by the serial controller driver. SerCx2 calls these functions to perform system-DMA-transmit transactions.


### -param Attributes [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes to assign to the new system-DMA-transmit object. Before calling this method, the caller must call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552402">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize the structure. This parameter is optional and can be specified as WDF_NO_OBJECT_ATTRIBUTES if the serial controller driver does not need to assign attributes to the object. For more information, see Remarks.


### -param SystemDmaTransmit [out]

A pointer to a location to which this method writes a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to the newly created system-DMA-transmit object. SerCx2 and the serial controller driver use this handle in subsequent calls to refer to this object.


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
A system-DMA-transmit object already exists from a previous <b>SerCx2SystemDmaTransmitCreate</b> call; or a custom-transmit object exists from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265256">SerCx2CustomTransmitCreate</a> method; or a custom-receive object exists from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265248">SerCx2CustomReceiveCreate</a> method; or <a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a> has not yet been called to create a PIO-transmit object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <i>Config</i>-&gt;<b>Size</b> value does not equal <b>sizeof</b>(<b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</b>).

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

Typically, a serial controller driver calls <b>SerCx2SystemDmaTransmitCreate</b> from its <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback function. This function receives a list of hardware resources, which can include system DMA channels.

The serial controller driver must successfully call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a> methods before calling <b>SerCx2SystemDmaTransmitCreate</b>.

Before calling <b>SerCx2SystemDmaTransmitCreate</b>, the serial controller driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265345">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</a> function to initialize the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265344">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a> structure pointed to by <i>SystemDmaTransmitConfig</i>. This function sets the following members of the structure to zero:

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
<li>If <b>MinimumTransferUnitOverride</b> is zero, SerCx2 sets the minimum transfer unit to its default value, which is specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure for the system DMA controller. For more information about this structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547020">WdfDmaEnablerWdmGetDmaAdapter</a>.</li>
<li>If <b>DmaAlignment</b> is zero, SerCx2 sets the alignment value to the minimum transfer unit. If <b>MinimumTransferUnitOverride</b> is zero, the default minimum transfer unit is used.</li>
<li>If <b>MinimumTransactionLength</b> is zero, SerCx2 sets the minimum transaction length to one byte.</li>
<li>If <b>Exclusive</b> is zero (<b>FALSE</b>), exclusive mode is disabled.</li>
</ul>
If the calling driver sets <b>Exclusive</b> to <b>TRUE</b>, the <b>MinimumTransferUnitOverride</b>, <b>DmaAlignment</b>, and <b>MinimumTransactionLength</b> members must be zero. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265344">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>.

If the specified combination of implemented callback functions is not valid, <b>SerCx2SystemDmaTransmitCreate</b> fails and returns STATUS_INVALID_PARAMETER. The driver must implement either all three or none of the <a href="https://msdn.microsoft.com/796A6C4B-0C7E-43C5-88BC-C03DAA3869A6">EvtSerCx2SystemDmaTransmitDrainFifo</a>,  <a href="https://msdn.microsoft.com/00B17CBC-FE0E-4611-A41B-42AD833731D3">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a>, and <a href="https://msdn.microsoft.com/79BD2B77-E99A-4CFA-9F7B-AFC984D5F0B3">EvtSerCx2SystemDmaTransmitPurgeFifo</a> functions.

As an option, a serial controller driver can use the <i>Attributes</i> parameter to create a context for the system-DMA-transmit object, and to supply pointers to <a href="https://msdn.microsoft.com/aba2efca-7d1f-4594-af65-13356f0e3f8b">EvtCleanupCallback</a> and <a href="https://msdn.microsoft.com/4c3b08d2-bb25-40bd-b2fc-1b9ea2d452b3">EvtDestroyCallback</a> functions that are called to prepare the object for deletion. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>.

If the <i>Attributes</i> parameter points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure, the caller must not overwrite the values that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552402">WDF_OBJECT_ATTRIBUTES_INIT</a> initialization function writes to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure.

For more information about creating system-DMA-transmit objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>. For more information about system-DMA-transmit transactions, see <a href="https://msdn.microsoft.com/8569E76F-CAFF-4A2C-8052-62B340C5ADED">SerCx2 System-DMA-Transmit Transactions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/aba2efca-7d1f-4594-af65-13356f0e3f8b">EvtCleanupCallback</a>



<a href="https://msdn.microsoft.com/4c3b08d2-bb25-40bd-b2fc-1b9ea2d452b3">EvtDestroyCallback</a>



<a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>



<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/00B17CBC-FE0E-4611-A41B-42AD833731D3">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a>



<a href="https://msdn.microsoft.com/DAC33D61-F85C-43A7-9F4D-AA31F8CA4430">EvtSerCx2SystemDmaTransmitCleanupTransaction</a>



<a href="https://msdn.microsoft.com/796A6C4B-0C7E-43C5-88BC-C03DAA3869A6">EvtSerCx2SystemDmaTransmitDrainFifo</a>



<a href="https://msdn.microsoft.com/2B6B33D9-1756-4C0B-91BB-AB36D4B6A913">EvtSerCx2SystemDmaTransmitInitializeTransaction</a>



<a href="https://msdn.microsoft.com/79BD2B77-E99A-4CFA-9F7B-AFC984D5F0B3">EvtSerCx2SystemDmaTransmitPurgeFifo</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265344">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265345">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265261">SerCx2InitializeDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552402">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547020">WdfDmaEnablerWdmGetDmaAdapter</a>
 

 

