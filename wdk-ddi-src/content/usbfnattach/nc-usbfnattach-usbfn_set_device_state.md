---
UID: NC:usbfnattach.USBFN_SET_DEVICE_STATE
title: USBFN_SET_DEVICE_STATE
author: windows-driver-content
description: The filter driver's implementation to set the device state and operating bus speed.
old-location: buses\usbfn_set_device_state.htm
tech.root: usbref
ms.assetid: EAEFEE8A-D96B-40D8-A4F0-FEFA670E1E6E
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: PFN_USBFN_SET_DEVICE_STATE, PFN_USBFN_SET_DEVICE_STATE callback function pointer [Buses], USBFN_SET_DEVICE_STATE, USBFN_SET_DEVICE_STATE callback, UsbFnSetDeviceState, UsbFnSetDeviceState callback function [Buses], buses.usbfn_set_device_state, usbfnattach/UsbFnSetDeviceState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbfnattach.h
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
-	usbfnattach.h
api_name:
-	USBFN_SET_DEVICE_STATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBFN_SET_DEVICE_STATE callback function


## -description


The filter driver's implementation to set the device state and operating bus speed.


## -parameters




### -param Context [in]

    A pointer to a driver-defined context.


### -param DeviceState [in]

    A <a href="https://msdn.microsoft.com/library/windows/hardware/mt187992">USBFN_DEVICE_STATE</a>-typed flag that indicates the state of the device.


### -param BusSpeed [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt187987">USBFN_BUS_SPEED</a>-typed flag that indicates the bus speed.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



To support attach and detatch detection, the USB lower filter driver must publish its support. During the publishing process, the driver also registers its implementation of this  callback function. For more information, see <a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>.

The lower filter driver might implement  a <i>USBFN_SET_DEVICE_STATE</i> even callback function if it requires notification of device state changes to properly configure charging when attached to a host, or in lab scenarios where charging via USB must be disabled.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
UsbLowerFilter_SetDeviceState(
    _In_ PVOID Context,
    _In_ USBFN_DEVICE_STATE DeviceState,
    _In_ USBFN_BUS_SPEED BusSpeed
    )
{
    PPDCP_CONTEXT PdcpContext = NULL;

    PAGED_CODE();

    // Get our context
    PdcpContext = DeviceGetUsbLowerFilterContext((WDFDEVICE)Context);

    PdcpContext-&gt;CurrentDeviceState = DeviceState;
    PdcpContext-&gt;BusSpeed = BusSpeed;

    return STATUS_SUCCESS;
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/05D2B46A-282C-4B75-9F5C-2FC0AF344AB9">USB filter driver for supporting proprietary chargers</a>
 

 

