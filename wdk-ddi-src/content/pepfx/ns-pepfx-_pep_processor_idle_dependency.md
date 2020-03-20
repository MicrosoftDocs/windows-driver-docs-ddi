---
UID: NS:pepfx._PEP_PROCESSOR_IDLE_DEPENDENCY
title: _PEP_PROCESSOR_IDLE_DEPENDENCY (pepfx.h)
description: The PEP_PROCESSOR_IDLE_DEPENDENCY structure specifies the dependencies of a platform idle state on the specified processor.
old-location: kernel\pep_processor_idle_dependency.htm
tech.root: kernel
ms.assetid: 8C2C074B-3D59-416A-BCBD-2A0117F86776
ms.date: 04/30/2018
keywords: ["_PEP_PROCESSOR_IDLE_DEPENDENCY structure"]
ms.keywords: "*PPEP_PROCESSOR_IDLE_DEPENDENCY, PEP_PROCESSOR_IDLE_DEPENDENCY, PEP_PROCESSOR_IDLE_DEPENDENCY structure [Kernel-Mode Driver Architecture], PPEP_PROCESSOR_IDLE_DEPENDENCY, PPEP_PROCESSOR_IDLE_DEPENDENCY structure pointer [Kernel-Mode Driver Architecture], _PEP_PROCESSOR_IDLE_DEPENDENCY, kernel.pep_processor_idle_dependency, pepfx/PEP_PROCESSOR_IDLE_DEPENDENCY, pepfx/PPEP_PROCESSOR_IDLE_DEPENDENCY"
f1_keywords:
 - "pepfx/PEP_PROCESSOR_IDLE_DEPENDENCY"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_PROCESSOR_IDLE_DEPENDENCY
product:
- Windows
targetos: Windows
req.typenames: PEP_PROCESSOR_IDLE_DEPENDENCY, *PPEP_PROCESSOR_IDLE_DEPENDENCY
---

# _PEP_PROCESSOR_IDLE_DEPENDENCY structure


## -description


The <b>PEP_PROCESSOR_IDLE_DEPENDENCY</b> structure specifies the dependencies of a platform idle state on the specified processor.


## -struct-fields




### -field TargetProcessor

A <b>POHANDLE</b> value that identifies the processor. The platform extension plug-in (PEP) received this handle in a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field ExpectedState

The index of the processor idle state that this processor must enter to initiate the platform's transition to this platform idle state. If the <b>IdleStates</b> array in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_idle_states_v2">PEP_PPM_QUERY_IDLE_STATES_V2</a> structure contains N elements, the idle states are numbered 0 to N-1 in the order in which they appear in the array.


### -field AllowDeeperStates

Whether a secondary (subordinate) processor can be in a deeper processor idle state than <b>ExpectedState</b> and still satisfy the constraints of the transition to the platform idle state. Set this member to <b>TRUE</b> if a secondary processor in a deeper idle state can still satisfy the constraints, and to <b>FALSE</b> if it cannot. A primary processor (identified by the <b>TargetProcessor</b> member) can enter the selected idle state only after its secondary processors have entered their corresponding idle states.


### -field LooseDependency

Whether the platform idle state has a loose dependency on the idle state of this processor. Set this member to <b>TRUE</b> to indicate a loose dependency in which a best effort to synchronize the idle state transitions of the platform and processor is sufficient. Set to <b>FALSE</b> to indicate a dependency in which the operating system is required to strictly synchronize these transitions. If <b>LooseDependency</b> is <b>FALSE</b>, the <b>WakesSpuriously</b> bit in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_processor_idle_state_v2">PEP_PROCESSOR_IDLE_STATE_V2</a> structure for this processor must be <b>FALSE</b>.


## -remarks



The <b>DependencyArray</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_ppm_idle_select">PEP_PPM_IDLE_SELECT</a> structure is a pointer to an array of <b>PEP_PROCESSOR_IDLE_DEPENDENCY</b> structures. The <b>DependencyArray</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_platform_idle_state">PEP_PLATFORM_IDLE_STATE</a> structure is the first element in an array of <b>PEP_PROCESSOR_IDLE_DEPENDENCY</b> structures.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_platform_idle_state">PEP_PLATFORM_IDLE_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_ppm_idle_select">PEP_PPM_IDLE_SELECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_idle_states_v2">PEP_PPM_QUERY_IDLE_STATES_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_processor_idle_state_v2">PEP_PROCESSOR_IDLE_STATE_V2</a>
 

 

