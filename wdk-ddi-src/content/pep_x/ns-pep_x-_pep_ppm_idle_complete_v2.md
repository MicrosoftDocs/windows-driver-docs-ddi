---
UID: NS:pep_x._PEP_PPM_IDLE_COMPLETE_V2
title: "_PEP_PPM_IDLE_COMPLETE_V2"
author: windows-driver-content
description: The PEP_PPM_IDLE_COMPLETE_V2 structure describe the idle states from which the processor and hardware platform are waking.
old-location: kernel\pep_ppm_idle_complete_v2.htm
old-project: kernel
ms.assetid: 2807D1D7-DCAF-446C-8DAD-CAF244B52CD2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PPEP_PPM_IDLE_COMPLETE_V2, PPEP_PPM_IDLE_COMPLETE_V2, PEP_PPM_IDLE_COMPLETE_V2, PEP_PPM_IDLE_COMPLETE_V2 structure [Kernel-Mode Driver Architecture], pepfx/PPEP_PPM_IDLE_COMPLETE_V2, kernel.pep_ppm_idle_complete_v2, _PEP_PPM_IDLE_COMPLETE_V2, pepfx/PEP_PPM_IDLE_COMPLETE_V2, PPEP_PPM_IDLE_COMPLETE_V2 structure pointer [Kernel-Mode Driver Architecture]"
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
-	PEP_PPM_IDLE_COMPLETE_V2
product: Windows
targetos: Windows
req.typenames: PEP_PPM_IDLE_COMPLETE_V2, *PPEP_PPM_IDLE_COMPLETE_V2, PEP_PPM_IDLE_COMPLETE_V2, *PPEP_PPM_IDLE_COMPLETE_V2
---

# _PEP_PPM_IDLE_COMPLETE_V2 structure


## -description


The <b>PEP_PPM_IDLE_COMPLETE_V2</b> structure describe the idle states from which the processor and hardware platform are waking.


## -syntax


````
typedef struct _PEP_PPM_IDLE_COMPLETE_V2 {
  ULONG ProcessorState;
  ULONG PlatformState;
} PEP_PPM_IDLE_COMPLETE_V2, *PPEP_PPM_IDLE_COMPLETE_V2;
````


## -struct-fields




### -field ProcessorState

[in] An index that identifies the idle state from which the processor is waking. The platform extension plug-in (PEP) previously specified the supported processor idle states in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification. If the PEP specified N processor idle states, valid processor-idle-state indexes range from 0 to N-1. When the hypervisor is enabled and the platform wakes from an idle state, this member is set to <b>PEP_PROCESSOR_IDLE_STATE_UNKNOWN</b> (0xffffffff). For more information, see <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186803">PEP_NOTIFY_PPM_IDLE_COMPLETE</a>.


### -field PlatformState

[in] An index that identifies the idle state from which the platform is waking. The PEP previously specified the supported platform idle states in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification. If the PEP specified M platform idle states, valid platform-idle-state indexes range from 0 to M-1. If the transition from the processor idle state does not involve a transition from an platform idle state, this member will contain the value <b>PEP_PLATFORM_IDLE_STATE_NONE</b> (0xffffffff).


### -field CoordinatedStateCount

 


### -field CoordinatedStates

 




## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186803">PEP_NOTIFY_PPM_IDLE_COMPLETE</a> notification. The <b>ProcessorState</b> and <b>PlatformState</b> members contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) when this notification is sent to the PEP.



