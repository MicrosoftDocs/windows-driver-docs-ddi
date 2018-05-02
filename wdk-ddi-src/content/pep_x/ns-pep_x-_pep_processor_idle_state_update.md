---
UID: NS:pep_x._PEP_PROCESSOR_IDLE_STATE_UPDATE
title: "_PEP_PROCESSOR_IDLE_STATE_UPDATE"
author: windows-driver-content
description: The PEP_PROCESSOR_IDLE_STATE_UPDATE structure contains the updated properties of a processor idle state.
old-location: kernel\pep_processor_idle_state_update.htm
old-project: kernel
ms.assetid: A05617FB-5105-4FCA-807F-C49F32BD1399
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PPEP_PROCESSOR_IDLE_STATE_UPDATE, PEP_PROCESSOR_IDLE_STATE_UPDATE, PEP_PROCESSOR_IDLE_STATE_UPDATE structure [Kernel-Mode Driver Architecture], PPEP_PROCESSOR_IDLE_STATE_UPDATE, PPEP_PROCESSOR_IDLE_STATE_UPDATE structure pointer [Kernel-Mode Driver Architecture], _PEP_PROCESSOR_IDLE_STATE_UPDATE, kernel.pep_processor_idle_state_update, pepfx/PEP_PROCESSOR_IDLE_STATE_UPDATE, pepfx/PPEP_PROCESSOR_IDLE_STATE_UPDATE"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PROCESSOR_IDLE_STATE_UPDATE
product: Windows
targetos: Windows
req.typenames: PEP_PROCESSOR_IDLE_STATE_UPDATE, *PPEP_PROCESSOR_IDLE_STATE_UPDATE
---

# _PEP_PROCESSOR_IDLE_STATE_UPDATE structure


## -description


The <b>PEP_PROCESSOR_IDLE_STATE_UPDATE</b> structure contains the updated properties of a processor idle state.


## -struct-fields




### -field Version

The version number of this structure. Set this member to PEP_PROCESSOR_IDLE_STATE_UPDATE_VERSION.


### -field Latency

The worst-case latency, in 100-nanosecond units, that the platform requires to wake from this platform idle state in response to a wake event.


### -field BreakEvenDuration

The minimum amount of time, specified in 100-nanosecond units, that the platform must spend in this idle state to make a transition to this state worthwhile. PoFx uses this member value as a hint to avoid switching the platform to an idle state unless the platform is likely to remain in this state for at least the amount of time specified by <b>BreakEvenDuration</b>.


## -remarks



The <i>Update</i> parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186887">UpdateProcessorIdleState</a> routine is a pointer to a <b>PEP_PROCESSOR_IDLE_STATE_UPDATE</b> structure. This routine updates the properties of the specified idle state for a processor. The PEP must not call this routine until it has responded to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification for this processor.




## -see-also




<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186887">UpdateProcessorIdleState</a>
 

 

