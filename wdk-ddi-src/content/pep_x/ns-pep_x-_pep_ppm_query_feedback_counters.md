---
UID: NS:pep_x._PEP_PPM_QUERY_FEEDBACK_COUNTERS
title: "_PEP_PPM_QUERY_FEEDBACK_COUNTERS"
author: windows-driver-content
description: The PEP_PPM_QUERY_FEEDBACK_COUNTERS structure describes all the processor performance counters that the platform extension plug-in (PEP) supports for a particular processor.
old-location: kernel\pep_ppm_query_feedback_counters.htm
old-project: kernel
ms.assetid: A27D34CC-A702-4944-84B7-FF9AF6BA030B
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PPEP_PPM_QUERY_FEEDBACK_COUNTERS, PEP_PPM_QUERY_FEEDBACK_COUNTERS, PEP_PPM_QUERY_FEEDBACK_COUNTERS structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_FEEDBACK_COUNTERS, PPEP_PPM_QUERY_FEEDBACK_COUNTERS structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_FEEDBACK_COUNTERS, kernel.pep_ppm_query_feedback_counters, pepfx/PEP_PPM_QUERY_FEEDBACK_COUNTERS, pepfx/PPEP_PPM_QUERY_FEEDBACK_COUNTERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pep_x.h, Pep_x.h
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
-	PEP_PPM_QUERY_FEEDBACK_COUNTERS
product: Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_FEEDBACK_COUNTERS, *PPEP_PPM_QUERY_FEEDBACK_COUNTERS
---

# _PEP_PPM_QUERY_FEEDBACK_COUNTERS structure


## -description


The <b>PEP_PPM_QUERY_FEEDBACK_COUNTERS</b> structure describes all the processor performance counters that the platform extension plug-in (PEP) supports for a particular processor.


## -struct-fields




### -field Count

[in] The number of processor performance feedback counters supported by the PEP. The PEP previously supplied this count in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186820">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a> notification.


### -field Counters

[out] The first element in an array of <a href="https://msdn.microsoft.com/library/windows/hardware/mt186833">PEP_PROCESSOR_FEEDBACK_COUNTER</a> structures. If this array contains more than one element, the additional elements immediately follow the end of the <b>PEP_PPM_QUERY_FEEDBACK_COUNTERS</b> structure. The <b>Count</b> member specifies the number of elements in this array. For more information, see Remarks.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186823">PEP_NOTIFY_PPM_QUERY_FEEDBACK_COUNTERS</a> notification. The <b>Count</b> member of the structure contains an input value that PoFx supplies when this notification is sent. The <b>Counters</b> member contains an output value that the PEP writes in response to the notification. The PEP writes any additional <b>Counters</b> array elements to the output buffer area that follows the <b>PEP_PPM_QUERY_FEEDBACK_COUNTERS</b> structure. The buffer that PoFx allocated for this structure is guaranteed to be large enough to contain any array elements that follow the structure.




## -see-also




<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186823">PEP_NOTIFY_PPM_QUERY_FEEDBACK_COUNTERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186833">PEP_PROCESSOR_FEEDBACK_COUNTER</a>
 

 

