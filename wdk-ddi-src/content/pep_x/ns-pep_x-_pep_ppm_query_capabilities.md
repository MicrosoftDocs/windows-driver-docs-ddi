---
UID: NS:pep_x._PEP_PPM_QUERY_CAPABILITIES
title: _PEP_PPM_QUERY_CAPABILITIES (pep_x.h)
description: Learn how the PEP_PPM_QUERY_CAPABILITIES structure contains information about the processor power management (PPM) capabilities of the platform extension plug-in (PEP).
old-location: kernel\pep_ppm_query_capabilities.htm
tech.root: kernel
ms.date: 08/10/2022
keywords: ["PEP_PPM_QUERY_CAPABILITIES structure"]
ms.keywords: "*PPEP_PPM_QUERY_CAPABILITIES, PEP_PPM_QUERY_CAPABILITIES, PEP_PPM_QUERY_CAPABILITIES structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_CAPABILITIES, PPEP_PPM_QUERY_CAPABILITIES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_CAPABILITIES, kernel.pep_ppm_query_capabilities, pepfx/PEP_PPM_QUERY_CAPABILITIES, pepfx/PPEP_PPM_QUERY_CAPABILITIES"
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
targetos: Windows
req.typenames: PEP_PPM_QUERY_CAPABILITIES, *PPEP_PPM_QUERY_CAPABILITIES
f1_keywords:
 - _PEP_PPM_QUERY_CAPABILITIES
 - pep_x/_PEP_PPM_QUERY_CAPABILITIES
 - PPEP_PPM_QUERY_CAPABILITIES
 - pep_x/PPEP_PPM_QUERY_CAPABILITIES
 - PEP_PPM_QUERY_CAPABILITIES
 - pep_x/PEP_PPM_QUERY_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_PPM_QUERY_CAPABILITIES
 - PPEP_PPM_QUERY_CAPABILITIES
 - PEP_PPM_QUERY_CAPABILITIES
---

# _PEP_PPM_QUERY_CAPABILITIES structure (pep_x.h)

## -description

The **PEP_PPM_QUERY_CAPABILITIES** structure contains information about the processor power management (PPM) capabilities of the platform extension plug-in (PEP).

## -struct-fields

### -field FeedbackCounterCount

The number of processor performance feedback counters supported by the PEP for this processor. On x86/AMD64 platforms, this must be zero.

### -field IdleStateCount

The number of processor idle states that the PEP supports. The PEP is not required to support the same number of idle states for all processors. The PEP can set `IdleStateCount = 0` to indicate that it doesn't support any idle states, in which case the PEP doesn't need to implement any other notifications that deal with processor idle states.

### -field PerformanceStatesSupported

Whether the PEP supports performance state controls. Set to TRUE if the PEP supports performance states, or to FALSE if it does not.

### -field ParkingSupported

Whether the PEP supports supplying core parking hints. Set to TRUE if the PEP can indicate which cores to park, or to FALSE if it cannot.

### -field DiscretePerformanceStateCount

The number of discrete performance states that the PEP supports.

### -field Reserved

Reserved for future use. Set to zero.

## -remarks

This structure is used by the [PEP_NOTIFY_PPM_QUERY_CAPABILITIES](../pepfx/ns-pepfx-_pep_ppm_query_capabilities.md) notification. All four members contain output values that the PEP writes to the structure in response to this notification.

## -see-also

- [PEP_NOTIFY_PPM_QUERY_CAPABILITIES](../pepfx/ns-pepfx-_pep_ppm_query_capabilities.md)
