---
UID: NS:pep_x._PEP_PPM_PERF_CHECK_COMPLETE
title: "_PEP_PPM_PERF_CHECK_COMPLETE"
description: The PEP_PPM_PERF_CHECK_COMPLETE structure is used to inform the PEP of details regarding the completion of a periodic performance check evaluation.
old-location: kernel\pep_ppm_perf_check_complete.htm
tech.root: kernel
ms.assetid: A107F641-AE30-4F99-9AB6-EC84F52A2B52
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_PERF_CHECK_COMPLETE, PEP_PPM_PERF_CHECK_COMPLETE, PEP_PPM_PERF_CHECK_COMPLETE structure [Kernel-Mode Driver Architecture], PPEP_PPM_PERF_CHECK_COMPLETE, PPEP_PPM_PERF_CHECK_COMPLETE structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_PERF_CHECK_COMPLETE, kernel.pep_ppm_perf_check_complete, pepfx/PEP_PPM_PERF_CHECK_COMPLETE, pepfx/PPEP_PPM_PERF_CHECK_COMPLETE"
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
-	PEP_PPM_PERF_CHECK_COMPLETE
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_PERF_CHECK_COMPLETE, *PPEP_PPM_PERF_CHECK_COMPLETE
---

# _PEP_PPM_PERF_CHECK_COMPLETE structure


## -description


The <b>PEP_PPM_PERF_CHECK_COMPLETE</b> structure is used to inform the PEP of details regarding the completion of a periodic performance check evaluation.


## -struct-fields




### -field EvaluationTime

[in] The interrupt time of the performance check evaluation that initiated this notification.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186771">PEP_NOTIFY_PPM_PERF_CHECK_COMPLETE notification</a>
 

 

