---
UID: NS:storport._STOR_POFX_DEVICE_V3
title: STOR_POFX_DEVICE_V3 (storport.h)
description: The STOR_POFX_DEVICE_V3 structure describes the power attributes of a storage device to the power management framework (PoFx).
old-location: storage\stor_pofx_device_v3.htm
tech.root: storage
ms.date: 06/21/2022
keywords: ["STOR_POFX_DEVICE_V3 structure"]
ms.keywords: "*PSTOR_POFX_DEVICE_V3, PSTOR_POFX_DEVICE_V3, PSTOR_POFX_DEVICE_V3 structure pointer [Storage Devices], STOR_POFX_DEVICE_FLAG_ADAPTIVE_D3_IDLE_TIMEOUT, STOR_POFX_DEVICE_FLAG_ENABLE_D3_COLD, STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT, STOR_POFX_DEVICE_FLAG_NO_D0, STOR_POFX_DEVICE_FLAG_NO_D3, STOR_POFX_DEVICE_FLAG_NO_DUMP_ACTIVE, STOR_POFX_DEVICE_FLAG_NO_UNIT_REGISTRATION, STOR_POFX_DEVICE_V3, STOR_POFX_DEVICE_V3 structure [Storage Devices], _STOR_POFX_DEVICE_V3, storage.stor_pofx_device_v3, storport/PSTOR_POFX_DEVICE_V3, storport/STOR_POFX_DEVICE_V2"
req.header: storport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.irql: 
targetos: Windows
req.typenames: STOR_POFX_DEVICE_V3, *PSTOR_POFX_DEVICE_V3
f1_keywords:
 - _STOR_POFX_DEVICE_V3
 - storport/_STOR_POFX_DEVICE_V3
 - PSTOR_POFX_DEVICE_V3
 - storport/PSTOR_POFX_DEVICE_V3
 - STOR_POFX_DEVICE_V3
 - storport/STOR_POFX_DEVICE_V3
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_POFX_DEVICE_V3
 - PSTOR_POFX_DEVICE_V3
 - STOR_POFX_DEVICE_V3
---

# STOR_POFX_DEVICE_V3 structure

## -description

The **STOR_POFX_DEVICE_V3** structure describes the power attributes of a storage device to the power management framework (PoFx). This structure is similar to [**STOR_POFX_DEVICE**](ns-storport-_stor_pofx_device.md) but allows the caller to specify an idle timeout value.

## -struct-fields

### -field Version

The version number of this structure. Set this member to **STOR_POFX_DEVICE_VERSION_V3**.

### -field Size

The size of this structure. Set this value to **STOR_POFX_DEVICE_V3_SIZE**.

### -field ComponentCount

The number of elements in the **Components** array. Set this member to 1. Currently, only a single component is supported for either a storage adapter or logical unit.

### -field Flags

The device power state capabilities flags. The miniport sets one or more of the *PoFx* device flags to enable or disable power state capabilities. **Flags** is a bitwise OR combination of the following.

| Flag value | Meaning |
| ---------- | ------- |
| STOR_POFX_DEVICE_FLAG_NO_D0 (0x01) | Requests that a power up IRP not be sent to the device object for the adapter or unit. |
| STOR_POFX_DEVICE_FLAG_NO_D3 (0x02) | Requests that a power down IRP not be sent to the device object for the adapter or unit. |
| STOR_POFX_DEVICE_FLAG_ENABLE_D3_COLD (0x04) | Enables Storport to set the D3 Cold state for the adapter if it supports it. This flag applies to adapters only. |
| STOR_POFX_DEVICE_FLAG_NO_DUMP_ACTIVE (0x08) | Indicates whether a device is available for dump when it is idle. The miniport is not able to bring the storage device active in dump mode if the device has entered the idle state or the power off when idle state. |
| STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT (0x10) | If the **STOR_POFX_DEVICE_V3** represents a unit, this flag indicates that the **UnitMinIdleTimeoutInMS** field should be honored. If the **STOR_POFX_DEVICE_V3** represents an adapter, this indicates the **AdapterIdleTimeoutInMS** field should be honored. |
| STOR_POFX_DEVICE_FLAG_ADAPTIVE_D3_IDLE_TIMEOUT (0x20) | Indicates that Storport should dynamically adjust the D3 idle timeout such that the device can aggressively enter D3 when necessary. This is valid only when **STOR_POFX_DEVICE_V3** is used. |
| STOR_POFX_DEVICE_FLAG_NO_UNIT_REGISTRATION (0x40) | Specifies that none of the units exposed by this adapter should be registered for runtime power management. This is valid only for **STOR_POFX_DEVICE** structures that represent an adapter. |
| STOR_POFX_DEVICE_FLAG_PERF_STATE_PEP_OPTIONAL (0x80) | Indicates the miniport does not require P-State support from the platform extension plug-in (PEP). When in doubt, set this flag. |
| STOR_POFX_DEVICE_FLAG_NO_IDLE_DEBOUNCE          (0x100) | Checks how capable the dump version of the miniport is at powering on the device when the device is in lower power states. |
| STOR_POFX_DEVICE_FLAG_DUMP_ALWAYS_POWER_ON      (0x200) | The miniport wants the dump stack to attempt to power on the device. |
| STOR_POFX_DEVICE_FLAG_DISABLE_INTERRUPTS_ON_D3  (0x400) | The miniport would like Storport to disable/ enable interrupts on Dx transitions. |
| STOR_POFX_DEVICE_FLAG_ADAPTER_D3_WAKE           (0x800) | The miniport isopt-in adapter D3 wake support.
| STOR_POFX_DEVICE_FLAG_GET_PERF_STATE_FROM_PEP   (0x1000) | The miniport requires P-states from the PEP. |

### -field UnitMinIdleTimeoutInMS

The minimum idle time in milliseconds for an unit. This value is only valid when STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT is set in **Flags**.

### -field AdapterIdleTimeoutInMS

The adapter idle timeout value in milliseconds. This value is only valid when STOR_POFX_DEVICE_FLAG_IDLE_TIMEOUT is set in **Flags**.

### -field MinimumPowerCyclePeriodInMS

Indicates that the device should not be power cycled (D0 -> D3 -> D0) more than once per the given period in milliseconds. This member is only valid when the STOR_POFX_DEVICE_FLAG_ADAPTIVE_D3_IDLE_TIMEOUT flag has been set.

### -field Components

This member is the first element in an array of one or more [**STOR_POFX_COMPONENT**](ns-storport-_stor_pofx_component.md) elements. If the array contains more than one element, the additional elements immediately follow the **STOR_POFX_DEVICE** structure. The array contains one element for each component in the device.  Currently, storage devices have only  one component so additional component structures are unnecessary.

## -remarks

To register a storage adapter for Storport PoFx support, the miniport driver calls [**StorPortEnablePassiveInitialization**](nf-storport-storportenablepassiveinitialization.md) in its [**HwStorInitialize**](nc-storport-hw_initialize.md) routine and implements a [**HwStorPassiveInitializeRoutine**](nc-storport-hw_passive_initialize_routine.md). The miniport calls [**StorPortInitializePoFxPower**](nf-storport-storportinitializepofxpower.md) within it's **HwStorPassiveInitializeRoutine** to provide information about the adapter component.

To register a storage unit for Storport PoFx support, the miniport driver implements the [**HwStorUnitControl**](nc-storport-hw_unit_control.md) callback routine and provides handling of the **ScsiUnitPoFxPowerInfo** unit control code. When the handling the **ScsiUnitPoFxPowerInfo** control code, the miniport calls [**StorPortInitializePoFxPower**](nf-storport-storportinitializepofxpower.md) if idle power management for the unit component is enabled.

The component for the storage device identified by its **Components** array index. Storage devices have only one component so the index of 0 is used.  Routines such as  [**StorPortPoFxActivateComponent**](nf-storport-storportpofxactivatecomponent.md) and [**StorPortPoFxIdleComponent**](nf-storport-storportpofxidlecomponent.md) use the array index of a component to identify the component.

## -see-also

[**STOR_POFX_COMPONENT**](ns-storport-_stor_pofx_component.md)

[**STOR_POFX_DEVICE**](ns-storport-_stor_pofx_device.md)

[**StorPortInitializePoFxPower**](nf-storport-storportinitializepofxpower.md)

[**StorPortPoFxActivateComponent**](nf-storport-storportpofxactivatecomponent.md)

[**StorPortPoFxIdleComponent**](nf-storport-storportpofxidlecomponent.md)
