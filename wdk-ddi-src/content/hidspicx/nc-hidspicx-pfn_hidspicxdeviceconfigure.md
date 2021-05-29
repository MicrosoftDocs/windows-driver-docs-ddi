---
UID: NC:hidspicx.PFN_HIDSPICXDEVICECONFIGURE
tech.root: hid
title: PFN_HIDSPICXDEVICECONFIGURE
ms.date: 
targetos: Windows
description: 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: hidspicx.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN10_NEXT
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - hidspicx.h
api_name:
 - PFN_HIDSPICXDEVICECONFIGURE
f1_keywords:
 - PFN_HIDSPICXDEVICECONFIGURE
 - hidspicx/PFN_HIDSPICXDEVICECONFIGURE
dev_langs:
 - c++
---

## -description

The **HidSpiCxDeviceConfigure** function 

## -parameters

### -param DriverGlobals

### -param Device

WDF handle to the device object this method is being called for.

### -param DeviceConfiguration

Pointer to a caller initialized HIDSPICX_DEVICE_CONFIG structure, specifying the details of the callbacks and queues to be used for communication between the class extension and client driver.

## -returns

NTSTATUS indicating whether HidSpiCx was able to successfully configure the device.

## -remarks

After calling WdfDeviceCreate (and still in its EVT_WDF_DRIVER_DEVICE_ADD callback), the client driver then calls this function with a pointer to a HIDSPICX_DEVICE_CONFIG structure, specifying interfaces the class extension will use to communicate with the device. The class extension will here initialize internal state, returning whether or not this is successful.

The client driver may, if necessary, create a default queue before or after making this callback, in order to handle (non-HID) IOCTLs not handled by the class extension.

The client driver is expected to provide a reset callback, which the class extension may call to initiate a synchronous reset of the device. A power down callback is also required. The client driver optionally specifies how many requests are to be pended in the Input Report Queue at a given time. If this is zero, the class extension will choose a default.

The client driver is expected to create and provide pointers to two non-power-managed WDFQUEUEs: an Input Report Queue and an Output Report Queue. The client may choose how reports are dispatched from these queues (manual, sequential, parallel etc). HidSpiCx will not attempt to change the state of this queue at any time ? interaction with the provided queues will be limited to forwarding and potentially cancelling requests.

Requests forwarded from the class extension to the provided queues have a variable-length buffer, containing a HIDSPICX_REPORT structure.

HidSpiCx uses internal WDF functions to hook certain power transition callbacks for the device. This means no intervention is required from the client driver in order to notify the class extension of changes in the device state.

Client drivers should not attempt to acquire power policy ownership and configure power policy settings because HidClass and HidSpiCx are responsible for managing the power policy of the device.

## -see-also
