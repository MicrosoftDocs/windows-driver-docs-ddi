---
UID: NC:hidspicx.PFN_HIDSPICXDEVICEINITCONFIG
tech.root: hid
title: PFN_HIDSPICXDEVICEINITCONFIG
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
 - PFN_HIDSPICXDEVICEINITCONFIG
f1_keywords:
 - PFN_HIDSPICXDEVICEINITCONFIG
 - hidspicx/PFN_HIDSPICXDEVICEINITCONFIG
dev_langs:
 - c++
---

## -description

The client driver must call the **HidSpiCxDeviceInitConfig** function in its EVT_WDF_DRIVER_DEVICE_ADD WDF callback, before calling **WdfDeviceCreate**. The class extension initializes private PNP and power hooks for the device.

## -parameters

### -param DriverGlobals

### -param DeviceInit

WDF handle to the device init object this method is being called for.

## -returns

NTSTATUS indicating whether HidSpiCx was able to successfully initialize the device init.

## -remarks

The client driver must call this function in its EVT_WDF_DRIVER_DEVICE_ADD WDF callback, before calling WdfDeviceCreate. The class extension initializes private PNP and power hooks for the device.

## -see-also
