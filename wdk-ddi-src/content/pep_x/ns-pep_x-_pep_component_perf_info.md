---
UID: NS:pep_x._PEP_COMPONENT_PERF_INFO
title: _PEP_COMPONENT_PERF_INFO (pep_x.h)
description: The PEP_COMPONENT_PERF_INFO structure describes the performance states (P-states) of a component.
old-location: kernel\pep_component_perf_info.htm
tech.root: kernel
ms.assetid: F05D67A0-6583-4C3E-B9AA-B99381A18047
ms.date: 04/30/2018
ms.keywords: "*PPEP_COMPONENT_PERF_INFO, PEP_COMPONENT_PERF_INFO, PEP_COMPONENT_PERF_INFO structure [Kernel-Mode Driver Architecture], PPEP_COMPONENT_PERF_INFO, PPEP_COMPONENT_PERF_INFO structure pointer [Kernel-Mode Driver Architecture], _PEP_COMPONENT_PERF_INFO, kernel.pep_component_perf_info, pepfx/PEP_COMPONENT_PERF_INFO, pepfx/PPEP_COMPONENT_PERF_INFO"
f1_keywords:
 - "pep_x/PEP_COMPONENT_PERF_INFO"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_COMPONENT_PERF_INFO
product:
- Windows
targetos: Windows
req.typenames: PEP_COMPONENT_PERF_INFO, *PPEP_COMPONENT_PERF_INFO
---

# _PEP_COMPONENT_PERF_INFO structure


## -description


The <b>PEP_COMPONENT_PERF_INFO</b> structure describes the performance states (P-states) of a component.


## -struct-fields




### -field SetCount

The number of elements in the <b>PerfStateSets</b> array.


### -field PerfStateSets

The first element in an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_set">PEP_COMPONENT_PERF_SET</a> structures. Each array element describes a P-state of the component. If the array contains more than one element, the additional elements immediately follow the end of the <b>PEP_COMPONENT_PERF_INFO</b> structure.


## -remarks



This structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_component_perf_states">PEP_DPM_REGISTER_COMPONENT_PERF_STATES</a> notification. The <b>PerfStateSets</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_component_perf_states">PEP_REGISTER_COMPONENT_PERF_STATES</a> structure is a <b>PEP_COMPONENT_PERF_INFO</b> structure.

The <b>PEP_COMPONENT_PERF_INFO</b> structure contains input values that are supplied by the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx). The platform extension plug-in (PEP) must not write to this structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_info">PEP_COMPONENT_PERF_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_component_perf_set">PEP_COMPONENT_PERF_SET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_component_perf_states">PEP_DPM_REGISTER_COMPONENT_PERF_STATES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_component_perf_states">PEP_REGISTER_COMPONENT_PERF_STATES</a>
 

 

