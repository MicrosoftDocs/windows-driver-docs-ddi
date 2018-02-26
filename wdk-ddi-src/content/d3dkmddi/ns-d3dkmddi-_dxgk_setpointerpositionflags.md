---
UID: NS:d3dkmddi._DXGK_SETPOINTERPOSITIONFLAGS
title: "_DXGK_SETPOINTERPOSITIONFLAGS"
author: windows-driver-content
description: The DXGK_SETPOINTERPOSITIONFLAGS structure identifies, in bit-field flags, information about a mouse pointer.
old-location: display\dxgk_setpointerpositionflags.htm
old-project: display
ms.assetid: c834080a-1a0a-4327-b80b-6e5eb3728605
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, A, D, DXGK_SETPOINTERPOSITIONFLAGS, DXGK_SETPOINTERPOSITIONFLAGS structure [Display Devices], DmStructs_57c5d8e6-b270-4423-8d85-5db8103e2492.xml, E, F, G, I, K, L, N, O, P, R, S, T, X, _, _DXGK_SETPOINTERPOSITIONFLAGS, d3dkmddi/DXGK_SETPOINTERPOSITIONFLAGS, display.dxgk_setpointerpositionflags"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_SETPOINTERPOSITIONFLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_SETPOINTERPOSITIONFLAGS
---

# _DXGK_SETPOINTERPOSITIONFLAGS structure


## -description


The <b>DXGK_SETPOINTERPOSITIONFLAGS</b> structure identifies, in bit-field flags, information about a mouse pointer.


## -syntax


````
typedef struct _DXGK_SETPOINTERPOSITIONFLAGS {
  union {
    struct {
      UINT Visible  :1;
      UINT Procedural  :1;
      UINT Reserved  :30;
    };
    UINT Value;
  };
} DXGK_SETPOINTERPOSITIONFLAGS;
````


## -struct-fields




### -field Visible

[in] A <b>UINT</b> value that specifies whether the mouse pointer is visible. If this member is set, the mouse pointer is visible; if this member is not set, the mouse pointer is invisible. The driver should ignore the values in the <b>X</b> and <b>Y</b> members of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_setpointerposition.md">DXGKARG_SETPOINTERPOSITION</a> structure if <b>Visible</b> is not set (that is, <b>Visible</b> is set to 0). 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Procedural

[in] A <b>UINT</b> value that specifies whether the mouse pointer position was set by an application with the <a href="https://msdn.microsoft.com/b17cf57f-dd96-4695-a51e-ee1e1f00f85f">SetCursorPos</a> or similar cursor function instead of coming from user device input.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).

Supported starting with Windows 8.


### -field Reserved

[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.


#### - Value

[in] A member in the union that <b>DXGK_SETPOINTERPOSITIONFLAGS</b> contains that can hold one 32-bit value that indicates information about a mouse pointer.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_setpointerposition.md">DXGKARG_SETPOINTERPOSITION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_SETPOINTERPOSITIONFLAGS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

