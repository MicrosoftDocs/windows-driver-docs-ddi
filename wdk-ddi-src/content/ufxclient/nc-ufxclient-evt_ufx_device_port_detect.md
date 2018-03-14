---
UID: NC:ufxclient.EVT_UFX_DEVICE_PORT_DETECT
title: EVT_UFX_DEVICE_PORT_DETECT
author: windows-driver-content
description: The client driver's implementation to initiate port detection.
old-location: buses\evt_ufx_device_port_detect.htm
old-project: usbref
ms.assetid: EC32BFE8-6E93-4CEF-8EA8-856B0E431FCF
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UFX_DEVICE_PORT_DETECT, EvtUfxDevicePortDetect, EvtUfxDevicePortDetect callback function [Buses], PFN_UFX_DEVICE_PORT_DETECT, PFN_UFX_DEVICE_PORT_DETECT callback function pointer [Buses], buses.evt_ufx_device_port_detect, ufxclient/EvtUfxDevicePortDetect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	UserDefined
api_location:
-	Ufxclient.h
api_name:
-	PFN_UFX_DEVICE_PORT_DETECT
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# EVT_UFX_DEVICE_PORT_DETECT callback


## -description


The client driver's implementation to initiate port detection


## -prototype


````
EVT_UFX_DEVICE_PORT_DETECT EvtUfxDevicePortDetect;

void EvtUfxDevicePortDetect(
  _In_ UFXDEVICE UfxDevice
)
{ ... }

typedef EVT_UFX_DEVICE_PORT_DETECT PFN_UFX_DEVICE_PORT_DETECT;
````


## -parameters










#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


## -returns



This callback function does not return a value.




## -remarks



The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_PORT_DETECT</i> implementation with the USB function class extension (UFX) by calling the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a> method.

The client driver must indicate completion of port detection by calling the <a href="..\ufxclient\nf-ufxclient-ufxdeviceportdetectcomplete.md">UfxDevicePortDetectComplete</a> or <a href="..\ufxclient\nf-ufxclient-ufxdeviceportdetectcompleteex.md">UfxDevicePortDetectCompleteEx</a> methods.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_UFX_DEVICE_PORT_DETECT UfxDevice_EvtDevicePortDetect;

VOID
UfxDevice_EvtDevicePortDetect (
    _In_ UFXDEVICE UfxDevice
    )
/*++
Routine Description:

    Starts the port detection state machine

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

--*/
{
    PUFXDEVICE_CONTEXT DeviceContext;
    PCONTROLLER_CONTEXT ControllerContext;

    DeviceContext = UfxDeviceGetContext(UfxDevice);
    ControllerContext = DeviceGetControllerContext(DeviceContext-&gt;FdoWdfDevice);

    //
    // #### TODO: Insert code to determine port/charger type ####
    // 
    // In this example we will return an unknown port type.  
    // This will allow UFX to connect to a host if one is present.  
    // UFX will timeout after 5 seconds if no host is present and transition to
    // an invalid charger type, which will allow the controller to exit D0.
    //

    UfxDevicePortDetectComplete(ControllerContext-&gt;UfxDevice, UsbfnUnknownPort);
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a>



<a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>



 

 


