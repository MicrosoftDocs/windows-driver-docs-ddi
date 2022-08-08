---
UID: NS:pep_x._PEP_COMPONENT_PERF_SET
title: _PEP_COMPONENT_PERF_SET (pep_x.h)
description: Learn how the PEP_COMPONENT_PERF_SET structure describes the performance states (P-states) in a P-state set.
old-location: kernel\pep_component_perf_set.htm
tech.root: kernel
ms.date: 08/05/2022
keywords: ["PEP_COMPONENT_PERF_SET structure"]
ms.keywords: "*PPEP_COMPONENT_PERF_SET, PEP_COMPONENT_PERF_SET, PEP_COMPONENT_PERF_SET structure [Kernel-Mode Driver Architecture], PPEP_COMPONENT_PERF_SET, PPEP_COMPONENT_PERF_SET structure pointer [Kernel-Mode Driver Architecture], _PEP_COMPONENT_PERF_SET, kernel.pep_component_perf_set, pepfx/PEP_COMPONENT_PERF_SET, pepfx/PPEP_COMPONENT_PERF_SET"
req.header: pep_x.h
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
req.typenames: PEP_COMPONENT_PERF_SET, *PPEP_COMPONENT_PERF_SET
f1_keywords:
 - _PEP_COMPONENT_PERF_SET
 - pep_x/_PEP_COMPONENT_PERF_SET
 - PPEP_COMPONENT_PERF_SET
 - pep_x/PPEP_COMPONENT_PERF_SET
 - PEP_COMPONENT_PERF_SET
 - pep_x/PEP_COMPONENT_PERF_SET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_COMPONENT_PERF_SET
 - PPEP_COMPONENT_PERF_SET
 - PEP_COMPONENT_PERF_SET
---

# _PEP_COMPONENT_PERF_SET structure (pep_x.h)

## -description

The **PEP_COMPONENT_PERF_SET** structure describes the performance states (P-states) in a P-state set.

## -struct-fields

### -field Name

An optional string that describes the device property controlled by this P-state set.  For example, this string might be "Clock frequency" or "Memory bandwidth". If no such string is available for this P-state, the **Name** member is set to NULL. Otherwise, this member contains a pointer to a [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that contains the string.

### -field Flags

Set to zero. No flag bits are currently defined for this member.

### -field Unit

A [PEP_PERF_STATE_UNIT](../pepfx/ne-pepfx-_pep_perf_state_unit.md) structure that specifies the units in which the performance values for this P-state set are expressed. Component performance can be expressed in hertz (frequency) or in bits per second (bandwidth).

### -field Type

A [PEP_PERF_STATE_TYPE](../pepfx/ne-pepfx-_pep_perf_state_type.md) enumeration value that indicates the type of performance information that is specified for this component. This member indicates whether the performance values for this P-state set are specified as a list of discrete values or as a continuous range of values.

### -field Discrete

The list of discrete performance values for this P-state set.

### -field Discrete.Count

The number of P-states in this P-state set.

### -field Discrete.States

A pointer to an array of [PEP_PERF_STATE](../pepfx/ns-pepfx-_pep_perf_state.md) structures, each of which describes a discrete performance value in this P-state set. The **Count** member specifies the number of elements in this array. A P-state is identified by its array index. If the array contains N elements, P-state indexes range from 0 to N–1.

### -field Range

The range of discrete performance measurement values for this P-state set.

### -field Range.Minimum

The minimum value in the range. This value is expressed in the units indicated by the **Unit** member.

### -field Range.Maximum

The maximum value in the range. This value is expressed in the units indicated by the **Unit** member.

## -remarks

The unnamed union contains the performance measurement values for this P-state. This union contains either a list of discrete values (if **Type** = **PepPerfStateTypeDiscrete**) or a continuous range of values (if **Type** = **PepPerfStateTypeRange**).

The **PerfStateSets** member of the [PEP_COMPONENT_PERF_INFO](../pepfx/ns-pepfx-_pep_component_perf_info.md) is the first element in an array of **PEP_COMPONENT_PERF_SET** structures. All members of the **PEP_COMPONENT_PERF_SET** structure contain input values that are supplied by the Windows [power management framework](../_kernel/index.md#device-power-management) (PoFx). The platform extension plug-in (PEP) must not write to this structure.

Device drivers use the [PO_FX_COMPONENT_PERF_SET](../wdm/ns-wdm-_po_fx_component_perf_set.md) structure, which is similar to the **PEP_COMPONENT_PERF_SET** structure.

## -see-also

- [PEP_COMPONENT_PERF_INFO](../pepfx/ns-pepfx-_pep_component_perf_info.md)
- [PEP_PERF_STATE](../pepfx/ns-pepfx-_pep_perf_state.md)
- [PEP_PERF_STATE_TYPE](../pepfx/ne-pepfx-_pep_perf_state_type.md)
- [PEP_PERF_STATE_UNIT](../pepfx/ne-pepfx-_pep_perf_state_unit.md)
- [PO_FX_COMPONENT_PERF_SET](../wdm/ns-wdm-_po_fx_component_perf_set.md)
- [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)
