---
UID: NS:d3dkmddi._DXGK_SETPOINTERPOSITIONFLAGS
title: "_DXGK_SETPOINTERPOSITIONFLAGS"
description: The DXGK_SETPOINTERPOSITIONFLAGS structure identifies, in bit-field flags, information about a mouse pointer.
old-location: display\dxgk_setpointerpositionflags.htm
ms.assetid: c834080a-1a0a-4327-b80b-6e5eb3728605
ms.date: 05/10/2018
ms.keywords: DXGK_SETPOINTERPOSITIONFLAGS, DXGK_SETPOINTERPOSITIONFLAGS structure [Display Devices], DmStructs_57c5d8e6-b270-4423-8d85-5db8103e2492.xml, _DXGK_SETPOINTERPOSITIONFLAGS, d3dkmddi/DXGK_SETPOINTERPOSITIONFLAGS, display.dxgk_setpointerpositionflags
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_SETPOINTERPOSITIONFLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_SETPOINTERPOSITIONFLAGS
---

# _DXGK_SETPOINTERPOSITIONFLAGS structure


## -description


The <b>DXGK_SETPOINTERPOSITIONFLAGS</b> structure identifies, in bit-field flags, information about a mouse pointer.


## -struct-fields




### -field Visible

[in] A <b>UINT</b> value that specifies whether the mouse pointer is visible. If this member is set, the mouse pointer is visible; if this member is not set, the mouse pointer is invisible. The driver should ignore the values in the <b>X</b> and <b>Y</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557660">DXGKARG_SETPOINTERPOSITION</a> structure if <b>Visible</b> is not set (that is, <b>Visible</b> is set to 0). 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Procedural

[in] A <b>UINT</b> value that specifies whether the mouse pointer position was set by an application with the <a href="https://msdn.microsoft.com/b17cf57f-dd96-4695-a51e-ee1e1f00f85f">SetCursorPos</a> or similar cursor function instead of coming from user device input.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).

Supported starting with Windows 8.


### -field Reserved

[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.


### -field Value

[in] A member in the union that <b>DXGK_SETPOINTERPOSITIONFLAGS</b> contains that can hold one 32-bit value that indicates information about a mouse pointer.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557660">DXGKARG_SETPOINTERPOSITION</a>
 

 

