---
UID: NS:pepfx._PEP_PPM_QUERY_DOMAIN_INFO
title: _PEP_PPM_QUERY_DOMAIN_INFO (pepfx.h)
description: Used in the PEP_NOTIFY_PPM_QUERY_DOMAIN_INFO notification that queries for information about a performance domain. .
old-location: kernel\pep_ppm_query_domain_info.htm
tech.root: kernel
ms.assetid: c608dac0-bb2a-4d89-a2f8-1017254c8a6c
ms.date: 04/30/2018
keywords: ["PEP_PPM_QUERY_DOMAIN_INFO structure"]
ms.keywords: "*PPEP_PPM_QUERY_DOMAIN_INFO, PEP_PPM_QUERY_DOMAIN_INFO, PEP_PPM_QUERY_DOMAIN_INFO structure [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_DOMAIN_INFO, kernel.pep_ppm_query_domain_info, pepfx/PEP_PPM_QUERY_DOMAIN_INFO"
f1_keywords:
 - "pepfx/PEP_PPM_QUERY_DOMAIN_INFO"
 - "PEP_PPM_QUERY_DOMAIN_INFO"
req.header: pepfx.h
req.include-header: Pep_x.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Pepfx.h
api_name:
- PEP_PPM_QUERY_DOMAIN_INFO
targetos: Windows
req.typenames: PEP_PPM_QUERY_DOMAIN_INFO, *PPEP_PPM_QUERY_DOMAIN_INFO
---

# _PEP_PPM_QUERY_DOMAIN_INFO structure


## -description


Used in the <b>PEP_NOTIFY_PPM_QUERY_DOMAIN_INFO</b> notification that queries for information about a performance domain. 


## -struct-fields




### -field DomainId

On input, the domain ID of the domain being queried.


### -field CoordinationType

On output, indicates the coordination type of the performance domain. The possible values are:

<ul>
<li>PROCESSOR_DOMAIN_COORDIANTION_SW_ALL (0x00)</li>
<li>PROCESSOR_DOMAIN_COORDIANTION_SW_ANY (0x01)</li>
<li>PROCESSOR_DOMAIN_COORDIANTION_HW_ALL (0x02)</li>
</ul>
If this notification is not supported, PROCESSOR_DOMAIN_COORDIANTION_SW_ALL coordination is used. 


### -field IdleProcessorsDiscounted

On output, and if HW-ALL coordination is used, this value is  TRUE if the platform automatically ignores requests from idle processors as it determines the resolved performance level of the domain, FALSE if requests from idle processors continue to be honored.  
If PROCESSOR_DOMAIN_COORDIANTION_HW_ALL coordination is not used: this field is ignored. 


### -field SchedulerDirectedTransitionsSupported

On output, this value is TRUE if the PEP supports the requirements of scheduler directed performance transitions for this domain, FALSE otherwise. 

### -field AffinitizePerfSet

On output, this value is TRUE if the PEP requires the PEP_NOTIFY_PPM_PERF_SET or PEP_NOTIFY_PPM_PERF_SET_STATE notification to execute on the processor changing frequency, or FALSE if the PEP allows these notifications to execute on any processor.
If PROCESSOR_DOMAIN_COORDIANTION_SW_ANY coordination is used: the PEP_NOTIFY_PPM_PERF_SET or PEP_NOTIFY_PPM_PERF_SET_STATE notification will execute on a processor in the domain.


### -field WorstCaseTransitionLatency

On output, this value indicates the worst case latency for the processor to transition to a new performance state, measured from the time the OS issues the notification to the PEP to transition to a new performance level, to the time the processor is running at the new performance level, in 100ns units. 


### -field WorstCaseTransitionOverhead

On output, this value indicates the worst case overhead (PEP code execution time plus time the processor is not executing instructions) measured from the time the OS issues the notification to the PEP to transition to a new performance level, to the time the processor is running at the new performance level, in 100ns units. 


## -see-also




[Processor power management (PPM) notifications](https://docs.microsoft.com/windows-hardware/drivers/kernel/ppm-notifications)
 

 

