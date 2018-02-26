---
UID: NS:pep_x._PEP_PPM_QUERY_FEEDBACK_COUNTERS
title: "_PEP_PPM_QUERY_FEEDBACK_COUNTERS"
author: windows-driver-content
description: The PEP_PPM_QUERY_FEEDBACK_COUNTERS structure describes all the processor performance counters that the platform extension plug-in (PEP) supports for a particular processor.
old-location: kernel\pep_ppm_query_feedback_counters.htm
old-project: kernel
ms.assetid: A27D34CC-A702-4944-84B7-FF9AF6BA030B
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PPEP_PPM_LPI_COMPLETE, *PPEP_PPM_QUERY_FEEDBACK_COUNTERS, ,, A, B, C, D, E, F, K, M, N, O, P, PEP_PPM_LPI_COMPLETE, PEP_PPM_QUERY_FEEDBACK_COUNTERS, PEP_PPM_QUERY_FEEDBACK_COUNTERS structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_FEEDBACK_COUNTERS, PPEP_PPM_QUERY_FEEDBACK_COUNTERS structure pointer [Kernel-Mode Driver Architecture], Q, R, S, T, U, Y, _, _PEP_PPM_LPI_COMPLETE, _PEP_PPM_QUERY_FEEDBACK_COUNTERS, kernel.pep_ppm_query_feedback_counters, pepfx/PEP_PPM_QUERY_FEEDBACK_COUNTERS, pepfx/PPEP_PPM_QUERY_FEEDBACK_COUNTERS"
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_PPM_QUERY_FEEDBACK_COUNTERS
product: Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_FEEDBACK_COUNTERS, *PPEP_PPM_QUERY_FEEDBACK_COUNTERS, PEP_PPM_QUERY_FEEDBACK_COUNTERS, *PPEP_PPM_QUERY_FEEDBACK_COUNTERS
---

# _PEP_PPM_QUERY_FEEDBACK_COUNTERS structure


## -description


The <b>PEP_PPM_QUERY_FEEDBACK_COUNTERS</b> structure describes all the processor performance counters that the platform extension plug-in (PEP) supports for a particular processor.


## -syntax


````
typedef struct _PEP_PPM_QUERY_FEEDBACK_COUNTERS {
  ULONG                          Count;
  PEP_PROCESSOR_FEEDBACK_COUNTER Counters[ANYSIZE_ARRAY];
} PEP_PPM_QUERY_FEEDBACK_COUNTERS, *PPEP_PPM_QUERY_FEEDBACK_COUNTERS;
````


## -struct-fields




#### - Count

[in] The number of processor performance feedback counters supported by the PEP. The PEP previously supplied this count in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186820">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a> notification.


#### - Counters

[out] The first element in an array of <a href="..\pep_x\ns-pep_x-_pep_processor_feedback_counter.md">PEP_PROCESSOR_FEEDBACK_COUNTER</a> structures. If this array contains more than one element, the additional elements immediately follow the end of the <b>PEP_PPM_QUERY_FEEDBACK_COUNTERS</b> structure. The <b>Count</b> member specifies the number of elements in this array. For more information, see Remarks.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186823">PEP_NOTIFY_PPM_QUERY_FEEDBACK_COUNTERS</a> notification. The <b>Count</b> member of the structure contains an input value that PoFx supplies when this notification is sent. The <b>Counters</b> member contains an output value that the PEP writes in response to the notification. The PEP writes any additional <b>Counters</b> array elements to the output buffer area that follows the <b>PEP_PPM_QUERY_FEEDBACK_COUNTERS</b> structure. The buffer that PoFx allocated for this structure is guaranteed to be large enough to contain any array elements that follow the structure.




## -see-also

<a href="..\pep_x\ns-pep_x-_pep_processor_feedback_counter.md">PEP_PROCESSOR_FEEDBACK_COUNTER</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186823">PEP_NOTIFY_PPM_QUERY_FEEDBACK_COUNTERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_QUERY_FEEDBACK_COUNTERS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

