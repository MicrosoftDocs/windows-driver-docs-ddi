---
UID: NS:pepfx._PEP_PPM_PERF_SET_STATE
title: _PEP_PPM_PERF_SET_STATE (pepfx.h)
description: Used in the PEP_NOTIFY_PPM_PERF_SET notification at runtime to set the current operating performance of the processor.  .
old-location: kernel\pep_ppm_perf_set_state.htm
tech.root: kernel
ms.date: 08/10/2022
keywords: ["PEP_PPM_PERF_SET_STATE structure"]
ms.keywords: "*PPEP_PPM_PERF_SET_STATE, PEP_PPM_PERF_SET_STATE, PEP_PPM_PERF_SET_STATE structure [Kernel-Mode Driver Architecture], PPEP_PPM_PERF_SET_STATE, PPEP_PPM_PERF_SET_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_PERF_SET_STATE, kernel.pep_ppm_perf_set_state, pepfx/PEP_PPM_PERF_SET_STATE, pepfx/PPEP_PPM_PERF_SET_STATE"
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
targetos: Windows
req.typenames: PEP_PPM_PERF_SET_STATE, *PPEP_PPM_PERF_SET_STATE
f1_keywords:
 - _PEP_PPM_PERF_SET_STATE
 - pepfx/_PEP_PPM_PERF_SET_STATE
 - PPEP_PPM_PERF_SET_STATE
 - pepfx/PPEP_PPM_PERF_SET_STATE
 - PEP_PPM_PERF_SET_STATE
 - pepfx/PEP_PPM_PERF_SET_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pepfx.h
api_name:
 - _PEP_PPM_PERF_SET_STATE
 - PPEP_PPM_PERF_SET_STATE
 - PEP_PPM_PERF_SET_STATE
---

# _PEP_PPM_PERF_SET_STATE structure (pepfx.h)

## -description

Used in the **PEP_NOTIFY_PPM_PERF_SET** notification at runtime to set the current operating performance of the processor.

## -struct-fields

### -field MinimumPerformanceState

On input, the new requested minimum performance state. This state is  defined as the absolute minimum instantaneous performance level at which  the processor may run. The operating system may set this value to any performance value in the range [Lowest Performance, Guaranteed Performance], inclusive. Minimum performance must never be set to a value higher than maximum performance.

### -field MaximumPerformanceState

On input, the new requested maximum performance state. This state is defined as the absolute maximum instantaneous performance level at which the processor may run. The OS may set Maximum performance to any performance value in the range [Lowest Performance, Highest Performance], inclusive.

### -field DesiredPerformanceState

On input, the new requested desired performance state. This state is defined as the performance level power manager is requesting from the processor. Desired performance may be set to any performance value in the range [Minimum Performance, Maximum Performance], inclusive. Desired performance may take one of two meanings, depending on whether the desired performance is above or below the guaranteed performance level.

- Below the guaranteed performance level, desired performance expresses the average performance level the platform must provide.  
- Above the guaranteed performance level, the platform must provide the guaranteed performance level. The platform should attempt to provide up to the desired performance level, if current operating conditions allow for it, but it is not required to do so.

### -field EnergyPerformancePreference

On input, the new requested energy performance preference for the processor.

## -see-also

- [Processor power management (PPM) notifications](../index.yml)