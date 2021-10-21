---
UID: NC:storport.HW_ADAPTER_CONTROL
title: HW_ADAPTER_CONTROL (storport.h)
description: A miniport driver's HwStorAdapterControl routine is called to perform synchronous operations to control the state or behavior of an adapter, such as stopping or restarting the HBA for power management.
old-location: storage\hwstoradaptercontrol.htm
tech.root: storage
ms.date: 05/13/2021
keywords: ["HW_ADAPTER_CONTROL callback function"]
ms.keywords: HW_ADAPTER_CONTROL, HwStorAdapterControl, HwStorAdapterControl routine [Storage Devices], storage.hwstoradaptercontrol, stormini_19cbc8b1-9908-4b4d-a62b-712fb97e6bbd.xml, storport/HwStorAdapterControl
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
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
req.irql: See Remarks.
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_ADAPTER_CONTROL
 - storport/HW_ADAPTER_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HW_ADAPTER_CONTROL
---

# HW_ADAPTER_CONTROL callback function

## -description

A miniport driver's **HwStorAdapterControl** routine is called to perform synchronous operations to control the state or behavior of an adapter, such as stopping or restarting the host bus adapter (HBA) for power management.

## -parameters

### -param DeviceExtension [in]

A pointer to the miniport driver's per-HBA storage area.

### -param ControlType [in]

A [**SCSI_ADAPTER_CONTROL_TYPE**](ne-storport-scsi_adapter_control_type.md) value that specifies an adapter-control operation, where each control type initiates an action by the miniport driver. See **SCSI_ADAPTER_CONTROL_TYPE** for details.

### -param Parameters [in]

Pointer to a structure or value that contains information related to the **ControlType**, or NULL if the control type doesn't use a structure. All structures are caller-allocated. See [**SCSI_ADAPTER_CONTROL_TYPE**](ne-storport-scsi_adapter_control_type.md) for details.

## -returns

Depending on the control type, **HwStorAdapterControl** returns one of the following SCSI_ADAPTER_CONTROL_STATUS values:

| Return code | Description |
| ----------- | ----------- |
| **ScsiAdapterControlSuccess** | The miniport driver completed the requested operation successfully. Currently, **HwStorAdapterControl** must return this value for all control types. |
| **ScsiAdapterControlUnsuccessful** | The adapter control operation was not successful. |

## -remarks

**HwStorAdapterControl** is a required function.

Storport calls a miniport's **HwStorAdapterControl** with a **ScsiQuerySupportedControlTypes** control type after the HBA has been initialized but before the first I/O. The miniport driver fills in the [**SCSI_SUPPORTED_CONTROL_TYPE_LIST**](ns-storport-scsi_supported_control_type_list.md) structure at **Parameters** with the operations that it supports. After **HwStorAdapterControl** returns from this call, the Storport driver calls the miniport driver's **HwStorAdapterControl** callback only for operations supported by the miniport.

Because miniport drivers that work with the Storport driver must support Plug and Play (PnP), miniports must support the  **ScsiStopAdapter** and **ScsiRestartAdapter** control types.

The following table lists the current IRQL and the spinlock acquired when the control type is issued.

| Control Type | IRQL | Spin lock |
| ------------ | ---- | --------- |
| **ScsiQuerySupportedControlTypes**        | PASSIVE_LEVEL     | None |
| **ScsiStopAdapter**                       | DIRQL             | InterruptLock |
| **ScsiRestartAdapter**                    | DIRQL             | InterruptLock |
| **ScsiSetBootConfig**                     | PASSIVE_LEVEL     | None |
| **ScsiSetRunningConfig**                  | PASSIVE_LEVEL     | None |
| **ScsiPowerSettingNotification**          | PASSIVE_LEVEL     | None |
| **ScsiAdapterPower**                      | <= DISPATCH_LEVEL | None |
| **ScsiAdapterPoFxPowerRequired**          | <= DISPATCH_LEVEL | None |
| **ScsiAdapterPoFxPowerActive**            | <= DISPATCH_LEVEL | None |
| **ScsiAdapterPoFxPowerSetFState**         | <= DISPATCH_LEVEL | None |
| **ScsiAdapterPoFxPowerControl**           | <= DISPATCH_LEVEL | None |
| **ScsiAdapterPrepareForBusReScan**        | PASSIVE_LEVEL     | None |
| **ScsiAdapterSystemPowerHints**           | PASSIVE_LEVEL     | None |
| **ScsiAdapterFilterResourceRequirements** | < DISPATCH_LEVEL  | None |
| **ScsiAdapterPoFxMaxOperationalPower**    | PASSIVE_LEVEL     | None |
| **ScsiAdapterPoFxSetPerfState**           | <= DISPATCH_LEVEL | None |
| **ScsiAdapterSurpriseRemoval**            | < DISPATCH_LEVEL  | None |
| **ScsiAdapterSerialNumber**               | < DISPATCH_LEVEL  | None |
| **ScsiAdapterCryptoOperation**            | PASSIVE_LEVEL     | None |
| **ScsiAdapterQueryFruId**                 | PASSIVE_LEVEL     | None |
| **ScsiAdapterSetEventLogging**            | PASSIVE_LEVEL     | None |

The name **HwStorAdapterControl**  is just a placeholder. The actual prototype of this routine is defined in *storport.h* as follows:

``` C
typedef
SCSI_ADAPTER_CONTROL_STATUS
HW_ADAPTER_CONTROL (
  _In_ PVOID  DeviceExtension,
  _In_ SCSI_ADAPTER_CONTROL_TYPE  ControlType,
  _In_ PVOID  Parameters
  );
```

### Examples

To define an **HwStorAdapterControl** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **HwStorAdapterControl** callback routine that is named *MyHwAdapterControl*, use the **HW_ADAPTER_CONTROL** type as shown in this code example:

``` C
HW_ADAPTER_CONTROL MyHwAdapterControl;
```

Then, implement your callback routine as follows:

``` C
_Use_decl_annotations_
SCSI_ADAPTER_CONTROL_STATUS
MyHwAdapterControl (
  _In_ PVOID  DeviceExtension,
  _In_ SCSI_ADAPTER_CONTROL_TYPE  ControlType,
  _In_ PVOID  Parameters
  );
  {
      ...
  }
```

The **HW_ADAPTER_CONTROL** function type is defined in the *Storport.h* header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **HW_ADAPTER_CONTROL** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[**HwStorFindAdapter**](nc-storport-hw_find_adapter.md)

[**HwStorInitialize**](nc-storport-hw_initialize.md)

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)

[**SCSI_ADAPTER_CONTROL_TYPE**](ne-storport-scsi_adapter_control_type.md)

[**SCSI_SUPPORTED_CONTROL_TYPE_LIST**](ns-storport-scsi_supported_control_type_list.md)
