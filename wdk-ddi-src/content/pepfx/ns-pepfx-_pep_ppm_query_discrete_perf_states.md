---
UID: NS:pepfx._PEP_PPM_QUERY_DISCRETE_PERF_STATES
title: "_PEP_PPM_QUERY_DISCRETE_PERF_STATES"
author: windows-driver-content
description: Used in the PEP_NOTIFY_PPM_QUERY_DISCRETE_PERF_STATES notification that stores the list of discrete performance states that PEP supports, if the PEP_NOTIFY_PPM_QUERY_CAPABILITIES notification indicates support for discrete performance states. .
old-location: kernel\pep_ppm_query_discrete_perf_states.htm
old-project: kernel
ms.assetid: 506b3d8e-4aba-4e70-a6db-52a52d717c6b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PPEP_PPM_QUERY_DISCRETE_PERF_STATES structure pointer [Kernel-Mode Driver Architecture], *PPEP_PPM_QUERY_DISCRETE_PERF_STATES, PPEP_PPM_QUERY_DISCRETE_PERF_STATES, PEP_PPM_QUERY_DISCRETE_PERF_STATES structure [Kernel-Mode Driver Architecture], PEP_PPM_QUERY_DISCRETE_PERF_STATES, pepfx/PEP_PPM_QUERY_DISCRETE_PERF_STATES, kernel.pep_ppm_query_discrete_perf_states, pepfx/PPEP_PPM_QUERY_DISCRETE_PERF_STATES, _PEP_PPM_QUERY_DISCRETE_PERF_STATES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
-	Pepfx.h
apiname:
-	PEP_PPM_QUERY_DISCRETE_PERF_STATES
product: Windows
targetos: Windows
req.typenames: "*PPEP_PPM_QUERY_DISCRETE_PERF_STATES, PEP_PPM_QUERY_DISCRETE_PERF_STATES"
---

# _PEP_PPM_QUERY_DISCRETE_PERF_STATES structure


## -description


Used in the <b>PEP_NOTIFY_PPM_QUERY_DISCRETE_PERF_STATES</b> notification that stores the list of discrete performance states that PEP supports, if the <b>PEP_NOTIFY_PPM_QUERY_CAPABILITIES</b> notification indicates support for discrete performance states. 


## -syntax


````
typedef struct _PEP_PPM_QUERY_DISCRETE_PERF_STATES {
  ULONG                      Count;
  PPEP_PROCESSOR_PERF_STATE  States;
} PEP_PPM_QUERY_DISCRETE_PERF_STATES, *PPEP_PPM_QUERY_DISCRETE_PERF_STATES;
````


## -struct-fields




### -field Count

On input, the size of the array pointed to by <i>States</i>. 


### -field States

On output, an array of <a href="https://msdn.microsoft.com/46231ac0-2c34-4154-8b3e-f34c40cbff4a">PEP_PROCESSOR_PERF_STATE</a> structures that indicates performance states that is filled by  PEP. 


## -see-also

<a href="..\pepfx\ns-pepfx-_pep_ppm_query_capabilities.md">PEP_PPM_QUERY_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186881">Processor power management (PPM) notifications</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_QUERY_DISCRETE_PERF_STATES structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

