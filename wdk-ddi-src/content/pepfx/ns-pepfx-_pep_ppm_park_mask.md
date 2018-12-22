---
UID: NS:pepfx._PEP_PPM_PARK_MASK
title: "_PEP_PPM_PARK_MASK"
description: The PEP_PROCESSOR_PARK_MASK structure contains the current core parking mask.
old-location: kernel\pep_ppm_park_mask.htm
tech.root: kernel
ms.assetid: 528576FD-BDB2-4772-9151-A1C855BA953E
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_PARK_MASK, PEP_PPM_PARK_MASK, PEP_PPM_PARK_MASK structure [Kernel-Mode Driver Architecture], PPEP_PPM_PARK_MASK, PPEP_PPM_PARK_MASK structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_PARK_MASK, kernel.pep_ppm_park_mask, pepfx/PEP_PPM_PARK_MASK, pepfx/PPEP_PPM_PARK_MASK"
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
-	PEP_PPM_PARK_MASK
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_PARK_MASK, *PPEP_PPM_PARK_MASK
---

# _PEP_PPM_PARK_MASK structure


## -description


The <b>PEP_PROCESSOR_PARK_MASK</b> structure contains the current core parking mask.


## -struct-fields




### -field Count

[in] Indicates the number of processors in the <b>Processors</b> array. 


### -field EvaluationTime

[in] The interrupt time of the performance check evaluation that initiated this notification. 


### -field Processors

[in/out] An array of processors in the core parking domain. 



#### On input

Indicates the OS parking preference for each processor.



#### On output

Returns the PEP parking preference for each processor.

The Processors array is guaranteed to contain the processors in increasing order by processor index.



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186768">PEP_NOTIFY_PPM_PARK_MASK notification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186838">PEP_PROCESSOR_PARK_STATE</a>
 

 

