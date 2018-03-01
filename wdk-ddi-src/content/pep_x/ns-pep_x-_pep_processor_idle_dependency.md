---
UID: NS:pep_x._PEP_PROCESSOR_IDLE_DEPENDENCY
title: "_PEP_PROCESSOR_IDLE_DEPENDENCY"
author: windows-driver-content
description: The PEP_PROCESSOR_IDLE_DEPENDENCY structure specifies the dependencies of a platform idle state on the specified processor.
old-location: kernel\pep_processor_idle_dependency.htm
old-project: kernel
ms.assetid: 8C2C074B-3D59-416A-BCBD-2A0117F86776
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPEP_PROCESSOR_IDLE_DEPENDENCY, PEP_PROCESSOR_IDLE_DEPENDENCY, PEP_PROCESSOR_IDLE_DEPENDENCY structure [Kernel-Mode Driver Architecture], PPEP_PROCESSOR_IDLE_DEPENDENCY, PPEP_PROCESSOR_IDLE_DEPENDENCY structure pointer [Kernel-Mode Driver Architecture], _PEP_PROCESSOR_IDLE_DEPENDENCY, kernel.pep_processor_idle_dependency, pepfx/PEP_PROCESSOR_IDLE_DEPENDENCY, pepfx/PPEP_PROCESSOR_IDLE_DEPENDENCY"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PROCESSOR_IDLE_DEPENDENCY
product: Windows
targetos: Windows
req.typenames: PEP_PROCESSOR_IDLE_DEPENDENCY, *PPEP_PROCESSOR_IDLE_DEPENDENCY, PEP_PROCESSOR_IDLE_DEPENDENCY, *PPEP_PROCESSOR_IDLE_DEPENDENCY
---

# _PEP_PROCESSOR_IDLE_DEPENDENCY structure


## -description


The <b>PEP_PROCESSOR_IDLE_DEPENDENCY</b> structure specifies the dependencies of a platform idle state on the specified processor.


## -syntax


````
typedef struct _PEP_PROCESSOR_IDLE_DEPENDENCY {
  POHANDLE TargetProcessor;
  UCHAR    ExpectedState;
  BOOLEAN  AllowDeeperStates;
  BOOLEAN  LooseDependency;
} PEP_PROCESSOR_IDLE_DEPENDENCY, *PPEP_PROCESSOR_IDLE_DEPENDENCY;
````


## -struct-fields




### -field TargetProcessor

A <b>POHANDLE</b> value that identifies the processor. The platform extension plug-in (PEP) received this handle in a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field ExpectedState

The index of the processor idle state that this processor must enter to initiate the platform's transition to this platform idle state. If the <b>IdleStates</b> array in the <a href="..\pepfx\ns-pepfx-_pep_ppm_query_idle_states_v2.md">PEP_PPM_QUERY_IDLE_STATES_V2</a> structure contains N elements, the idle states are numbered 0 to N-1 in the order in which they appear in the array.


### -field AllowDeeperStates

Whether a secondary (subordinate) processor can be in a deeper processor idle state than <b>ExpectedState</b> and still satisfy the constraints of the transition to the platform idle state. Set this member to <b>TRUE</b> if a secondary processor in a deeper idle state can still satisfy the constraints, and to <b>FALSE</b> if it cannot. A primary processor (identified by the <b>TargetProcessor</b> member) can enter the selected idle state only after its secondary processors have entered their corresponding idle states.


### -field LooseDependency

Whether the platform idle state has a loose dependency on the idle state of this processor. Set this member to <b>TRUE</b> to indicate a loose dependency in which a best effort to synchronize the idle state transitions of the platform and processor is sufficient. Set to <b>FALSE</b> to indicate a dependency in which the operating system is required to strictly synchronize these transitions. If <b>LooseDependency</b> is <b>FALSE</b>, the <b>WakesSpuriously</b> bit in the <a href="..\pepfx\ns-pepfx-_pep_processor_idle_state_v2.md">PEP_PROCESSOR_IDLE_STATE_V2</a> structure for this processor must be <b>FALSE</b>.


## -remarks



The <b>DependencyArray</b> member of the <a href="..\pep_x\ns-pep_x-_pep_ppm_idle_select.md">PEP_PPM_IDLE_SELECT</a> structure is a pointer to an array of <b>PEP_PROCESSOR_IDLE_DEPENDENCY</b> structures. The <b>DependencyArray</b> member of the <a href="..\pepfx\ns-pepfx-_pep_platform_idle_state.md">PEP_PLATFORM_IDLE_STATE</a> structure is the first element in an array of <b>PEP_PROCESSOR_IDLE_DEPENDENCY</b> structures.




## -see-also

<a href="..\pepfx\ns-pepfx-_pep_platform_idle_state.md">PEP_PLATFORM_IDLE_STATE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="..\pep_x\ns-pep_x-_pep_ppm_idle_select.md">PEP_PPM_IDLE_SELECT</a>



<a href="..\pepfx\ns-pepfx-_pep_processor_idle_state_v2.md">PEP_PROCESSOR_IDLE_STATE_V2</a>



<a href="..\pepfx\ns-pepfx-_pep_ppm_query_idle_states_v2.md">PEP_PPM_QUERY_IDLE_STATES_V2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PROCESSOR_IDLE_DEPENDENCY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

