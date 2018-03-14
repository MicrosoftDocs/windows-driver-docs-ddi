---
UID: NS:pep_x._PEP_PPM_PARK_MASK
title: "_PEP_PPM_PARK_MASK"
author: windows-driver-content
description: The PEP_PROCESSOR_PARK_MASK structure contains the current core parking mask.
old-location: kernel\pep_ppm_park_mask.htm
old-project: kernel
ms.assetid: 528576FD-BDB2-4772-9151-A1C855BA953E
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_PPM_PARK_MASK, PEP_PPM_PARK_MASK, PEP_PPM_PARK_MASK structure [Kernel-Mode Driver Architecture], PPEP_PPM_PARK_MASK, PPEP_PPM_PARK_MASK structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_PARK_MASK, kernel.pep_ppm_park_mask, pepfx/PEP_PPM_PARK_MASK, pepfx/PPEP_PPM_PARK_MASK"
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PPM_PARK_MASK
product: Windows
targetos: Windows
req.typenames: PEP_PPM_PARK_MASK, *PPEP_PPM_PARK_MASK, PEP_PPM_PARK_MASK, *PPEP_PPM_PARK_MASK
---

# _PEP_PPM_PARK_MASK structure


## -description


The <b>PEP_PROCESSOR_PARK_MASK</b> structure contains the current core parking mask.


## -syntax


````
typedef struct _PEP_PPM_PARK_MASK {
  ULONG                                              Count;
  ULONGLONG                                          EvaluationTime;
  _Field_size_full_(Count) PPEP_PROCESSOR_PARK_STATE Processors;
} PEP_PPM_PARK_MASK, *PPEP_PPM_PARK_MASK;
````


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



<a href="..\pepfx\ns-pepfx-_pep_processor_park_state.md">PEP_PROCESSOR_PARK_STATE</a>



 

 


