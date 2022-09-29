---
UID: NS:pepfx._PEP_QUERY_COMPONENT_PERF_SET
title: _PEP_QUERY_COMPONENT_PERF_SET (pepfx.h)
description: The PEP_QUERY_COMPONENT_PERF_SET structure contains query information about a set of performance state values (P-state set) for a component.
old-location: kernel\pep_query_component_perf_set.htm
tech.root: kernel
ms.date: 08/10/2022
keywords: ["PEP_QUERY_COMPONENT_PERF_SET structure"]
ms.keywords: "*PPEP_QUERY_COMPONENT_PERF_SET, PEP_QUERY_COMPONENT_PERF_SET, PEP_QUERY_COMPONENT_PERF_SET structure [Kernel-Mode Driver Architecture], PPEP_QUERY_COMPONENT_PERF_SET, PPEP_QUERY_COMPONENT_PERF_SET structure pointer [Kernel-Mode Driver Architecture], _PEP_QUERY_COMPONENT_PERF_SET, kernel.pep_query_component_perf_set, pepfx/PEP_QUERY_COMPONENT_PERF_SET, pepfx/PPEP_QUERY_COMPONENT_PERF_SET"
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.typenames: PEP_QUERY_COMPONENT_PERF_SET, *PPEP_QUERY_COMPONENT_PERF_SET
f1_keywords:
 - _PEP_QUERY_COMPONENT_PERF_SET
 - pepfx/_PEP_QUERY_COMPONENT_PERF_SET
 - PPEP_QUERY_COMPONENT_PERF_SET
 - pepfx/PPEP_QUERY_COMPONENT_PERF_SET
 - PEP_QUERY_COMPONENT_PERF_SET
 - pepfx/PEP_QUERY_COMPONENT_PERF_SET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_QUERY_COMPONENT_PERF_SET
 - PPEP_QUERY_COMPONENT_PERF_SET
 - PEP_QUERY_COMPONENT_PERF_SET
---

# _PEP_QUERY_COMPONENT_PERF_SET structure (pepfx.h)

## -description

The **PEP_QUERY_COMPONENT_PERF_SET** structure contains query information about a set of performance state values (P-state set) for a component.

## -struct-fields

### -field DeviceHandle

A **PEPHANDLE** value that identifies the device. The PEP supplied this handle in response to a previous [PEP_DPM_REGISTER_DEVICE](./ns-pepfx-_pep_register_crashdump_device.md) notification.

### -field Component

The index that identifies the component. This member is an index into the *Components* array in the [PEP_DEVICE_REGISTER_V2](./ns-pepfx-_pep_device_register_v2.md) structure that the PEP previously supplied in response to the **PEP_DPM_REGISTER_DEVICE** notification for this device. If the *Components* array contains N elements, component indexes range from 0 to N–1.

### -field Set

The index that identifies this P-state set. If this component has M P-state sets, P-state set indexes range from 0 to M–1. The PEP previously specified the number of P-state sets in response to a [PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES](./ns-pepfx-_pep_query_component_perf_capabilities.md) notification.

### -field Flags

A set of input flags. No flag bits are currently defined for this member, which is always zero.

### -field Unit

A [PEP_PERF_STATE_UNIT](./ne-pepfx-_pep_perf_state_unit.md) enumeration value that indicates whether the values for this P-state set are expressed in hertz (frequency units) or bits per second (bandwidth units).

### -field Type

A [PEP_PERF_STATE_TYPE](./ne-pepfx-_pep_perf_state_type.md) enumeration value that indicates whether the performance values for this P-state set are expressed as a list of discrete values or as a continuous range of values.

### -field Discrete

Use this structure if `Type == PepPerfStateTypeDiscrete`.

### -field Discrete.Count

The number of discrete performance values in this P-state set.

### -field Range

Use this structure if `Type == PepPerfStateTypeRange`.

### -field Range.Minimum

The minimum value in the range of performance values for this P-state set. This value is expressed in the measurement units indicated by the *Unit* member.

### -field Range.Maximum

The maximum value in the range of performance values for this P-state set. This value is expressed in the measurement units indicated by the *Unit* member.

## -remarks

This structure is used by the [PEP_DPM_QUERY_COMPONENT_PERF_SET](./ns-pepfx-_pep_query_component_perf_set.md) notification. The *DeviceHandle*, *Component*, *Set*, and *Flags* members contain input values that are supplied by the Windows [power management framework](../_kernel/index.md#device-power-management) (PoFx) when this notification is sent. The *Discrete* member or *Range* member contains an output value that the PEP writes to the structure in response to the notification.

The unnamed union contains either the number of discrete performance values in this P-state set, or the range of values in this P-state set.

## -see-also

- [PEP_DEVICE_REGISTER_V2](./ns-pepfx-_pep_device_register_v2.md)
- [PEP_DPM_QUERY_COMPONENT_PERF_SET](./ns-pepfx-_pep_query_component_perf_set.md)
- [PEP_DPM_REGISTER_DEVICE](./ns-pepfx-_pep_register_crashdump_device.md)
- [PEP_PERF_STATE_TYPE](./ne-pepfx-_pep_perf_state_type.md) [PEP_PERF_STATE_UNIT](./ne-pepfx-_pep_perf_state_unit.md)
