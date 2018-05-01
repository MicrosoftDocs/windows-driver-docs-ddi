---
UID: NS:pep_x._PEP_PPM_PERF_SET
title: "_PEP_PPM_PERF_SET"
author: windows-driver-content
description: The PEP_PPM_PERF_SET structure specifies the new performance level that the operating system is requesting for the processor.
old-location: kernel\pep_ppm_perf_set.htm
old-project: kernel
ms.assetid: BA2495F6-09E8-4AF9-9489-E745B759F999
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: "*PPEP_PPM_PERF_SET, PEP_PPM_PERF_SET, PEP_PPM_PERF_SET structure [Kernel-Mode Driver Architecture], PPEP_PPM_PERF_SET, PPEP_PPM_PERF_SET structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_PERF_SET, kernel.pep_ppm_perf_set, pepfx/PEP_PPM_PERF_SET, pepfx/PPEP_PPM_PERF_SET"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PPM_PERF_SET
product: Windows
targetos: Windows
req.typenames: PEP_PPM_PERF_SET, *PPEP_PPM_PERF_SET
---

# _PEP_PPM_PERF_SET structure


## -description


The <b>PEP_PPM_PERF_SET</b> structure specifies the new performance level that the operating system is requesting for the processor.


## -struct-fields




### -field MinimumPerformance

[in] The new minimum performance level in platform-specific units. This member indicates the absolute minimum performance level that the processor can run at.


### -field MaximumPerformance

[in] The new maximum performance level in platform-specific units. This member indicates the absolute maximum performance level that the processor can run at.


### -field DesiredPerformance

[in] The new desired performance level in platform-specific units. This member is set to a value in the range <b>MinimumPerformance</b> to <b>MaximumPerformance</b>.


### -field TimeWindow

[in] The width, in milliseconds, of the new time window over which the platform must provide the required average performance. If this time window is nonzero, the instantaneous performance provided by the platform does not need to match the desired performance level, and only needs to fall within the constraints specified by the minimum and maximum performance level.


### -field PerformanceTolerance

[in] The new performance tolerance in platform-specific units. This member contains the minimum performance level that the platform can deliver and still meet the operating system's performance requirements.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186816">PEP_NOTIFY_PPM_PERF_SET</a> notification. All five members of this structure contain input values that PoFx supplies when this notification is sent to the PEP.

Processor performance levels are specified in platform-specific units. For example, a hardware platform might use a metric such as the processor clock frequency to provide a rough approximation to the amount of processing work  that is being done. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt629132">Platform Performance Thresholds</a>.




## -see-also




<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186816">PEP_NOTIFY_PPM_PERF_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629132">Platform Performance Thresholds</a>
 

 

