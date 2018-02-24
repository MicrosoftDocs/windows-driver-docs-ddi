---
UID: NF:sercx.SerCx2InitializeDeviceInit
title: SerCx2InitializeDeviceInit function
author: windows-driver-content
description: The SerCx2InitializeDeviceInit method enables version 2 of the serial framework extension (SerCx2) to register extension-specific properties with the driver framework during the creation of the framework device object for the serial controller.
old-location: serports\sercx2initializedeviceinit.htm
old-project: serports
ms.assetid: E63B234D-07B7-467D-A13B-157781513F22
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: serports.sercx2initializedeviceinit, SerCx2InitializeDeviceInit, SerCx2InitializeDeviceInit method [Serial Ports], 2/SerCx2InitializeDeviceInit
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
-	SerCx2InitializeDeviceInit
product: Windows
targetos: Windows
req.typenames: "*PSERCX_STATUS, SERCX_STATUS"
req.product: Windows 10 or later.
---

# SerCx2InitializeDeviceInit function


## -description


The <b>SerCx2InitializeDeviceInit</b> method enables version 2 of the serial framework extension (SerCx2) to register extension-specific properties with the driver framework during the creation of the framework device object for the serial controller.


## -syntax


````
NTSTATUS SerCx2InitializeDeviceInit(
  [in, out] PWDFDEVICE_INIT DeviceInit
);
````


## -parameters




### -param DeviceInit [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure, which is an opaque structure that stores information that the Kernel Mode Driver Framework (KMDF) uses to create a framework device object. The serial controller driver receives a pointer to this structure as an input parameter to the driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.


## -returns



<b>SerCx2InitializeDeviceInit</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

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
The method was called at the wrong IRQL, or the <i>DeviceInit</i> parameter is <b>NULL</b>.

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



The serial controller driver must call this method from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function before it creates a WDFDEVICE object for the serial controller.

<b>SerCx2InitializeDeviceInit</b> attaches extension-specific information to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure. This information enables SerCx2 to perform certain actions on behalf of the serial controller driver. For example, SerCx2 receives I/O requests that clients send to the serial controller.

The serial controller driver must call <b>SerCx2InitializeDeviceInit</b> before creating a framework device object to represent the serial controller, and before calling the <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a> method to finish initializing the device object. The driver calls a method such as <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> to create the device object.

<b>SerCx2InitializeDeviceInit</b> sets a default security descriptor that allows both kernel-mode drivers and user-mode drivers to send I/O requests to SerCx2. The descriptor allows applications to send these requests only if they run with administrator privileges. To specify this descriptor, SerCx2 uses the following SDDL string:

<code>"D:P(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;UD)"</code>
If necessary, the serial controller driver can override the default setting by calling the <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitassignsddlstring.md">WdfDeviceInitAssignSDDLString</a> method with the desired security descriptor. The driver must call <b>WdfDeviceInitAssignSDDLString</b> after calling <b>SerCx2InitializeDeviceInit</b> but before calling <b>WdfDeviceCreate</b>. For more information about SDDL strings, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563667">SDDL for Device Objects</a>.




## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitassignsddlstring.md">WdfDeviceInitAssignSDDLString</a>



<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2InitializeDeviceInit method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

