---
UID: NF:sercx.SerCx2InitializeDevice
title: SerCx2InitializeDevice function (sercx.h)
description: The SerCx2InitializeDevice method finishes initializing the framework device object for the serial controller.
old-location: serports\sercx2initializedevice.htm
tech.root: serports
ms.assetid: C0D20E2D-5895-4FD1-9F03-9E5D1C783992
ms.date: 04/23/2018
keywords: ["SerCx2InitializeDevice function"]
ms.keywords: 2/SerCx2InitializeDevice, SerCx2InitializeDevice, SerCx2InitializeDevice method [Serial Ports], serports.sercx2initializedevice
f1_keywords:
 - "sercx/SerCx2InitializeDevice"
 - "SerCx2InitializeDevice"
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
- SerCx2InitializeDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCx2InitializeDevice function


## -description


The <b>SerCx2InitializeDevice</b> method finishes initializing the framework device object for the serial controller.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. For more information, see Remarks.


### -param Config [in]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_config">SERCX2_CONFIG</a> structure that contains pointers to a set of event callback functions that are implemented by the serial controller driver. Version 2 of the serial framework controller (SerCx2) calls these functions to configure the serial controller and to perform basic operations that are independent of the I/O transaction types (PIO, system DMA, or custom) that the driver  supports.


## -returns



<b>SerCx2InitializeDevice</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

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
The method was called at the wrong IRQL, or the <i>Device</i> parameter is not a valid WDFDEVICE handle.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <i>Config</i>-><b>Size</b> value does not equal <b>sizeof</b>(<b>SERCX2_CONFIG</b>).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <b>RequestAttributes</b> member is not valid, or required callback functions are missing from the list of function pointers. For more information, see Remarks.

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



Before calling this method, the serial controller driver must previously have called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedeviceinit">SerCx2InitializeDeviceInit</a> method.

The serial controller driver must call this method from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function after it creates a framework device object for the serial controller. The driver typically calls a method such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> to create the framework device object and to obtain a WDFDEVICE handle to this object.

Three of the function pointers in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_config">SERCX2_CONFIG</a> structure are required by SerCx2. The driver must implement the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_purge_fifos">EvtSerCx2PurgeFifos</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_control">EvtSerCx2Control</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_apply_config">EvtSerCx2ApplyConfig</a> callback functions. Otherwise, the <b>SerCx2InitializeDevice</b> call fails and returns STATUS_INVALID_PARAMETER.

If the <b>RequestAttributes</b> member of the <b>SERCX2_CONFIG</b> structure is set to a value other than WDF_NO_OBJECT_ATTRIBUTES, the driver must not overwrite the values written to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> function. Otherwise, the <b>SerCx2InitializeDevice</b> call fails and returns STATUS_INVALID_PARAMETER.

If the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetrequestattributes">WdfDeviceInitSetRequestAttributes</a> method to set the attributes to use for request objects, the request attributes specified in this call must match the request attributes that the driver specifies in the call to <b>SerCx2InitializeDevice</b>. For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265314(v=vs.85)">SerCx2 Custom-Receive Transactions</a> and <a href="https://docs.microsoft.com/previous-versions/dn265320(v=vs.85)">SerCx2 Custom-Transmit Transactions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/ns-sercx-_sercx2_config">SERCX2_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedeviceinit">SerCx2InitializeDeviceInit</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetrequestattributes">WdfDeviceInitSetRequestAttributes</a>
 

 

