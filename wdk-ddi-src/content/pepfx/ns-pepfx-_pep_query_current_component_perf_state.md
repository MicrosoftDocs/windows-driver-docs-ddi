---
UID: NS:pepfx._PEP_QUERY_CURRENT_COMPONENT_PERF_STATE
title: _PEP_QUERY_CURRENT_COMPONENT_PERF_STATE (pepfx.h)
description: The PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure contains information about the current P-state in the specified P-state set.
old-location: kernel\pep_query_current_component_perf_state.htm
tech.root: kernel
ms.assetid: 2A561853-B809-4BF5-911C-520A7D9C473C
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
 - PEP_QUERY_CURRENT_COMPONENT_PERF_STATE
---

# _PEP_QUERY_CURRENT_COMPONENT_PERF_STATE structure (pepfx.h)


## -description

The <b>PEP_QUERY_CURRENT_COMPONENT_PERF_STATE</b> structure contains information about the current P-state in the specified P-state set.

## -struct-fields

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.

### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

### -field Set

[in] The index that identifies this P-state set. If M is the number of P-state sets for this component, P-state set indexes range from 0 to M–1. The PEP previously specified the number of P-state sets in response to a <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_query_component_perf_capabilities">PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES</a> notification.

### -field StateIndex

### -field StateValue

 




#### - ( unnamed union )

The current performance level of this P-state set expressed either as an index into a set of discrete values or as a value in a range. In response to a previous <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_query_component_perf_set">PEP_DPM_QUERY_COMPONENT_PERF_SET</a> notification, the PEP indicated whether the performance values in the P-state set are of type <b>PoFxPerfStateTypeDiscrete</b> or <b>PoFxPerfStateTypeRange</b>.



#### StateIndex

[out] The index of the current P-state for the specified P-state set. Write to this member if the performance values for the P-state set are of type <b>PoFxPerfStateTypeDiscrete</b>.



#### StateValue

[out] The value of the current P-state for the specified P-state set. Write to this member if the performance values for the P-state set are of type <b>PoFxPerfStateTypeRange</b>.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_query_current_component_perf_state">PEP_DPM_QUERY_CURRENT_COMPONENT_PERF_STATE</a> notification. The <b>DeviceHandle</b>, <b>Component</b>, and <b>Set</b> members contain input values supplied by the Windows <a href="/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) when this notification is sent. The <b>StateIndex</b> member or <b>StateValue</b> member contains an output value that the PEP writes to the structure in response to the notification.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_query_current_component_perf_state">PEP_DPM_QUERY_CURRENT_COMPONENT_PERF_STATE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>