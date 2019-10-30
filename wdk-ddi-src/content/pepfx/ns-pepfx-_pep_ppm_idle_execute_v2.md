---
UID: NS:pepfx._PEP_PPM_IDLE_EXECUTE_V2
title: _PEP_PPM_IDLE_EXECUTE_V2 (pepfx.h)
description: The PEP_PPM_IDLE_EXECUTE_V2 structure specifies the idle state that the processor is to enter.
old-location: kernel\pep_ppm_idle_execute_v2.htm
tech.root: kernel
ms.assetid: 28CF8291-E7C3-4289-909C-C89D350A9D83
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_IDLE_EXECUTE_V2, PEP_PPM_IDLE_EXECUTE_V2, PEP_PPM_IDLE_EXECUTE_V2 structure [Kernel-Mode Driver Architecture], PPEP_PPM_IDLE_EXECUTE_V2, PPEP_PPM_IDLE_EXECUTE_V2 structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_IDLE_EXECUTE_V2, kernel.pep_ppm_idle_execute_v2, pepfx/PEP_PPM_IDLE_EXECUTE_V2, pepfx/PPEP_PPM_IDLE_EXECUTE_V2"
ms.topic: struct
f1_keywords:
 - "pepfx/PEP_PPM_IDLE_EXECUTE_V2"
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
- PEP_PPM_IDLE_EXECUTE_V2
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_IDLE_EXECUTE_V2, *PPEP_PPM_IDLE_EXECUTE_V2
---

# _PEP_PPM_IDLE_EXECUTE_V2 structure


## -description


The <b>PEP_PPM_IDLE_EXECUTE_V2</b> structure specifies the idle state that the processor is to enter.


## -struct-fields




### -field Status

[out] An <b>NTSTATUS</b> value that indicates whether the processor idle state transition was successful. The platform extension plug-in (PEP) sets this member to <b>STATUS_SUCCESSFUL</b> if the transition succeeded. Otherwise, this member is set to an appropriate error status code.


### -field ProcessorState

[in] The index of the processor idle state that the processor is to enter. The PEP previously specified the supported processor idle states in response to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_idle_states_v2">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification. If the PEP specified N processor idle states, valid processor-idle-state indexes range from 0 to N-1.


### -field PlatformState

[in] The index of the platform idle state that the hardware platform will enter when the processor enters the processor idle state specified by <b>ProcessorState</b>. The PEP previously specified the supported platform idle states in response to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification. If the PEP specified M platform idle states, valid platform-idle-state indexes range from 0 to M-1. If no change in platform idle state will occur, this member will contain the value <b>PEP_PLATFORM_IDLE_STATE_NONE</b> (0xffffffff).


### -field CoordinatedStateCount

Supplies the number of coordinated idle states being entered by this transition.


### -field CoordinatedStates

Supplies a pointer to an array of coordinated idle states that are being entered by this transition.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_idle_execute">PEP_NOTIFY_PPM_IDLE_EXECUTE</a> notification. The <b>ProcessorState</b> and <b>PlatformState</b> members contain input values that are supplied by the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx). The <b>Status</b> member contains an output value that the PEP writes to this member.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_idle_execute">PEP_NOTIFY_PPM_IDLE_EXECUTE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_idle_states_v2">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>
 

 

