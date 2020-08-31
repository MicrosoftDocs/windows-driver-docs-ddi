---
UID: NS:pepfx._PEP_PERF_STATE
title: _PEP_PERF_STATE (pepfx.h)
description: The PEP_PERF_STATE structure describes a performance state (P-state) in a P-state set in which the P-states are specified as a list of one or more discrete values.
old-location: kernel\pep_perf_state.htm
tech.root: kernel
ms.assetid: D5C9EF42-B6FE-4472-8188-2B23F87FA475
ms.date: 04/30/2018
keywords: ["PEP_PERF_STATE structure"]
ms.keywords: "*PPEP_PERF_STATE, PEP_PERF_STATE, PEP_PERF_STATE structure [Kernel-Mode Driver Architecture], PPEP_PERF_STATE, PPEP_PERF_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_PERF_STATE, kernel.pep_perf_state, pepfx/PEP_PERF_STATE, pepfx/PPEP_PERF_STATE"
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
req.typenames: PEP_PERF_STATE, *PPEP_PERF_STATE
f1_keywords:
 - _PEP_PERF_STATE
 - pepfx/_PEP_PERF_STATE
 - PPEP_PERF_STATE
 - pepfx/PPEP_PERF_STATE
 - PEP_PERF_STATE
 - pepfx/PEP_PERF_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_PERF_STATE
---

# _PEP_PERF_STATE structure


## -description

The <b>PEP_PERF_STATE</b> structure describes a performance state (P-state) in a P-state set in which the P-states are specified as a list of one or more discrete values.

## -struct-fields

### -field Value

The discrete value represented by this P-state. For more information, see Remarks.

### -field Context

A pointer to PEP-defined context data. The PEP uses this context to contain additional information about the discrete performance level that cannot be expressed in the <b>Value</b> member. This context is opaque to the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx). The <b>Context</b> member is optional and can be set to NULL.

## -remarks

The <b>Discrete.States</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_set">PEP_COMPONENT_PERF_SET</a> structure is a pointer to an array of <b>PEP_PERF_STATE</b> structures. The <b>Unit</b> member of the <b>PEP_COMPONENT_PERF_SET</b> structure specifies the units in which the <b>Value</b> member in each array element is expressed. Component performance can be expressed in hertz (frequency) or in bits per second (bandwidth). For example, if <b>Value</b> = 100,000,000 and <b>Unit</b> = <b>PepPerfStateUnitFrequency</b>, this performance state represents a frequency of 100 megahertz.

Device drivers use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_perf_state">PO_FX_PERF_STATE</a> structure, which is similar to the <b>PEP_PERF_STATE</b> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_set">PEP_COMPONENT_PERF_SET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_perf_state">PO_FX_PERF_STATE</a>

