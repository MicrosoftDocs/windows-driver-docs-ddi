---
UID: NS:pepfx._PEP_PROCESSOR_IDLE_STATE_V2
title: _PEP_PROCESSOR_IDLE_STATE_V2 (pepfx.h)
description: The PEP_PROCESSOR_IDLE_STATE_V2 structure describes a processor idle state that the platform extension plug-in (PEP) supports.
old-location: kernel\pep_processor_idle_state_v2.htm
tech.root: kernel
ms.assetid: DEA8B166-5236-4BE3-B16D-9EE1B34796F8
ms.date: 04/30/2018
ms.keywords: "*PPEP_PROCESSOR_IDLE_STATE_V2, PEP_PROCESSOR_IDLE_STATE_V2, PEP_PROCESSOR_IDLE_STATE_V2 structure [Kernel-Mode Driver Architecture], PPEP_PROCESSOR_IDLE_STATE_V2, PPEP_PROCESSOR_IDLE_STATE_V2 structure pointer [Kernel-Mode Driver Architecture], _PEP_PROCESSOR_IDLE_STATE_V2, kernel.pep_processor_idle_state_v2, pepfx/PEP_PROCESSOR_IDLE_STATE_V2, pepfx/PPEP_PROCESSOR_IDLE_STATE_V2"
ms.topic: struct
f1_keywords:
 - "pepfx/PEP_PROCESSOR_IDLE_STATE_V2"
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
- PEP_PROCESSOR_IDLE_STATE_V2
product:
- Windows
targetos: Windows
req.typenames: PEP_PROCESSOR_IDLE_STATE_V2, *PPEP_PROCESSOR_IDLE_STATE_V2
---

# _PEP_PROCESSOR_IDLE_STATE_V2 structure


## -description


The <b>PEP_PROCESSOR_IDLE_STATE_V2</b> structure describes a processor idle state that the platform extension plug-in (PEP) supports.


## -struct-fields




### -field Ulong

 


### -field Interruptible

 


### -field CacheCoherent

 


### -field ThreadContextRetained

 


### -field CStateType

 


### -field WakesSpuriously

 


### -field PlatformOnly

 


### -field Autonomous

 


### -field Reserved

 


### -field Latency

The worst-case latency, in 100-nanosecond units,  that the processor requires to wake from this idle state in response to a wake event.


### -field BreakEvenDuration

The minimum amount of time, specified in 100-nanosecond units, that the processor must spend in this idle state to make a transition to this state worthwhile. The Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">power management framework</a> (PoFx) uses this member value as a hint to avoid switching a processor to an idle state unless the processor is likely to remain in this state for at least the amount of time specified by <b>BreakEvenDuration</b>.


#### - ( unnamed union )

A collection of flag bits and status fields that can be accessed either individually as bitfields, or together as a 32-bit unsigned integer value.



#### Ulong

Flag bits and status fields accessed as a single 32-bit unsigned integer value.



#### ( unnamed struct )

Flag bits and status fields accessed as individual bitfields.



##### Interruptible

Whether the processor can respond to interrupts when in this idle state. Set this flag bit to 1 if the processor can respond to interrupts, and to 0 if it cannot.



##### CacheCoherent

Whether the processor's local cache or caches remain coherent through the duration of this processor idle state. Set this flag bit to 1 if cache coherency is maintained in this idle state, and to 0 if it is not.



##### ThreadContextRetained

Whether thread context is retained in this processor idle state. Set this flag bit to 1 if the processor hardware retains the thread context across the idle transition. Set to 0 if the processor uses the multiprocessor parking protocol to exit the idle state and return control to the operating system. For more information about this protocol, see the document titled "Multiprocessor Startup for ARM Platforms" at <a href="https://www.acpica.org/related-documents">https://www.acpica.org/related-documents</a>.



##### CStateType

The C-state type of the processor idle state. Set this bitfield to zero if this idle state does not correspond to an ACPI-defined C-state. Otherwise, set this bitfield to the C-state number. That is, set <b>CStateType</b> = 1 for C1, set <b>CStateType</b> = 2 for C2, and so on. For more information about C-states, see section 8.1, "Processor Power States", of the [ACPI 5.0 specification](https://uefi.org/specifications).



##### WakesSpuriously

Whether the processor can wake spuriously in this idle state. Set this flag bit to 0 if the processor is guaranteed to stay in this idle state until it receives a device interrupt, inter-processor interrupt (IPI), or wake request. Set to 1 if the processor might wake autonomously for some other reason.



##### PlatformOnly

Whether the transition to this processor idle state can be performed only as part of a coordinated transition to a platform-wide idle state. Set this flag bit to 1 if the processor idle state transition can be performed only as part of a transition to a platform idle state. Otherwise, set to 0.



##### Autonomous

Whether a coordinated transition to this processor idle state is performed autonomously by the processor hardware. Set this flag bit to 1 if these transitions are autonomous, and to 0 if they are not. A flag value of 1 indicates that the idle state can be entered without sending a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_ppm_test_idle_state">PEP_NOTIFY_PPM_TEST_IDLE_STATE</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_processor_idle_state_v2">PEP_NOTIFY_PPM_IDLE_PRE_EXECUTE</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_ppm_idle_complete">PEP_NOTIFY_PPM_IDLE_COMPLETE</a> notification. This flag can be set to 1 only if <b>CStateType</b> is nonzero.



##### Reserved

Reserved for future use. Set to zero.


## -remarks



This structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_ppm_query_idle_states_v2">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification. The <b>IdleStates</b>  member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_ppm_query_idle_states_v2">PEP_PPM_QUERY_IDLE_STATES_V2</a> structure is the first element in an array of <b>PEP_PROCESSOR_IDLE_STATE_V2</b> structures.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_ppm_query_idle_states_v2">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_ppm_query_idle_states_v2">PEP_PPM_QUERY_IDLE_STATES_V2</a>
 

 

