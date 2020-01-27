---
UID: NS:pep_x._PEP_PPM_QUERY_IDLE_STATES_V2
title: _PEP_PPM_QUERY_IDLE_STATES_V2 (pep_x.h)
description: The PEP_PPM_QUERY_IDLE_STATES_V2 structure is used during processor initialization to query the platform extension plug-in (PEP) for a list of processor idle states that the processor supports.
old-location: kernel\pep_ppm_query_idle_states_v2.htm
tech.root: kernel
ms.assetid: 0C225F3B-0D09-48FD-9BD3-F17D5E602698
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_QUERY_IDLE_STATES_V2, PEP_PPM_QUERY_IDLE_STATES_V2, PEP_PPM_QUERY_IDLE_STATES_V2 structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_IDLE_STATES_V2, PPEP_PPM_QUERY_IDLE_STATES_V2 structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_IDLE_STATES_V2, kernel.pep_ppm_query_idle_states_v2, pepfx/PEP_PPM_QUERY_IDLE_STATES_V2, pepfx/PPEP_PPM_QUERY_IDLE_STATES_V2"
f1_keywords:
 - "pep_x/PEP_PPM_QUERY_IDLE_STATES_V2"
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
- PEP_PPM_QUERY_IDLE_STATES_V2
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_IDLE_STATES_V2, *PPEP_PPM_QUERY_IDLE_STATES_V2
---

# _PEP_PPM_QUERY_IDLE_STATES_V2 structure


## -description


The <b>PEP_PPM_QUERY_IDLE_STATES_V2</b> structure is used during processor initialization to query the platform extension plug-in (PEP) for a list of processor idle states that the processor supports.


## -struct-fields




### -field Count

[in] The number of elements in the <b>IdleStates</b> array. The Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) previously sent the PEP a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_capabilities">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a> notification to determine this number.


### -field IdleStates

[out] The first element in an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_processor_idle_state_v2">PEP_PROCESSOR_IDLE_STATE_V2</a> structures that describe the processor idle states. If this array contains more than one element, the addition array elements follow the end of the <b>PEP_PPM_QUERY_IDLE_STATES_V2</b> structure.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_idle_states_v2">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification. The <b>Count</b> member of the <b>PEP_PPM_QUERY_IDLE_STATES_V2</b> structure contains an input value that is supplied by the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx). The <b>IdleStates</b> array elements contain output values that the PEP writes to the structure in response to this notification.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_capabilities">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_idle_states_v2">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_processor_idle_state_v2">PEP_PROCESSOR_IDLE_STATE_V2</a>
 

 

