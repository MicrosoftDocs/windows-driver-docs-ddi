---
UID: NC:wdm.PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK
title: PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK (wdm.h)
description: The DevicePowerNotRequiredCallback callback routine notifies the device driver that the device is not required to stay in the D0 power state.
tech.root: kernel
ms.date: 01/10/2023
keywords: ["PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK callback function"]
ms.keywords: DevicePowerNotRequiredCallback, DevicePowerNotRequiredCallback routine [Kernel-Mode Driver Architecture], PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK, kernel.devicepowernotrequiredcallback, wdm/DevicePowerNotRequiredCallback
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
 - PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK
 - wdm/PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK
---

## -description

The *DevicePowerNotRequiredCallback* callback routine notifies the device driver that the device is not required to stay in the D0 power state.

## -parameters

### -param Context [in]

A pointer to the device context. The device driver uses this context to store information about the current power state of the device. The device driver specified this pointer in the **DeviceContext** member of the [**PO_FX_DEVICE**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1) structure that the driver used to register the device with the power management framework (PoFx). This context is opaque to PoFx.

## -remarks

When PoFx calls the driver's *DevicePowerNotRequiredCallback* routine, the driver must first decide whether to initiate a transition to a low-power Dx state (by sending an [IRP_MN_SET_POWER](/windows-hardware/drivers/kernel/irp-mn-set-power) request down the device stack) or to remain in the D0 state. Next, without waiting for any Dx transition to complete, the driver must call the [PoFxCompleteDevicePowerNotRequired](/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxcompletedevicepowernotrequired) routine to notify PoFx that the driver completed its response to the *DevicePowerNotRequiredCallback* callback. The driver can call **PoFxCompleteDevicePowerNotRequired** before or after the *DevicePowerNotRequiredCallback* routine returns.

When a device is in the D0 state, and the Fx state or active/idle condition of a component in the device changes, PoFx evaluates whether the device can enter a low-power Dx state or must remain in the D0 state. If the device can enter a low-power Dx state, PoFx calls the driver's *DevicePowerNotRequiredCallback* routine.

If the device enters a low-power Dx state in response to a *DevicePowerNotRequiredCallback* callback, but PoFx later determines that the device must enter the D0 state, PoFx calls the driver's [DevicePowerRequiredCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_device_power_required_callback) routine. In response to this call, the device must enter the D0 state.

### Examples

To define a *DevicePowerNotRequiredCallback* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *DevicePowerNotRequiredCallback* callback routine that is named `MyDevicePowerNotRequiredCallback`, use the PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK type as shown in this code example:

```cpp
PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK MyDevicePowerNotRequiredCallback;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyDevicePowerNotRequiredCallback(
    PVOID Context
    )
  {
      // Function body
  }

```

The PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[DevicePowerRequiredCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_device_power_required_callback)

[IRP_MN_SET_POWER](/windows-hardware/drivers/kernel/irp-mn-set-power)

[**PO_FX_DEVICE**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1)

[PoFxCompleteDevicePowerNotRequired](/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxcompletedevicepowernotrequired)

[PoFxRegisterDevice](/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice)
