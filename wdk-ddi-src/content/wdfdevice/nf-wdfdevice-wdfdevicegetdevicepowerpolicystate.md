---
UID: NF:wdfdevice.WdfDeviceGetDevicePowerPolicyState
title: WdfDeviceGetDevicePowerPolicyState function (wdfdevice.h)
description: The WdfDeviceGetDevicePowerPolicyState method returns the current state of the framework's power policy state machine, for a specified device.
old-location: wdf\wdfdevicegetdevicepowerpolicystate.htm
tech.root: wdf
ms.assetid: 3a4aab60-6568-4017-acad-ca643cb4d661
ms.date: 02/26/2018
keywords: ["WdfDeviceGetDevicePowerPolicyState function"]
ms.keywords: DFDeviceObjectGeneralRef_34dd5376-7889-4900-bcd9-65ad9ff732e2.xml, WdfDeviceGetDevicePowerPolicyState, WdfDeviceGetDevicePowerPolicyState method, kmdf.wdfdevicegetdevicepowerpolicystate, wdf.wdfdevicegetdevicepowerpolicystate, wdfdevice/WdfDeviceGetDevicePowerPolicyState
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceGetDevicePowerPolicyState
 - wdfdevice/WdfDeviceGetDevicePowerPolicyState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceGetDevicePowerPolicyState
---

# WdfDeviceGetDevicePowerPolicyState function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

>[!NOTE]
>This function is for Microsoft-internal use only.

The <b>WdfDeviceGetDevicePowerPolicyState</b> method returns the current state of the framework's power policy state machine, for a specified device.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

## -returns

<b>WdfDeviceGetDevicePowerPolicyState</b> returns a <a href="/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_power_policy_state">WDF_DEVICE_POWER_POLICY_STATE</a>-typed enumerator that identifies the current state of the framework's power policy state machine for the specified device. 

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about the framework's state machines, see <a href="/windows-hardware/drivers/wdf/state-machines-in-the-framework">State Machines in the Framework</a>.

The <b>WdfDeviceGetDevicePowerPolicyState</b> method returns a meaningful value only if it is called from within the callback functions that the driver registers when it calls <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.


#### Examples

The following code example obtains the current state of the framework's power policy state machine for a specified device.

```cpp
WDF_DEVICE_POWER_POLICY_STATE devicePowerPolicyState;

devicePowerPolicyState = WdfDeviceGetDevicePowerPolicyState(Device);
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevstatenormalize">WdfDevStateNormalize</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepnpstate">WdfDeviceGetDevicePnpState</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepowerstate">WdfDeviceGetDevicePowerState</a>