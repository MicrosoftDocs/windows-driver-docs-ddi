---
UID: NC:wdm.PO_FX_DEVICE_POWER_REQUIRED_CALLBACK
title: PO_FX_DEVICE_POWER_REQUIRED_CALLBACK (wdm.h)
description: The DevicePowerRequiredCallback callback routine notifies the device driver that the device must enter and remain in the D0 power state.
tech.root: kernel
ms.date: 01/10/2023
keywords: ["PO_FX_DEVICE_POWER_REQUIRED_CALLBACK callback function"]
ms.keywords: DevicePowerRequiredCallback, DevicePowerRequiredCallback routine [Kernel-Mode Driver Architecture], PO_FX_DEVICE_POWER_REQUIRED_CALLBACK, kernel.devicepowerrequiredcallback, wdm/DevicePowerRequiredCallback
req.header: wdm.h
req.include-header: Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at IRQL <= DISPATCH_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - PO_FX_DEVICE_POWER_REQUIRED_CALLBACK
 - wdm/PO_FX_DEVICE_POWER_REQUIRED_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - PO_FX_DEVICE_POWER_REQUIRED_CALLBACK
---

## -description

The *DevicePowerRequiredCallback* callback routine notifies the device driver that the device must enter and remain in the D0 power state.

## -parameters

### -param Context [in]

A pointer to the device context. The device driver uses this context to store information about the current power state of the device. The device driver specified this pointer in the **DeviceContext** member of the [**PO_FX_DEVICE**](./ns-wdm-_po_fx_device_v1.md) structure that the driver used to register the device with the power management framework (PoFx). This context is opaque to PoFx.

## -remarks

After PoFx calls the driver's *DevicePowerRequiredCallback* routine, the driver must initiate a transition to the D0 state by sending a D0 IRP (an [IRP_MN_SET_POWER](/windows-hardware/drivers/kernel/irp-mn-set-power) request) down the device stack, if the device is not already in the D0 state. After the driver completes (and all lower drivers complete) handling of this request, the driver must call the [PoFxReportDevicePoweredOn](./nf-wdm-pofxreportdevicepoweredon.md) routine. The **PoFxReportDevicePoweredOn** call notifies PoFx that the device completed its response to the *DevicePowerRequiredCallback* call. The driver can call **PoFxReportDevicePoweredOn** during or after the *DevicePowerRequiredCallback* call.

Each time the *DevicePowerRequiredCallback* routine is called, the driver must respond by calling **PoFxReportDevicePoweredOn**. The **PoFxReportDevicePoweredOn** call can occur either during or after the *DevicePowerRequiredCallback* call. The driver must call **PoFxReportDevicePoweredOn** regardless of whether no D0 IRP is required, the D0 IRP request fails, or the dispatched D0 IRP succeeds or fails.

PoFx calls the *DevicePowerRequiredCallback* routine only if PoFx previously called the driver's [DevicePowerNotRequiredCallback](./nc-wdm-po_fx_device_power_not_required_callback.md) routine to notify the driver that the device was not required to stay in the D0 state.

The call to the *DevicePowerRequiredCallback* routine can occur at any time after the driver calls [PoFxCompleteDevicePowerNotRequired](./nf-wdm-pofxcompletedevicepowernotrequired.md) to complete a *DevicePowerNotRequiredCallback* callback. The *DevicePowerRequiredCallback* call does not necessarily occur as a result of an action taken by the driver, such as requesting that a component change to the active condition.

### Examples

To define a *DevicePowerRequiredCallback* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *DevicePowerRequiredCallback* callback routine that is named `MyDevicePowerRequiredCallback`, use the PO_FX_DEVICE_POWER_REQUIRED_CALLBACK type as shown in this code example:

```cpp
PO_FX_DEVICE_POWER_REQUIRED_CALLBACK MyDevicePowerRequiredCallback;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyDevicePowerRequiredCallback(
    PVOID Context
    )
  {
      // Function body
  }
```

The PO_FX_DEVICE_POWER_REQUIRED_CALLBACK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the PO_FX_DEVICE_POWER_REQUIRED_CALLBACK function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[DevicePowerNotRequiredCallback](./nc-wdm-po_fx_device_power_not_required_callback.md)

[**PO_FX_DEVICE**](./ns-wdm-_po_fx_device_v1.md)

[PoFxCompleteDevicePowerNotRequired](./nf-wdm-pofxcompletedevicepowernotrequired.md)

[PoFxRegisterDevice](./nf-wdm-pofxregisterdevice.md)

[PoFxReportDevicePoweredOn](./nf-wdm-pofxreportdevicepoweredon.md)