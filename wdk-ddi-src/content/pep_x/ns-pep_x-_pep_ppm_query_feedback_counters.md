---
UID: NS:pep_x._PEP_PPM_QUERY_FEEDBACK_COUNTERS
title: _PEP_PPM_QUERY_FEEDBACK_COUNTERS (pep_x.h)
description: Learn how the PEP_PPM_QUERY_FEEDBACK_COUNTERS structure (pep_x.h) describes all the processor performance counters that the platform extension plug-in (PEP) supports for a particular processor.
old-location: kernel\pep_ppm_query_feedback_counters.htm
tech.root: kernel
ms.date: 07/30/2021
keywords: ["PEP_PPM_QUERY_FEEDBACK_COUNTERS structure"]
ms.keywords: "*PPEP_PPM_QUERY_FEEDBACK_COUNTERS, PEP_PPM_QUERY_FEEDBACK_COUNTERS, PEP_PPM_QUERY_FEEDBACK_COUNTERS structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_FEEDBACK_COUNTERS, PPEP_PPM_QUERY_FEEDBACK_COUNTERS structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_FEEDBACK_COUNTERS, kernel.pep_ppm_query_feedback_counters, pepfx/PEP_PPM_QUERY_FEEDBACK_COUNTERS, pepfx/PPEP_PPM_QUERY_FEEDBACK_COUNTERS"
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
targetos: Windows
req.typenames: PEP_PPM_QUERY_FEEDBACK_COUNTERS, *PPEP_PPM_QUERY_FEEDBACK_COUNTERS
f1_keywords:
 - _PEP_PPM_QUERY_FEEDBACK_COUNTERS
 - pep_x/_PEP_PPM_QUERY_FEEDBACK_COUNTERS
 - PPEP_PPM_QUERY_FEEDBACK_COUNTERS
 - pep_x/PPEP_PPM_QUERY_FEEDBACK_COUNTERS
 - PEP_PPM_QUERY_FEEDBACK_COUNTERS
 - pep_x/PEP_PPM_QUERY_FEEDBACK_COUNTERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_PPM_QUERY_FEEDBACK_COUNTERS
 - PPEP_PPM_QUERY_FEEDBACK_COUNTERS
 - PEP_PPM_QUERY_FEEDBACK_COUNTERS
---

# _PEP_PPM_QUERY_FEEDBACK_COUNTERS structure (pep_x.h)

## -description

The **PEP_PPM_QUERY_FEEDBACK_COUNTERS** structure describes all the processor performance counters that the platform extension plug-in (PEP) supports for a particular processor.

## -struct-fields

### -field Count

[in] The number of processor performance feedback counters supported by the PEP. The PEP previously supplied this count in response to a [PEP_NOTIFY_PPM_QUERY_CAPABILITIES](../pepfx/ns-pepfx-_pep_ppm_query_capabilities.md) notification.

### -field Counters

[out] The first element in an array of [PEP_PROCESSOR_FEEDBACK_COUNTER](../pepfx/ns-pepfx-_pep_processor_feedback_counter.md) structures. If this array contains more than one element, the additional elements immediately follow the end of the **PEP_PPM_QUERY_FEEDBACK_COUNTERS** structure. The **Count** member specifies the number of elements in this array. For more information, see Remarks.

## -remarks

This structure is used by the [PEP_NOTIFY_PPM_QUERY_FEEDBACK_COUNTERS](../pepfx/ns-pepfx-_pep_ppm_query_feedback_counters.md) notification. The **Count** member of the structure contains an input value that PoFx supplies when this notification is sent. The **Counters** member contains an output value that the PEP writes in response to the notification. The PEP writes any additional **Counters** array elements to the output buffer area that follows the **PEP_PPM_QUERY_FEEDBACK_COUNTERS** structure. The buffer that PoFx allocated for this structure is guaranteed to be large enough to contain any array elements that follow the structure.

## -see-also

[PEP_NOTIFY_PPM_QUERY_FEEDBACK_COUNTERS](../pepfx/ns-pepfx-_pep_ppm_query_feedback_counters.md)

[PEP_PROCESSOR_FEEDBACK_COUNTER](../pepfx/ns-pepfx-_pep_processor_feedback_counter.md)