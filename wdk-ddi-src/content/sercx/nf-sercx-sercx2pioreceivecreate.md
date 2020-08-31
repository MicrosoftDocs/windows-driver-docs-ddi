---
UID: NF:sercx.SerCx2PioReceiveCreate
title: SerCx2PioReceiveCreate function (sercx.h)
description: The SerCx2PioReceiveCreate method creates a PIO-receive object, which version 2 of the serial framework extension (SerCx2) uses to perform PIO-receive transactions.
old-location: serports\sercx2pioreceivecreate.htm
tech.root: serports
ms.assetid: DFD953F7-06DF-4FBD-8BEC-3A15943D6462
ms.date: 04/23/2018
keywords: ["SerCx2PioReceiveCreate function"]
ms.keywords: 2/SerCx2PioReceiveCreate, SerCx2PioReceiveCreate, SerCx2PioReceiveCreate method [Serial Ports], serports.sercx2pioreceivecreate
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SerCx2PioReceiveCreate
 - sercx/SerCx2PioReceiveCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 2.0\Sercx.h
api_name:
 - SerCx2PioReceiveCreate
---

# SerCx2PioReceiveCreate function


## -description

The <b>SerCx2PioReceiveCreate</b> method creates a PIO-receive object, which version 2 of the serial framework extension (SerCx2) uses to perform PIO-receive transactions.

## -parameters

### -param Device 

[in]
A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>.

### -param PioReceiveConfig 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_pio_receive_config">SERCX2_PIO_RECEIVE_CONFIG</a> structure. Before calling this method, the caller must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_pio_receive_config_init">SERCX2_PIO_RECEIVE_CONFIG_INIT</a> function to initialize the structure. This structure contains pointers to a set of event callback routines that are implemented by the serial controller driver. SerCx2 calls these functions to perform PIO-receive transactions.

### -param Attributes 

[in, optional]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes to assign to the new PIO-receive object. Before calling this method, the caller must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize the structure. This parameter is optional and can be specified as WDF_NO_OBJECT_ATTRIBUTES if the serial controller driver does not need to assign attributes to the object. For more information, see Remarks.

### -param PioReceive 

[out]
A pointer to a location to which this method writes a <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to the newly created PIO-receive object. SerCx2 and the serial controller driver use this handle in subsequent calls to refer to this object.

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
A PIO-receive object already exists from a previous <b>SerCx2PioReceiveCreate</b> call.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <i>Config</i>-><b>Size</b> value does not equal <b>sizeof</b>(<b>SERCX2_PIO_RECEIVE_CONFIG</b>).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified combination of implemented callback functions is not valid. The driver must implement the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_read_buffer">EvtSerCx2PioReceiveReadBuffer</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_enable_ready_notification">EvtSerCx2PioReceiveEnableReadyNotification</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_cancel_ready_notification">EvtSerCx2PioReceiveCancelReadyNotification</a> functions.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient resources are available to perform the requested operation.

</td>
</tr>
</table>

## -remarks

Your serial controller driver calls this method to create a PIO-receive object. SerCx2 uses this object to perform PIO-receive transactions, which use programmed I/O (PIO) to read data received by the serial controller.

Typically, a serial controller driver calls <b>SerCx2PioReceiveCreate</b> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> function. The driver must call this method only after it successfully calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a> method.

As an option, a serial controller driver can use the <i>Attributes</i> parameter to create a context for the PIO-receive object, and to supply pointers to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> functions that are called to prepare the object for deletion. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>.

If the <i>Attributes</i> parameter points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure, the caller must not overwrite the values that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> initialization function writes to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure.

For more information about creating PIO-receive objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>. For more information about PIO-receive transactions, see <a href="https://docs.microsoft.com/previous-versions/dn265332(v=vs.85)">SerCx2 PIO-Receive Transactions</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_pio_receive_config">SERCX2_PIO_RECEIVE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_pio_receive_config_init">SERCX2_PIO_RECEIVE_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>

