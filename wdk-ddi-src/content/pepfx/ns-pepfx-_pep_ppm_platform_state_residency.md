---
UID: NS:pepfx._PEP_PPM_PLATFORM_STATE_RESIDENCY
title: "_PEP_PPM_PLATFORM_STATE_RESIDENCY"
author: windows-driver-content
description: The PEP_PPM_PLATFORM_STATE_RESIDENCY structure specifies the accumulated residency time and transition count for a particular platform idle state.
old-location: kernel\pep_ppm_platform_state_residency.htm
tech.root: kernel
ms.assetid: 35DB4043-F1B6-43C0-B8E7-FCEFF1E7E459
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_PLATFORM_STATE_RESIDENCY, PEP_PPM_PLATFORM_STATE_RESIDENCY, PEP_PPM_PLATFORM_STATE_RESIDENCY structure [Kernel-Mode Driver Architecture], PPEP_PPM_PLATFORM_STATE_RESIDENCY, PPEP_PPM_PLATFORM_STATE_RESIDENCY structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_PLATFORM_STATE_RESIDENCY, kernel.pep_ppm_platform_state_residency, pepfx/PEP_PPM_PLATFORM_STATE_RESIDENCY, pepfx/PPEP_PPM_PLATFORM_STATE_RESIDENCY"
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
-	PEP_PPM_PLATFORM_STATE_RESIDENCY
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_PLATFORM_STATE_RESIDENCY, *PPEP_PPM_PLATFORM_STATE_RESIDENCY
---

# _PEP_PPM_PLATFORM_STATE_RESIDENCY structure


## -description


The <b>PEP_PPM_PLATFORM_STATE_RESIDENCY</b> structure specifies the accumulated residency time and transition count for a particular platform idle state.


## -struct-fields




### -field Residency

The accumulated residency time, in 100-nanosecond units. This is the total amount of time that the hardware platform has spent in this idle state since system startup.


### -field TransitionCount

The total number of times that the platform has entered this idle state since system startup.


## -remarks



The <b>States</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186817">PEP_PPM_PLATFORM_STATE_RESIDENCIES</a> structure is a pointer to an array of <b>PEP_PPM_PLATFORM_STATE_RESIDENCY</b> structures.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186817">PEP_PPM_PLATFORM_STATE_RESIDENCIES</a>
 

 

