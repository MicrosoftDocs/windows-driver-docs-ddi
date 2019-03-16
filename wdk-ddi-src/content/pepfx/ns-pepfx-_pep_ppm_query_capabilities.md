---
UID: NS:pepfx._PEP_PPM_QUERY_CAPABILITIES
title: _PEP_PPM_QUERY_CAPABILITIES (pepfx.h)
description: The PEP_PPM_QUERY_CAPABILITIES structure contains information about the processor power management (PPM) capabilities of the platform extension plug-in (PEP).
old-location: kernel\pep_ppm_query_capabilities.htm
tech.root: kernel
ms.assetid: D33FA62B-9DC8-4AC4-85FC-726C39FB76F4
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_QUERY_CAPABILITIES, PEP_PPM_QUERY_CAPABILITIES, PEP_PPM_QUERY_CAPABILITIES structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_CAPABILITIES, PPEP_PPM_QUERY_CAPABILITIES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_CAPABILITIES, kernel.pep_ppm_query_capabilities, pepfx/PEP_PPM_QUERY_CAPABILITIES, pepfx/PPEP_PPM_QUERY_CAPABILITIES"
ms.topic: struct
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
- PEP_PPM_QUERY_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_CAPABILITIES, *PPEP_PPM_QUERY_CAPABILITIES
---

# _PEP_PPM_QUERY_CAPABILITIES structure


## -description


The <b>PEP_PPM_QUERY_CAPABILITIES</b> structure contains information about the processor power management (PPM) capabilities of the platform extension plug-in (PEP).


## -struct-fields




### -field FeedbackCounterCount

[out] The number of processor performance feedback counters supported by the PEP for this processor. On x86/AMD64 platforms, this must be zero.


### -field IdleStateCount

[out] The number of processor idle states that the PEP supports. The PEP is not required to support the same number of idle states for all processors. The PEP can set <b>IdleStateCount</b> = 0 to indicate that it doesn't support any idle states, in which case the PEP doesn't need to implement any other notifications that deal with processor idle states.


### -field PerformanceStatesSupported

[out] Whether the PEP supports performance state controls. Set to TRUE if the PEP supports performance states, or to FALSE if it does not.


### -field ParkingSupported

[out] Whether the PEP supports supplying core parking hints. Set to TRUE if the PEP can indicate which cores to park, or to FALSE if it cannot.


### -field DiscretePerformanceStateCount

 




## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186820">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a> notification. All four members contain output values that the PEP writes to the structure in response to this notification.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186820">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a>
 

 

