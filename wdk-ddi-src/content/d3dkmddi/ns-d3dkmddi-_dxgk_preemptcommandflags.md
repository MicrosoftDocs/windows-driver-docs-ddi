---
UID: NS:d3dkmddi._DXGK_PREEMPTCOMMANDFLAGS
title: _DXGK_PREEMPTCOMMANDFLAGS (d3dkmddi.h)
description: The DXGK_PREEMPTCOMMANDFLAGS structure specifies a union that contains either a structure with a reserved member or a 32-bit value. No bit-field flags are currently defined.
old-location: display\dxgk_preemptcommandflags.htm
ms.assetid: 24444451-7323-4e1a-9981-cf5caa00c4e3
ms.date: 05/10/2018
ms.keywords: DXGK_PREEMPTCOMMANDFLAGS, DXGK_PREEMPTCOMMANDFLAGS structure [Display Devices], DmStructs_7163ce37-49c8-4b17-aadc-cd36ad5cac9d.xml, _DXGK_PREEMPTCOMMANDFLAGS, d3dkmddi/DXGK_PREEMPTCOMMANDFLAGS, display.dxgk_preemptcommandflags
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_PREEMPTCOMMANDFLAGS"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- d3dkmddi.h
api_name:
- DXGK_PREEMPTCOMMANDFLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_PREEMPTCOMMANDFLAGS
---

# _DXGK_PREEMPTCOMMANDFLAGS structure


## -description


The DXGK_PREEMPTCOMMANDFLAGS structure specifies a union that contains either a structure with a reserved member or a 32-bit value. No bit-field flags are currently defined.


## -struct-fields




### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting all 32 bits (0xFFFFFFFF) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that DXGK_PREEMPTCOMMANDFLAGS contains that can hold a 32-bit value.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_preemptcommand">DXGKARG_PREEMPTCOMMAND</a>
 

 

