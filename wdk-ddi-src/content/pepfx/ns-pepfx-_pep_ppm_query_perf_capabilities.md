---
UID: NS:pepfx._PEP_PPM_QUERY_PERF_CAPABILITIES
title: "_PEP_PPM_QUERY_PERF_CAPABILITIES"
author: windows-driver-content
description: The PEP_PPM_QUERY_PERF_CAPABILITIES structure describes the performance capabilities of the processors in the specified processor performance domain.
old-location: kernel\pep_ppm_query_perf_capabilities.htm
tech.root: kernel
ms.assetid: 562EA523-A74D-4D46-8C01-12C745106F86
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_QUERY_PERF_CAPABILITIES, PEP_PPM_QUERY_PERF_CAPABILITIES, PEP_PPM_QUERY_PERF_CAPABILITIES structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_PERF_CAPABILITIES, PPEP_PPM_QUERY_PERF_CAPABILITIES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_PERF_CAPABILITIES, kernel.pep_ppm_query_perf_capabilities, pepfx/PEP_PPM_QUERY_PERF_CAPABILITIES, pepfx/PPEP_PPM_QUERY_PERF_CAPABILITIES"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PPM_QUERY_PERF_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_PERF_CAPABILITIES, *PPEP_PPM_QUERY_PERF_CAPABILITIES
---

# _PEP_PPM_QUERY_PERF_CAPABILITIES structure


## -description


The <b>PEP_PPM_QUERY_PERF_CAPABILITIES</b> structure describes the performance capabilities of the processors in the specified processor performance domain.


## -struct-fields




### -field HighestPerformance

[out] The highest performance level in platform-specific units. For more information, see Remarks.


### -field NominalPerformance

[out] The nominal performance level in platform-specific units. For more information, see Remarks.


### -field LowestNonlinearPerformance

[out] The lowest nonlinear performance level in platform-specific units. For more information, see Remarks.


### -field LowestPerformance

[out] The lowest performance level in platform-specific units. For more information, see Remarks.


### -field DomainId

[out] The domain ID of the processor performance domain.


### -field DomainMembers

[out] The number of processors in this performance domain.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186825">PEP_NOTIFY_PPM_QUERY_PERF_CAPABILITIES</a> notification. All six members contain output values that the platform extension plug-in (PEP) writes to the structure in response to this notification.

Processor performance levels are specified in platform-specific units. For example, a hardware platform might use a metric such as the processor clock frequency to provide a rough approximation to the amount of processing work that is being done. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt629132">Platform Performance Thresholds</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186825">PEP_NOTIFY_PPM_QUERY_PERF_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629132">Platform Performance Thresholds</a>
 

 

