---
UID: NS:pep_x._PEP_PLATFORM_IDLE_STATE
title: "_PEP_PLATFORM_IDLE_STATE"
author: windows-driver-content
description: The PEP_PLATFORM_IDLE_STATE structure specifies the properties of a platform idle state.
old-location: kernel\pep_platform_idle_state.htm
old-project: kernel
ms.assetid: D0503B73-EDFA-4742-BAFA-4FEE56F0A3C8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PEP_PLATFORM_IDLE_STATE structure [Kernel-Mode Driver Architecture], PEP_PLATFORM_IDLE_STATE, pepfx/PPEP_PLATFORM_IDLE_STATE, PPEP_PLATFORM_IDLE_STATE, kernel.pep_platform_idle_state, pepfx/PEP_PLATFORM_IDLE_STATE, *PPEP_PLATFORM_IDLE_STATE, _PEP_PLATFORM_IDLE_STATE, PPEP_PLATFORM_IDLE_STATE structure pointer [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_PLATFORM_IDLE_STATE
product: Windows
targetos: Windows
req.typenames: PEP_PLATFORM_IDLE_STATE, *PPEP_PLATFORM_IDLE_STATE, PEP_PLATFORM_IDLE_STATE, *PPEP_PLATFORM_IDLE_STATE
---

# _PEP_PLATFORM_IDLE_STATE structure


## -description


The <b>PEP_PLATFORM_IDLE_STATE</b> structure specifies the properties of a platform idle state.


## -syntax


````
typedef struct _PEP_PLATFORM_IDLE_STATE {
  POHANDLE                                                                                   InitiatingProcessor;
  UCHAR                                                                                      InitiatingState;
  ULONG                                                                                      Latency;
  ULONG                                                                                      BreakEvenDuration;
  _Field_range_(0, DependencyArrayCount) ULONG                                               DependencyArrayUsed;
  ULONG                                                                                      DependencyArrayCount;
  _Field_size_part_(DependencyArrayCount, DependencyArrayUsed) PEP_PROCESSOR_IDLE_DEPENDENCY DependencyArray[ANYSIZE_ARRAY];
} PEP_PLATFORM_IDLE_STATE, *PPEP_PLATFORM_IDLE_STATE;
````


## -struct-fields




### -field InitiatingProcessor

A <b>POHANDLE</b> value that identifies the processor that initiates the transition to this platform idle state, or <b>NULL</b> if any processor can initiate the transition. If non-NULL, this handle represents the registration of the processor (as a device) with the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).


### -field InitiatingState

The index of the processor idle state that the processor enters to initiate the platform's entry to the specified platform idle state. If the <b>IdleStates</b> array in the <a href="..\pep_x\ns-pep_x-_pep_ppm_query_coordinated_states.md">PEP_PPM_QUERY_IDLE_STATES_V2</a> structure contains N elements, the idle states are numbered 0 to Nâ€“1 in the order in which they appear in the array.


### -field Latency

The worst-case latency, in 100-nanosecond units, that the platform requires to wake from this idle state in response to a wake event.


### -field BreakEvenDuration

The minimum amount of time, specified in 100-nanosecond units, that the platform must spend in this idle state to make a transition to this state worthwhile. PoFx uses this member value as a hint to avoid switching the platform to an idle state unless the platform is likely to remain in this state for at least the amount of time specified by <b>BreakEvenDuration</b>.




### -field DependencyArrayUsed

The number of items in <b>DependencyArray</b> which were filled in by the PEP.


### -field DependencyArrayCount

The number of elements in the <b>DependencyArray</b> array. The array contains one element for each processor in the hardware platform.


### -field DependencyArray

The first element in an array of <a href="..\pep_x\ns-pep_x-_pep_processor_idle_dependency.md">PEP_PROCESSOR_IDLE_DEPENDENCY</a> structures. This array specifies the set of dependencies that the platform idle state has on each processor. If the platform contains N processors, the array contains N elements, and processors are numbered 0 to N-1 in the order in which they are represented in the array.


## -remarks



This structure is used in conjunction with the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a> notification. The <b>State</b> member of a <a href="..\pep_x\ns-pep_x-_pep_ppm_query_platform_state.md">PEP_PPM_QUERY_PLATFORM_STATE</a> structure is a <b>PEP_PLATFORM_IDLE_STATE</b> structure.




## -see-also

<a href="..\pep_x\ns-pep_x-_pep_processor_idle_dependency.md">PEP_PROCESSOR_IDLE_DEPENDENCY</a>



<a href="..\pep_x\ns-pep_x-_pep_ppm_query_coordinated_states.md">PEP_PPM_QUERY_IDLE_STATES_V2</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a>



<a href="..\pep_x\ns-pep_x-_pep_ppm_query_platform_state.md">PEP_PPM_QUERY_PLATFORM_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PLATFORM_IDLE_STATE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

