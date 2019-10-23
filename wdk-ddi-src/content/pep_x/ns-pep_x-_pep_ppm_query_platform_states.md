---
UID: NS:pep_x._PEP_PPM_QUERY_PLATFORM_STATES
title: _PEP_PPM_QUERY_PLATFORM_STATES (pep_x.h)
description: The PEP_PPM_QUERY_PLATFORM_STATES structure specifies the number of platform idle states the hardware platform supports.
old-location: kernel\pep_ppm_query_platform_states.htm
tech.root: kernel
ms.assetid: 488EC668-15B9-4B6F-B8AA-3142DB87D19B
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_QUERY_PLATFORM_STATES, PEP_PPM_QUERY_PLATFORM_STATES, PEP_PPM_QUERY_PLATFORM_STATES structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_PLATFORM_STATES, PPEP_PPM_QUERY_PLATFORM_STATES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_PLATFORM_STATES, kernel.pep_ppm_query_platform_states, pepfx/PEP_PPM_QUERY_PLATFORM_STATES, pepfx/PPEP_PPM_QUERY_PLATFORM_STATES"
ms.topic: struct
f1_keywords:
 - "pep_x/PEP_PPM_QUERY_PLATFORM_STATES"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_PPM_QUERY_PLATFORM_STATES
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_PLATFORM_STATES, *PPEP_PPM_QUERY_PLATFORM_STATES
---

# _PEP_PPM_QUERY_PLATFORM_STATES structure


## -description


The <b>PEP_PPM_QUERY_PLATFORM_STATES</b> structure specifies the number of platform idle states the hardware platform supports.


## -struct-fields




### -field PlatformStateCount

The number of platform idle states supported by the platform.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>
 

 

