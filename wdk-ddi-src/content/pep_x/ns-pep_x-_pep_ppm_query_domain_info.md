---
UID: NS:pep_x._PEP_PPM_QUERY_DOMAIN_INFO
title: "_PEP_PPM_QUERY_DOMAIN_INFO"
author: windows-driver-content
description: Used in the PEP_NOTIFY_PPM_QUERY_DOMAIN_INFO notification that queries for information about a performance domain. .
old-location: kernel\pep_ppm_query_domain_info.htm
old-project: kernel
ms.assetid: c608dac0-bb2a-4d89-a2f8-1017254c8a6c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.pep_ppm_query_domain_info, pepfx/PEP_PPM_QUERY_DOMAIN_INFO, _PEP_PPM_QUERY_DOMAIN_INFO, PEP_PPM_QUERY_DOMAIN_INFO, PEP_PPM_QUERY_DOMAIN_INFO structure [Kernel-Mode Driver Architecture], *PPEP_PPM_QUERY_DOMAIN_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Pepfx.h
apiname:
-	PEP_PPM_QUERY_DOMAIN_INFO
product: Windows
targetos: Windows
req.typenames: "*PPEP_PPM_QUERY_DOMAIN_INFO, PEP_PPM_QUERY_DOMAIN_INFO"
---

# _PEP_PPM_QUERY_DOMAIN_INFO structure


## -description


Used in the <b>PEP_NOTIFY_PPM_QUERY_DOMAIN_INFO</b> notification that queries for information about a performance domain. 


## -syntax


````
typedef struct _PEP_PPM_QUERY_DOMAIN_INFO {
  ULONG    DomainId;
  UCHAR    CoordinationType;
  BOOLEAN  IdleProcessorsDiscounted;
  BOOLEAN  SchedulerDirectedTransitionsSupported;
  ULONG    WorstCaseTransitionLatency;
  ULONG    WorstCaseTransitionOverhead;
} PEP_PPM_QUERY_DOMAIN_INFO, PEP_PPM_QUERY_DOMAIN_INFO;
````


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


### -field WorstCaseTransitionLatency

On output, this value indicates the worst case latency for the processor to transition to a new performance state, measured from the time the OS issues the notification to the PEP to transition to a new performance level, to the time the processor is running at the new performance level, in 100ns units. 


### -field WorstCaseTransitionOverhead

On output, this value indicates the worst case overhead (PEP code execution time plus time the processor is not executing instructions) measured from the time the OS issues the notification to the PEP to transition to a new performance level, to the time the processor is running at the new performance level, in 100ns units. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186881">Processor power management (PPM) notifications</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_QUERY_DOMAIN_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

