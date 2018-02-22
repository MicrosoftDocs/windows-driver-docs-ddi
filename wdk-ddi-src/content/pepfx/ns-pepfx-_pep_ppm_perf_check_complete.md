---
UID: NS:pepfx._PEP_PPM_PERF_CHECK_COMPLETE
title: "_PEP_PPM_PERF_CHECK_COMPLETE"
author: windows-driver-content
description: The PEP_PPM_PERF_CHECK_COMPLETE structure is used to inform the PEP of details regarding the completion of a periodic performance check evaluation.
old-location: kernel\pep_ppm_perf_check_complete.htm
old-project: kernel
ms.assetid: A107F641-AE30-4F99-9AB6-EC84F52A2B52
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: pepfx/PEP_PPM_PERF_CHECK_COMPLETE, pepfx/PPEP_PPM_PERF_CHECK_COMPLETE, PEP_PPM_PERF_CHECK_COMPLETE structure [Kernel-Mode Driver Architecture], _PEP_PPM_PERF_CHECK_COMPLETE, kernel.pep_ppm_perf_check_complete, PPEP_PPM_PERF_CHECK_COMPLETE structure pointer [Kernel-Mode Driver Architecture], PEP_PPM_PERF_CHECK_COMPLETE, *PPEP_PPM_PERF_CHECK_COMPLETE, PPEP_PPM_PERF_CHECK_COMPLETE
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_PPM_PERF_CHECK_COMPLETE
product: Windows
targetos: Windows
req.typenames: PEP_PPM_PERF_CHECK_COMPLETE, *PPEP_PPM_PERF_CHECK_COMPLETE
---

# _PEP_PPM_PERF_CHECK_COMPLETE structure


## -description


The <b>PEP_PPM_PERF_CHECK_COMPLETE</b> structure is used to inform the PEP of details regarding the completion of a periodic performance check evaluation.


## -syntax


````
typedef struct _PEP_PPM_PERF_CHECK_COMPLETE {
  ULONGLONG EvaluationTime;
} PEP_PPM_PERF_CHECK_COMPLETE, *PPEP_PPM_PERF_CHECK_COMPLETE;
````


## -struct-fields




### -field EvaluationTime

[in] The interrupt time of the performance check evaluation that initiated this notification.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186771">PEP_NOTIFY_PPM_PERF_CHECK_COMPLETE notification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_PERF_CHECK_COMPLETE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

