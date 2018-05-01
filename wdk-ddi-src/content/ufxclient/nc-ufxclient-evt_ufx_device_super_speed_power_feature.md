---
UID: NC:ufxclient.EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE
title: EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE
author: windows-driver-content
description: The client driver's implementation to set or clear the specified power feature on the function controller.
old-location: buses\evt_ufx_device_super_speed_power_feature.htm
old-project: usbref
ms.assetid: 5A2B787B-13B8-48E9-B53E-7F6409820B88
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE, EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE callback, EvtUfxDeviceSuperSpeedPowerFeature, EvtUfxDeviceSuperSpeedPowerFeature callback function [Buses], PFN_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE, PFN_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE callback function pointer [Buses], buses.evt_ufx_device_super_speed_power_feature, ufxclient/EvtUfxDeviceSuperSpeedPowerFeature
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ufxclient.h
api_name:
-	PFN_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE
product: Windows
targetos: Windows
req.typenames: 
---

# EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE callback function


## -description


The client driver's implementation to set or clear the specified power feature on the function controller. 


## -parameters












#### - Feature [in]

Feature selector for the power feature that is set or cleared, as defined in section 9.4 of the USB 3.0 Specification.  The feature selector can be one of these values: 

<ul>
<li>U1_ENABLE</li>
<li>U2_ENABLE
</li>
</ul>

#### - Set [in]

If TRUE, set the feature.

If FALSE, clear the feature.


#### - UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


## -returns



This callback function does not return a value.




## -remarks



The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE</i> implementation with the USB function class extension (UFX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a> method.

This event callback is only required for controllers that support SuperSpeed operation.

The client driver indicates completion of this event by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a> method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE UfxDevice_EvtDeviceSuperSpeedPowerFeature;

VOID
UfxDevice_EvtDeviceSuperSpeedPowerFeature (
    _In_ UFXDEVICE Device,
    _In_ USHORT Feature,
    _In_ BOOLEAN Set
    )
/*++

Routine Description:

    EvtDeviceSuperSpeedPowerFeature handler for the UFXDEVICE object.
    
    Handles a set or clear U1/U2 request from the host.  

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

    Feature - Indicates the feature being set or cleared.  Either U1 or U2 enable.

    Set - Indicates if the feature should be set or cleared
    
--*/
{
    TraceEntry();

    if (Feature == USB_FEATURE_U1_ENABLE) {
        if (Set == TRUE) {
            //
            // #### TODO: Insert code to initiate U1  ####
            //
        } else {
            //
            // #### TODO: Insert code to exit U1 ####
            //
        }
    } else if (Feature == USB_FEATURE_U2_ENABLE) {
        if (Set == TRUE) {
            //
            // #### TODO: Insert code to initiate U2 ####
            //
        } else {
            //
            // #### TODO: Insert code to exit U2 ####
            //
        }
    } else {
        NT_ASSERT(FALSE);
    }

    UfxDeviceEventComplete(Device, STATUS_SUCCESS);
    TraceExit();
}

</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a>
 

 

