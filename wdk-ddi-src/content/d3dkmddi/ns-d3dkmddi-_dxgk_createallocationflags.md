---
UID: NS:d3dkmddi._DXGK_CREATEALLOCATIONFLAGS
title: _DXGK_CREATEALLOCATIONFLAGS (d3dkmddi.h)
description: The DXGK_CREATEALLOCATIONFLAGS structure identifies how to create allocations.
old-location: display\dxgk_createallocationflags.htm
ms.assetid: 3c6c5515-855a-4016-a327-958959981f0f
ms.date: 05/10/2018
ms.keywords: DXGK_CREATEALLOCATIONFLAGS, DXGK_CREATEALLOCATIONFLAGS structure [Display Devices], DmStructs_320b15bf-5664-4fb9-9126-2c063ef75467.xml, _DXGK_CREATEALLOCATIONFLAGS, d3dkmddi/DXGK_CREATEALLOCATIONFLAGS, display.dxgk_createallocationflags
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_CREATEALLOCATIONFLAGS"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
- DXGK_CREATEALLOCATIONFLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_CREATEALLOCATIONFLAGS
---

# _DXGK_CREATEALLOCATIONFLAGS structure


## -description


The DXGK_CREATEALLOCATIONFLAGS structure identifies how to create allocations.


## -struct-fields




### -field Resource

A UINT value that specifies whether allocations belong to a resource. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that DXGK_CREATEALLOCATIONFLAGS contains that can hold a 32-bit value that identifies how to create allocations.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation">DXGKARG_CREATEALLOCATION</a>
 

 

