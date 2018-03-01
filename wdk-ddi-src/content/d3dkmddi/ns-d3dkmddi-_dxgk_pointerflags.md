---
UID: NS:d3dkmddi._DXGK_POINTERFLAGS
title: "_DXGK_POINTERFLAGS"
author: windows-driver-content
description: The DXGK_POINTERFLAGS structure identifies mouse pointer capabilities of the display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_pointerflags.htm
old-project: display
ms.assetid: 0d49a089-700e-42c0-a1f3-7b181b8aef96
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_POINTERFLAGS, DXGK_POINTERFLAGS structure [Display Devices], DmStructs_e2e2d800-cf64-44f9-95a2-a5eca8b8c303.xml, _DXGK_POINTERFLAGS, d3dkmddi/DXGK_POINTERFLAGS, display.dxgk_pointerflags
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_POINTERFLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_POINTERFLAGS
---

# _DXGK_POINTERFLAGS structure


## -description


The DXGK_POINTERFLAGS structure identifies mouse pointer capabilities of the display miniport driver that the driver provides through a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.


## -syntax


````
typedef struct _DXGK_POINTERFLAGS {
  union {
    struct {
      UINT Monochrome  :1;
      UINT Color  :1;
      UINT MaskedColor  :1;
      UINT Reserved  :29;
    };
    UINT Value;
  };
} DXGK_POINTERFLAGS;
````


## -struct-fields




### -field Monochrome

A UINT value that specifies whether the mouse pointer can display in monochrome. Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Color

A UINT value that specifies whether the mouse pointer can display in color and with transparency (alpha). Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field MaskedColor

A UINT value that specifies whether the mouse pointer can display in color and with a mask value in the transparency (alpha) bits. Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFF8) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that DXGK_POINTERFLAGS contains that can hold a 32-bit value that identifies mouse pointer capabilities.


## -remarks



The display miniport driver can specify mouse pointer capabilities by setting bits in the 32-bit <b>Value</b> member or by setting individual members of the structure in the union that DXGK_POINTERFLAGS contains.

The driver always specifies a color mouse pointer by using a A8R8G8B8 pixel format.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_POINTERFLAGS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

