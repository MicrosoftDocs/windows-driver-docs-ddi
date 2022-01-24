---
UID: NC:ufxclient.EVT_UFX_DEVICE_PORT_DETECT
title: EVT_UFX_DEVICE_PORT_DETECT (ufxclient.h)
description: The client driver's implementation to initiate port detection.
old-location: buses\evt_ufx_device_port_detect.htm
tech.root: usbref
ms.date: 01/18/2022
keywords: ["EVT_UFX_DEVICE_PORT_DETECT callback function"]
ms.keywords: EVT_UFX_DEVICE_PORT_DETECT, EVT_UFX_DEVICE_PORT_DETECT callback, EvtUfxDevicePortDetect, EvtUfxDevicePortDetect callback function [Buses], PFN_UFX_DEVICE_PORT_DETECT, PFN_UFX_DEVICE_PORT_DETECT callback function pointer [Buses], buses.evt_ufx_device_port_detect, ufxclient/EvtUfxDevicePortDetect
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UFX_DEVICE_PORT_DETECT
 - ufxclient/EVT_UFX_DEVICE_PORT_DETECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ufxclient.h
api_name:
 - EVT_UFX_DEVICE_PORT_DETECT
---

# EVT_UFX_DEVICE_PORT_DETECT callback function

## -description

The client driver's implementation to initiate port detection

## -parameters

### -param unnamedParam1 [in]

The handle to a USB device object that the client driver received in a previous call to the [UfxDeviceCreate](nf-ufxclient-ufxdevicecreate.md) method.

## -remarks

The client driver for the function host controller registers its *EVT_UFX_DEVICE_PORT_DETECT* implementation with the USB function class extension (UFX) by calling the [UfxDeviceCreate](nf-ufxclient-ufxdevicecreate.md) method.

The client driver must indicate completion of port detection by calling the [UfxDevicePortDetectComplete](nf-ufxclient-ufxdeviceportdetectcomplete.md) or [UfxDevicePortDetectCompleteEx](nf-ufxclient-ufxdeviceportdetectcompleteex.md) methods.

### Examples

```cpp
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
    ControllerContext = DeviceGetControllerContext(DeviceContext->FdoWdfDevice);

    //
    // #### TODO: Insert code to determine port/charger type ####
    // 
    // In this example we will return an unknown port type.  
    // This will allow UFX to connect to a host if one is present.  
    // UFX will timeout after 5 seconds if no host is present and transition to
    // an invalid charger type, which will allow the controller to exit D0.
    //

    UfxDevicePortDetectComplete(ControllerContext->UfxDevice, UsbfnUnknownPort);
}

```

## -see-also

- [UfxDeviceCreate](nf-ufxclient-ufxdevicecreate.md)
- [UfxDeviceEventComplete](nf-ufxclient-ufxdeviceeventcomplete.md)
- [UfxDevicePortDetectComplete](nf-ufxclient-ufxdeviceportdetectcomplete.md)
- [UfxDevicePortDetectCompleteEx](nf-ufxclient-ufxdeviceportdetectcompleteex.md)
