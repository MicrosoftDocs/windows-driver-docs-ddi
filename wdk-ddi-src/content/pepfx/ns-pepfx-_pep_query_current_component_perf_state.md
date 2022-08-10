---
UID: NS:pepfx._PEP_QUERY_CURRENT_COMPONENT_PERF_STATE
title: _PEP_QUERY_CURRENT_COMPONENT_PERF_STATE (pepfx.h)
description: The PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure contains information about the current P-state in the specified P-state set.
old-location: kernel\pep_query_current_component_perf_state.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure"]
ms.keywords: "*PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE, PEP_QUERY_CURRENT_COMPONENT_PERF_STATE, PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure [Kernel-Mode Driver Architecture], PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE, PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_QUERY_CURRENT_COMPONENT_PERF_STATE, kernel.pep_query_current_component_perf_state, pepfx/PEP_QUERY_CURRENT_COMPONENT_PERF_STATE, pepfx/PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE"
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
req.typenames: PEP_QUERY_CURRENT_COMPONENT_PERF_STATE, *PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE
f1_keywords:
 - _PEP_QUERY_CURRENT_COMPONENT_PERF_STATE
 - pepfx/_PEP_QUERY_CURRENT_COMPONENT_PERF_STATE
 - PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE
 - pepfx/PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE
 - PEP_QUERY_CURRENT_COMPONENT_PERF_STATE
 - pepfx/PEP_QUERY_CURRENT_COMPONENT_PERF_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_QUERY_CURRENT_COMPONENT_PERF_STATE
 - PPEP_QUERY_CURRENT_COMPONENT_PERF_STATE
 - PEP_QUERY_CURRENT_COMPONENT_PERF_STATE
---

# _PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure (pepfx.h)

## -description

The **PEP_QUERY_CURRENT_COMPONENT_PERF_STATE** structure contains information about the current P-state in the specified P-state set.

## -struct-fields

### -field DeviceHandle

A **PEPHANDLE** value that identifies the device. The PEP supplied this handle in response to a previous [PEP_DPM_REGISTER_DEVICE](./ns-pepfx-_pep_register_crashdump_device.md) notification.

### -field Component

The index that identifies the component. This member is an index into the *Components* array in the [PEP_DEVICE_REGISTER_V2](./ns-pepfx-_pep_device_register_v2.md) structure that the PEP previously supplied in response to the **PEP_DPM_REGISTER_DEVICE** notification for this device. If the *Components* array contains N elements, component indexes range from 0 to N–1.

### -field Set

The index that identifies this P-state set. If M is the number of P-state sets for this component, P-state set indexes range from 0 to M–1. The PEP previously specified the number of P-state sets in response to a [PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES](./ns-pepfx-_pep_query_component_perf_capabilities.md) notification.

### -field StateIndex

The index of the current P-state for the specified P-state set. Write to this member if the performance values for the P-state set are of type **PoFxPerfStateTypeDiscrete**.

### -field StateValue

The value of the current P-state for the specified P-state set. Write to this member if the performance values for the P-state set are of type **PoFxPerfStateTypeRange**.

## -remarks

This structure is used by the [PEP_DPM_QUERY_CURRENT_COMPONENT_PERF_STATE](./ns-pepfx-_pep_query_current_component_perf_state.md) notification. The *DeviceHandle*, *Component*, and *Set* members contain input values supplied by the Windows [power management framework](../_kernel/index.md#device-power-management) (PoFx) when this notification is sent. The *StateIndex* member or *StateValue* member contains an output value that the PEP writes to the structure in response to the notification.

The unnamed union contains the current performance level of this P-state set expressed either as an index into a set of discrete values or as a value in a range. In response to a previous [PEP_DPM_QUERY_COMPONENT_PERF_SET](./ns-pepfx-_pep_query_component_perf_set.md) notification, the PEP indicated whether the performance values in the P-state set are of type **PoFxPerfStateTypeDiscrete** or **PoFxPerfStateTypeRange**.

## -see-also

- [PEP_DPM_REGISTER_DEVICE](./ns-pepfx-_pep_register_crashdump_device.md)
- [PEP_DEVICE_REGISTER_V2](./ns-pepfx-_pep_device_register_v2.md)
- [PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES](./ns-pepfx-_pep_query_component_perf_capabilities.md)
- [PEP_DPM_QUERY_CURRENT_COMPONENT_PERF_STATE](./ns-pepfx-_pep_query_current_component_perf_state.md)
- [PEP_DPM_QUERY_COMPONENT_PERF_SET](./ns-pepfx-_pep_query_component_perf_set.md)
