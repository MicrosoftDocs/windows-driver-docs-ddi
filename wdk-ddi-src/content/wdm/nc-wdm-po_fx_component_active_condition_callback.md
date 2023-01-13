---
UID: NC:wdm.PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK
title: PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK (wdm.h)
description: The ComponentActiveConditionCallback callback routine notifies the driver that the specified component completed a transition from the idle condition to the active condition.
tech.root: kernel
ms.date: 01/10/2023
keywords: ["PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK callback function"]
ms.keywords: ComponentActiveConditionCallback, ComponentActiveConditionCallback routine [Kernel-Mode Driver Architecture], PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK, kernel.componentactiveconditioncallback, wdm/ComponentActiveConditionCallback
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
 - PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK
 - wdm/PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK
---

## -description

The *ComponentActiveConditionCallback* callback routine notifies the driver that the specified component completed a transition from the idle condition to the active condition.

## -parameters

### -param Context [in]

A pointer to the device context. The device driver uses this context to store information about the current power state of the device. The device driver specified this pointer in the **DeviceContext** member of the [**PO_FX_DEVICE**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1) structure that the driver used to register the device with the power management framework (PoFx). This context is opaque to PoFx.

### -param Component [in]

Specifies the index that identifies the component. This parameter is an index into the **Components** array in the **PO_FX_DEVICE** structure that the device driver used to register the device with PoFx. If the **Components** array contains N elements, component indexes range from 0 to N–1.

## -remarks

A component's hardware registers can be accessed only when the component is in the active condition. Do not rely on the Fx power state of a component to determine whether the component can be accessed. If the component is in the F0 state and is in the idle condition, the component might be about to switch to another Fx state.

To gain access to a component that is in the idle condition, the driver can call the [PoFxActivateComponent](/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxactivatecomponent) routine to switch the component to the active condition. If the component is not already in the active condition when **PoFxActivateComponent** is called, PoFx initiates the transition to the active condition, and then calls the *ComponentActiveConditionCallback* routine to notify the driver when the transition is complete.

The driver receives a *ComponentActiveConditionCallback* callback whenever the component completes a transition to the active condition, regardless of whether the driver called **PoFxActivateComponent** to initiate the transition. For example, the Windows kernel might activate the component on behalf of the driver before sending a [Plug and Play IRP](/windows-hardware/drivers/kernel/passing-pnp-irps-down-the-device-stack) or a [system set-power IRP](/windows-hardware/drivers/kernel/power-irps-for-the-system) to the driver.

### Examples

To define a *ComponentActiveConditionCallback* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *ComponentActiveConditionCallback* callback routine that is named `MyComponentActiveConditionCallback`, use the PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK type as shown in this code example:

```cpp
PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK MyComponentActiveConditionCallback;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyComponentActiveConditionCallback(
    PVOID Context,
    ULONG Component
    )
  {
      // Function body
  }
```

The PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[**PO_FX_DEVICE**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1)

[PoFxActivateComponent](/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxactivatecomponent)
