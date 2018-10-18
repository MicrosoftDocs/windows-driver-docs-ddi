---
UID: NC:ufxclient.EVT_UFX_DEVICE_PORT_DETECT
title: EVT_UFX_DEVICE_PORT_DETECT
author: windows-driver-content
description: The client driver's implementation to initiate port detection.
old-location: buses\evt_ufx_device_port_detect.htm
tech.root: usbref
ms.assetid: EC32BFE8-6E93-4CEF-8EA8-856B0E431FCF
ms.date: 5/7/2018
ms.keywords: EVT_UFX_DEVICE_PORT_DETECT, EVT_UFX_DEVICE_PORT_DETECT callback, EvtUfxDevicePortDetect, EvtUfxDevicePortDetect callback function [Buses], PFN_UFX_DEVICE_PORT_DETECT, PFN_UFX_DEVICE_PORT_DETECT callback function pointer [Buses], buses.evt_ufx_device_port_detect, ufxclient/EvtUfxDevicePortDetect
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UFX_DEVICE_PORT_DETECT callback function


## -description


The client driver's implementation to initiate port detection


## -parameters




### -param Arg1








#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


## -returns



This callback function does not return a value.




## -remarks



The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_PORT_DETECT</i> implementation with the USB function class extension (UFX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a> method.

The client driver must indicate completion of port detection by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187962">UfxDevicePortDetectComplete</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/mt187963">UfxDevicePortDetectCompleteEx</a> methods.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a>
 

 

