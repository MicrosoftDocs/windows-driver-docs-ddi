---
UID: NS:pep_x._PEP_PPM_LPI_COMPLETE
title: _PEP_PPM_LPI_COMPLETE (pep_x.h)
description: The PEP_PPM_LPI_COMPLETE structure (pep_x.h) describes the processor performance counters that the platform extension plug-in (PEP) supports for a particular processor.
old-location: kernel\pep_ppm_query_feedback_counters.htm
tech.root: kernel
ms.date: 08/01/2025
keywords: ["PEP_PPM_LPI_COMPLETE structure"]
ms.keywords: "*PPEP_PPM_LPI_COMPLETE, *PPEP_PPM_QUERY_FEEDBACK_COUNTERS, PEP_PPM_LPI_COMPLETE, PEP_PPM_QUERY_FEEDBACK_COUNTERS, PEP_PPM_QUERY_FEEDBACK_COUNTERS structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_FEEDBACK_COUNTERS, PPEP_PPM_QUERY_FEEDBACK_COUNTERS structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_LPI_COMPLETE, kernel.pep_ppm_query_feedback_counters, pepfx/PEP_PPM_QUERY_FEEDBACK_COUNTERS, pepfx/PPEP_PPM_QUERY_FEEDBACK_COUNTERS"
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
targetos: Windows
req.typenames: PEP_PPM_LPI_COMPLETE, *PPEP_PPM_LPI_COMPLETE, PEP_PPM_LPI_COMPLETE, *PPEP_PPM_LPI_COMPLETE, PEP_PPM_QUERY_FEEDBACK_COUNTERS, *PPEP_PPM_QUERY_FEEDBACK_COUNTERS
f1_keywords:
 - _PEP_PPM_LPI_COMPLETE
 - pep_x/_PEP_PPM_LPI_COMPLETE
 - PPEP_PPM_LPI_COMPLETE
 - pep_x/PPEP_PPM_LPI_COMPLETE
 - PEP_PPM_LPI_COMPLETE
 - pep_x/PEP_PPM_LPI_COMPLETE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_PPM_LPI_COMPLETE
 - PPEP_PPM_LPI_COMPLETE
 - PEP_PPM_LPI_COMPLETE
---

# _PEP_PPM_LPI_COMPLETE structure

## -description

The **PEP_PPM_LPI_COMPLETE** structure describes the processor performance counters that the platform extension plug-in (PEP) supports for a particular processor.

## -struct-fields

### -field CoordinatedStateCount

The number of coordinated idle states being exited by this transition.

### -field CoordinatedStates

Pointer to an array of coordinated idle states that are being exited by this transition.

## -remarks

This structure is used by the **PEP_NOTIFY_PPM_LPI_COMPLETE** notification. The notification is sent to the PEP to notify it that current processor is waking up from a completed platform idle transition. The first processor to wake indicates the platform idle states being exited. The first processor to wake from a platform idle state may not be the processor that entered the platform idle state.

This notification is only sent when using the ACPI LPI interface. Windows doesn't inform the PEP of processor idle state transitions or coordinated idle transitions except those listed below:

Windows 10, version 1703: This notification is only sent when a platform idle state associated with the root processor container (if one exists) is exited, and only includes the platform idle state associated with the root processor container.

Windows 10, version 1709: This notification is sent for all platform idle states. For example, all coordinated idle states associated with a processor container which directly or indirectly contains all processors in the system.

This notification is sent with interrupts disabled. This notification is always executed on the target processor.

## -see-also

- [PEP_NOTIFY_PPM_QUERY_FEEDBACK_COUNTERS](../pepfx/ns-pepfx-_pep_ppm_query_feedback_counters.md)
- [PEP_PROCESSOR_FEEDBACK_COUNTER](../pepfx/ns-pepfx-_pep_processor_feedback_counter.md)
