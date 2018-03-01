---
UID: NC:usbfnattach.USBFN_SET_DEVICE_STATE
title: USBFN_SET_DEVICE_STATE
author: windows-driver-content
description: The filter driver's implementation to set the device state and operating bus speed.
old-location: buses\usbfn_set_device_state.htm
old-project: usbref
ms.assetid: EAEFEE8A-D96B-40D8-A4F0-FEFA670E1E6E
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFN_USBFN_SET_DEVICE_STATE, PFN_USBFN_SET_DEVICE_STATE callback function pointer [Buses], USBFN_SET_DEVICE_STATE, UsbFnSetDeviceState, UsbFnSetDeviceState callback function [Buses], buses.usbfn_set_device_state, usbfnattach/UsbFnSetDeviceState
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
-	PFN_USBFN_SET_DEVICE_STATE
product: Windows
targetos: Windows
req.typenames: USBD_INTERFACE_LIST_ENTRY, *PUSBD_INTERFACE_LIST_ENTRY
req.product: Windows 10 or later.
---

# USBFN_SET_DEVICE_STATE callback


## -description


The filter driver's implementation to set the device state and operating bus speed.


## -prototype


````
USBFN_SET_DEVICE_STATE UsbFnSetDeviceState;

NTSTATUS UsbFnSetDeviceState(
  _In_ PVOID              Context,
  _In_ USBFN_DEVICE_STATE DeviceState,
  _In_ USBFN_BUS_SPEED    BusSpeed
)
{ ... }

typedef USBFN_SET_DEVICE_STATE PFN_USBFN_SET_DEVICE_STATE;
````


## -parameters




### -param Context [in]

    A pointer to a driver-defined context.


### -param DeviceState [in]

    A <a href="..\usbfnbase\ne-usbfnbase-_usbfn_device_state.md">USBFN_DEVICE_STATE</a>-typed flag that indicates the state of the device.


### -param BusSpeed [in]

A <a href="..\usbfnbase\ne-usbfnbase-_usbfn_bus_speed.md">USBFN_BUS_SPEED</a>-typed flag that indicates the bus speed.


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBFN_SET_DEVICE_STATE callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

