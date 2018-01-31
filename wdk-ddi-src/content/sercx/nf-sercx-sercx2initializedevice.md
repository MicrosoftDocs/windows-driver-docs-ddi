---
UID: NF:sercx.SerCx2InitializeDevice
title: SerCx2InitializeDevice function
author: windows-driver-content
description: The SerCx2InitializeDevice method finishes initializing the framework device object for the serial controller.
old-location: serports\sercx2initializedevice.htm
old-project: serports
ms.assetid: C0D20E2D-5895-4FD1-9F03-9E5D1C783992
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: 2/SerCx2InitializeDevice, serports.sercx2initializedevice, SerCx2InitializeDevice, SerCx2InitializeDevice method [Serial Ports]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	2.0\Sercx.h
apiname:
-	SerCx2InitializeDevice
product: Windows
targetos: Windows
req.typenames: "*PSERCX_STATUS, SERCX_STATUS"
req.product: Windows 10 or later.
---

# SerCx2InitializeDevice function


## -description


The <b>SerCx2InitializeDevice</b> method finishes initializing the framework device object for the serial controller.


## -syntax


````
NTSTATUS SerCx2InitializeDevice(
  [in] WDFDEVICE      Device,
  [in] PSERCX2_CONFIG Config
);
````


## -parameters




#### - Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. For more information, see Remarks.


#### - Config [in]

A pointer to a caller-allocated <a href="..\sercx\ns-sercx-_sercx2_config.md">SERCX2_CONFIG</a> structure that contains pointers to a set of event callback functions that are implemented by the serial controller driver. Version 2 of the serial framework controller (SerCx2) calls these functions to configure the serial controller and to perform basic operations that are independent of the I/O transaction types (PIO, system DMA, or custom) that the driver  supports.


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
The <i>Config</i>-&gt;<b>Size</b> value does not equal <b>sizeof</b>(<b>SERCX2_CONFIG</b>).

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


Before calling this method, the serial controller driver must must previously have called the <a href="..\sercx\nf-sercx-sercx2initializedeviceinit.md">SerCx2InitializeDeviceInit</a> method.

The serial controller driver must call this method from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function after it creates a framework device object for the serial controller. The driver typically calls a method such as <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> to create the framework device object and to obtain a WDFDEVICE handle to this object.

Three of the function pointers in the <a href="..\sercx\ns-sercx-_sercx2_config.md">SERCX2_CONFIG</a> structure are required by SerCx2. The driver must implement the <a href="..\sercx\nc-sercx-evt_sercx2_purge_fifos.md">EvtSerCx2PurgeFifos</a>, <a href="..\sercx\nc-sercx-evt_sercx2_control.md">EvtSerCx2Control</a>, and <a href="..\sercx\nc-sercx-evt_sercx2_apply_config.md">EvtSerCx2ApplyConfig</a> callback functions. Otherwise, the <b>SerCx2InitializeDevice</b> call fails and returns STATUS_INVALID_PARAMETER.

If the <b>RequestAttributes</b> member of the <b>SERCX2_CONFIG</b> structure is set to a value other than WDF_NO_OBJECT_ATTRIBUTES, the driver must not overwrite the values written to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure by the <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> function. Otherwise, the <b>SerCx2InitializeDevice</b> call fails and returns STATUS_INVALID_PARAMETER.

If the driver calls the <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetrequestattributes.md">WdfDeviceInitSetRequestAttributes</a> method to set the attributes to use for request objects, the request attributes specified in this call must match the request attributes that the driver specifies in the call to <b>SerCx2InitializeDevice</b>. For more information, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a> and <a href="https://msdn.microsoft.com/E72E68BC-A60A-41BE-8606-92A608648042">SerCx2 Custom-Transmit Transactions</a>.



## -see-also

<a href="..\sercx\ns-sercx-_sercx2_config.md">SERCX2_CONFIG</a>

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>

<a href="..\sercx\nf-sercx-sercx2initializedeviceinit.md">SerCx2InitializeDeviceInit</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetrequestattributes.md">WdfDeviceInitSetRequestAttributes</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2InitializeDevice method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

