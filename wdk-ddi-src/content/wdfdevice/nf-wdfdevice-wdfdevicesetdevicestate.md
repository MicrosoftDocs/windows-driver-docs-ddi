---
UID: NF:wdfdevice.WdfDeviceSetDeviceState
title: WdfDeviceSetDeviceState function (wdfdevice.h)
description: The WdfDeviceSetDeviceState method sets the device state for a specified device.
old-location: wdf\wdfdevicesetdevicestate.htm
tech.root: wdf
ms.assetid: bee3c0e9-9196-4e9b-9b75-08883f452304
ms.date: 02/26/2018
keywords: ["WdfDeviceSetDeviceState function"]
ms.keywords: DFDeviceObjectGeneralRef_41bd0604-a8fb-4df9-a1d2-f602d7ddcac4.xml, WdfDeviceSetDeviceState, WdfDeviceSetDeviceState method, kmdf.wdfdevicesetdevicestate, wdf.wdfdevicesetdevicestate, wdfdevice/WdfDeviceSetDeviceState
f1_keywords:
 - "wdfdevice/WdfDeviceSetDeviceState"
 - "WdfDeviceSetDeviceState"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfDeviceSetDeviceState
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceSetDeviceState function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceSetDeviceState</b> method sets the device state for a specified device.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param DeviceState [in]

A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_state">WDF_DEVICE_STATE</a> structure that contains the device's state information.


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




When a driver calls <b>WdfDeviceSetDeviceState</b>, the framework notifies the Plug and Play (PnP) manager that the device state has changed.


#### Examples

The following code example informs the PnP manager that a specified device is disabled.

```cpp
WDF_DEVICE_STATE    deviceState;

WDF_DEVICE_STATE_INIT (&deviceState);
deviceState.Disabled = WdfTrue;
WdfDeviceSetDeviceState (
                         Device,
                         &deviceState
                         );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_device_state_init">WDF_DEVICE_STATE_INIT</a>
 

 

