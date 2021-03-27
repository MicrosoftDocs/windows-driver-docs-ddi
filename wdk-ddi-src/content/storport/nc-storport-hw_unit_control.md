---
UID: NC:storport.HW_UNIT_CONTROL
title: HW_UNIT_CONTROL (storport.h)
description: A miniport driver's HwStorUnitControl routine is called to perform synchronous operations to control the state of storage unit device.
old-location: storage\hwstorunitcontrol.htm
tech.root: storage
ms.date: 05/13/2021
keywords: ["HW_UNIT_CONTROL callback function"]
ms.keywords: HW_UNIT_CONTROL, HwStorUnitControl, HwStorUnitControl routine [Storage Devices], storage.hwstorunitcontrol, storport/HwStorUnitControl
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
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
 - HW_UNIT_CONTROL
 - storport/HW_UNIT_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HW_UNIT_CONTROL
---

# HW_UNIT_CONTROL callback function

## -description

A miniport driver's **HwStorUnitControl** routine is called to perform synchronous operations to control the state of storage unit device.

## -parameters

### -param DeviceExtension

[in] A pointer to the miniport driver's per-unit storage area.

### -param ControlType

[in] A [**SCSI_UNIT_CONTROL_TYPE**](ne-storport-scsi_unit_control_type.md) value that specifies a unit control operation, where each control type initiates an action by the miniport driver. See **SCSI_UNIT_CONTROL_TYPE** for details.

### -param Parameters

[in] Pointer to a structure or value that contains information related to the **ControlType**. All structures are caller-allocated. See [**SCSI_UNIT_CONTROL_TYPE**](ne-storport-scsi_unit_control_type.md)  for details.

#### Address

The address of the unit the control operation is specified for.

## -returns

Depending on the control type, **HwStorUnitControl** returns one of the following **SCSI_UNIT_CONTROL_STATUS** values:

| Return code | Description |
| ----------- | ----------- |
| **ScsiUnitControlSuccess** | The miniport driver completed the requested operation successfully. |
| **ScsiUnitControlUnsuccessful** | The unit control operation was not successful. |

## -remarks

Storport calls a miniport's **HwStorUnitControl** with a **ScsiQuerySupportedControlTypes** control type after the HBA has been initialized but before the first I/O. The miniport driver fills in the [**SCSI_SUPPORTED_CONTROL_TYPE_LIST**](ns-storport-scsi_supported_control_type_list.md) structure at **Parameters** with the operations that it supports. After **HwStorUnitControl** returns from this call, the Storport driver calls the miniport driver's **HwStorAdapterControl** callback only for operations supported by the miniport.

Storport calls **HwStorUnitControl** to notify the miniport driver of a change to the unit device identified by **Address**, or that the miniport should perform a query or set operation on that unit, such as starting a unit or handling a power control operation for a unit.

The following table lists the current IRQL and the spinlock acquired when the control type is issued.

| Control Type | IRQL | Spin lock |
| ------------ | ---- | --------- |
| **ScsiQuerySupportedControlTypes**     | PASSIVE_LEVEL  | None |
| **ScsiUnitUsage**                      | PASSIVE_LEVEL  | None |
| **ScsiUnitStart**                      | PASSIVE_LEVEL  | None |
| **ScsiUnitPower**                      | DISPATCH_LEVEL | None |
| **ScsiUnitPoFxPowerInfo**              | PASSIVE_LEVEL  | None |
| **ScsiUnitPoFxPowerRequired**          | DISPATCH_LEVEL | None |
| **ScsiUnitPoFxPowerActive**            | DISPATCH_LEVEL | None |
| **ScsiUnitPoFxPowerSetFState**         | DISPATCH_LEVEL | None |
| **ScsiUnitPoFxPowerControl**           | DISPATCH_LEVEL | None |
| **ScsiUnitRemove**                     | PASSIVE_LEVEL  | None |
| **ScsiUnitSurpriseRemoval**            | PASSIVE_LEVEL  | None |
| **ScsiUnitRichDescription**            | PASSIVE_LEVEL  | None |
| **ScsiUnitQueryBusType**               | PASSIVE_LEVEL  | None |
| **ScsiUnitQueryFruId**                 | PASSIVE_LEVEL  | None |

The name **HwStorUnitControl**  is just a placeholder. The actual prototype of this routine is defined in *storport.h* as follows:

``` C
typedef
SCSI_UNIT_CONTROL_STATUS
HW_UNIT_CONTROL (
  _In_ PVOID  DeviceExtension,
  _In_ SCSI_UNIT_CONTROL_TYPE  ControlType,
  _In_ PVOID  Parameters
  );
```

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)

[**SCSI_UNIT_CONTROL_TYPE**](ne-storport-scsi_unit_control_type.md)
