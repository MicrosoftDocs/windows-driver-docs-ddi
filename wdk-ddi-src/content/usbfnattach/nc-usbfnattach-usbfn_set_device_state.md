---
UID: NC:usbfnattach.USBFN_SET_DEVICE_STATE
title: USBFN_SET_DEVICE_STATE (usbfnattach.h)
description: The filter driver's implementation to set the device state and operating bus speed.
old-location: buses\usbfn_set_device_state.htm
tech.root: usbref
ms.assetid: EAEFEE8A-D96B-40D8-A4F0-FEFA670E1E6E
ms.date: 05/07/2018
keywords: ["USBFN_SET_DEVICE_STATE callback function"]
ms.keywords: PFN_USBFN_SET_DEVICE_STATE, PFN_USBFN_SET_DEVICE_STATE callback function pointer [Buses], USBFN_SET_DEVICE_STATE, USBFN_SET_DEVICE_STATE callback, UsbFnSetDeviceState, UsbFnSetDeviceState callback function [Buses], buses.usbfn_set_device_state, usbfnattach/UsbFnSetDeviceState
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
targetos: Windows
req.typenames: 
f1_keywords:
 - USBFN_SET_DEVICE_STATE
 - usbfnattach/USBFN_SET_DEVICE_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbfnattach.h
api_name:
 - USBFN_SET_DEVICE_STATE
---

# USBFN_SET_DEVICE_STATE callback function


## -description

The filter driver's implementation to set the device state and operating bus speed.

## -parameters

### -param Context 

[in]
    A pointer to a driver-defined context.

### -param DeviceState 

[in]
    A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ne-usbfnbase-_usbfn_device_state">USBFN_DEVICE_STATE</a>-typed flag that indicates the state of the device.

### -param BusSpeed 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ne-usbfnbase-_usbfn_bus_speed">USBFN_BUS_SPEED</a>-typed flag that indicates the bus speed.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks

To support attach and detatch detection, the USB lower filter driver must publish its support. During the publishing process, the driver also registers its implementation of this  callback function. For more information, see <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188012(v=vs.85)">USB filter driver for supporting proprietary chargers</a>.

The lower filter driver might implement  a <i>USBFN_SET_DEVICE_STATE</i> even callback function if it requires notification of device state changes to properly configure charging when attached to a host, or in lab scenarios where charging via USB must be disabled.


#### Examples


```cpp
NTSTATUS
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

    PdcpContext->CurrentDeviceState = DeviceState;
    PdcpContext->BusSpeed = BusSpeed;

    return STATUS_SUCCESS;
}

```


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/mt188012(v=vs.85)">USB filter driver for supporting proprietary chargers</a>

