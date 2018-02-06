---
UID: NF:sercx.SerCxDeviceInitConfig
title: SerCxDeviceInitConfig function
author: windows-driver-content
description: The SerCxDeviceInitConfig method is called by the serial controller driver to attach the serial framework extension (SerCx) to the I/O pipeline for a framework device object (FDO or PDO) that it is creating.
old-location: serports\sercxdeviceinitconfig.htm
old-project: serports
ms.assetid: 13466A7E-D39B-4E60-AD02-2E6EFE27495A
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.sercxdeviceinitconfig, SerCxDeviceInitConfig method [Serial Ports], 1/SerCxDeviceInitConfig, SerCxDeviceInitConfig
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
-	1.0\Sercx.h
apiname:
-	SerCxDeviceInitConfig
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCxDeviceInitConfig function


## -description


The <b>SerCxDeviceInitConfig</b> method is called by the serial controller driver to attach the serial framework extension (SerCx) to the I/O pipeline for a framework device object (FDO or PDO) that it is creating.


## -syntax


````
NTSTATUS SerCxDeviceInitConfig(
  [in, out] PWDFDEVICE_INIT DeviceInit
);
````


## -parameters




### -param DeviceInit [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that is to be configured.


## -returns


<b>SerCxDeviceInitConfig</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status code.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Could not allocate system resources (typically memory).

</td>
</tr>
</table> 



## -remarks


This method associates SerCx's configuration information with the <b>WDFDEVICE_INIT</b> structure for the framework device object (PDO or FDO) that is to be created. Call <b>SerCxDeviceInitConfig</b> before you call the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> method to create the device object.

The controller driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function receives a pointer to an initialized <b>WDFDEVICE_INIT</b> structure as an input parameter.

SerCx sets a default security descriptor that the serial controller driver can, if necessary, override. For example, this default security descriptor enables a user-mode driver to send an I/O request to a peripheral device that is connected to a port on the serial controller. To change this setting in the security descriptor, the serial controller driver can call the <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitassignsddlstring.md">WdfDeviceInitAssignSDDLString</a> method. This call must occur after the <b>SerCxDeviceInitConfig</b> call, but before the call to the <b>WdfDeviceCreate</b> method.



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitassignsddlstring.md">WdfDeviceInitAssignSDDLString</a>

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxDeviceInitConfig method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

