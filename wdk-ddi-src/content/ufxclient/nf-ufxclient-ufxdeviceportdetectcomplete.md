---
UID: NF:ufxclient.UfxDevicePortDetectComplete
title: UfxDevicePortDetectComplete function
author: windows-driver-content
description: Notifies UFX about the port type that was detected.
old-location: buses\ufxdeviceportdetectcomplete.htm
old-project: usbref
ms.assetid: D5F65152-54CD-45FA-99CE-F5B4DF444BB8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UfxDevicePortDetectComplete, UfxDevicePortDetectComplete method [Buses], buses.ufxdeviceportdetectcomplete, ufxclient/UfxDevicePortDetectComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ufxclient.h
api_name:
-	UfxDevicePortDetectComplete
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UfxDevicePortDetectComplete function


## -description


Notifies UFX about the port type that was detected.


## -syntax


````
VOID UfxDevicePortDetectComplete(
  [in] UFXDEVICE       UfxDevice,
  [in] USBFN_PORT_TYPE PortType
);
````


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


### -param PortType [in]

Contains an enumeration value of type <a href="..\usbfnbase\ne-usbfnbase-_usbfn_port_type.md">USBFN_PORT_TYPE</a>.


## -returns



This method does not return a value.




## -remarks



The client driver calls <b>UfxDevicePortDetectComplete</b> when port detection is complete. On some platforms, UFX may use the reported port type to notify the battery manager of the maximum current it can draw from the USB port.

The client driver typically calls <b>UfxDevicePortDetectComplete</b> from its <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_port_detect.md">EVT_UFX_DEVICE_PORT_DETECT</a> callback function, as shown in this example.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    // In this example we will return an unknown port type.  This will allow UFX to connect to a host if
    // one is present.  UFX will timeout after 5 seconds if no host is present and transition to
    // an invalid charger type, which will allow the controller to exit D0.
    //
    UfxDevicePortDetectComplete(ControllerContext-&gt;UfxDevice, UsbfnUnknownPort);
</pre>
</td>
</tr>
</table></span></div>


