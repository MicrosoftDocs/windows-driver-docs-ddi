---
UID: NC:ufxclient.EVT_UFX_DEVICE_ADDRESSED
title: EVT_UFX_DEVICE_ADDRESSED (ufxclient.h)
description: The client driver's implementation to assign an address on the function controller.
old-location: buses\evt_ufx_device_addressed.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["EVT_UFX_DEVICE_ADDRESSED callback function"]
ms.keywords: EVT_UFX_DEVICE_ADDRESSED, EVT_UFX_DEVICE_ADDRESSED callback, EvtUfxDeviceAddressed, EvtUfxDeviceAddressed callback function [Buses], PFN_UFX_DEVICE_ADDRESSED, PFN_UFX_DEVICE_ADDRESSED callback function pointer [Buses], buses.evt_ufx_device_addressed, ufxclient/EvtUfxDeviceAddressed
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UFX_DEVICE_ADDRESSED
 - ufxclient/EVT_UFX_DEVICE_ADDRESSED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ufxclient.h
api_name:
 - EVT_UFX_DEVICE_ADDRESSED
---

# EVT_UFX_DEVICE_ADDRESSED callback function


## -description

The client driver's implementation to assign an address on the function controller.

## -parameters

### -param unnamedParam1 [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.


### -param unnamedParam2 [in]

New USB device address to assign.

## -remarks

The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_ADDRESSED</i> implementation with the USB function class extension (UFX) by calling the <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a> method.

The client driver indicates completion of this event by calling the <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdeviceeventcomplete">UfxDeviceEventComplete</a> method.


#### Examples


```

EVT_UFX_DEVICE_ADDRESSED UfxDevice_EvtDeviceAddressed;

VOID
UfxDevice_EvtDeviceAddressed (
    _In_ UFXDEVICE UfxDevice,
    _In_ USHORT DeviceAddress
    )
/*++

Routine Description:

    EvtDeviceAddressed handler for the UFXDEVICE object.
    Sets the Address indicated by 'DeviceAddress' on the controller.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

    DeviceAddress - USB Device Address, as determined by the UFX.

--*/
{
    UNREFERENCED_PARAMETER(DeviceAddress);

    TraceEntry();

    //
    // Set the device address on the controller
    //

    //
    // #### Insert code to set the device address on controller ####
    //
    
    UfxDeviceEventComplete(UfxDevice, STATUS_SUCCESS);

    TraceExit();
}

```

## -see-also

<a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>



<a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdeviceeventcomplete">UfxDeviceEventComplete</a>

