---
UID: NS:pep_x._PEP_PPM_QUERY_IDLE_STATES_V2
title: "_PEP_PPM_QUERY_IDLE_STATES_V2"
author: windows-driver-content
description: The PEP_PPM_QUERY_IDLE_STATES_V2 structure is used during processor initialization to query the platform extension plug-in (PEP) for a list of processor idle states that the processor supports.
old-location: kernel\pep_ppm_query_idle_states_v2.htm
old-project: kernel
ms.assetid: 0C225F3B-0D09-48FD-9BD3-F17D5E602698
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_PPM_QUERY_IDLE_STATES_V2, PEP_PPM_QUERY_IDLE_STATES_V2, PEP_PPM_QUERY_IDLE_STATES_V2 structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_IDLE_STATES_V2, PPEP_PPM_QUERY_IDLE_STATES_V2 structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_IDLE_STATES_V2, kernel.pep_ppm_query_idle_states_v2, pepfx/PEP_PPM_QUERY_IDLE_STATES_V2, pepfx/PPEP_PPM_QUERY_IDLE_STATES_V2"
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
-	PEP_PPM_QUERY_IDLE_STATES_V2
product: Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_IDLE_STATES_V2, *PPEP_PPM_QUERY_IDLE_STATES_V2, PEP_PPM_QUERY_IDLE_STATES_V2, *PPEP_PPM_QUERY_IDLE_STATES_V2
---

# _PEP_PPM_QUERY_IDLE_STATES_V2 structure


## -description


The <b>PEP_PPM_QUERY_IDLE_STATES_V2</b> structure is used during processor initialization to query the platform extension plug-in (PEP) for a list of processor idle states that the processor supports.


## -struct-fields




### -field Count

[in] The number of elements in the <b>IdleStates</b> array. The Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) previously sent the PEP a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186820">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a> notification to determine this number.


### -field IdleStates

[out] The first element in an array of <a href="https://msdn.microsoft.com/library/windows/hardware/mt186836">PEP_PROCESSOR_IDLE_STATE_V2</a> structures that describe the processor idle states. If this array contains more than one element, the addition array elements follow the end of the <b>PEP_PPM_QUERY_IDLE_STATES_V2</b> structure.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification. The <b>Count</b> member of the <b>PEP_PPM_QUERY_IDLE_STATES_V2</b> structure contains an input value that is supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The <b>IdleStates</b> array elements contain output values that the PEP writes to the structure in response to this notification.




## -see-also




<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186820">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186836">PEP_PROCESSOR_IDLE_STATE_V2</a>
 

 

