---
UID: NS:d3dumddi._D3DDDI_COLORFILLFLAGS
title: "_D3DDDI_COLORFILLFLAGS"
author: windows-driver-content
description: The D3DDDI_COLORFILLFLAGS structure describes how to color-fill a rectangle on a surface.
old-location: display\d3dddi_colorfillflags.htm
old-project: display
ms.assetid: 672baa43-7fa1-4c10-9d60-c7c8a4729f26
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, C, D, D3DDDI_COLORFILLFLAGS, D3DDDI_COLORFILLFLAGS structure [Display Devices], D3D_other_Structs_555ecebb-bdd8-4c7f-97cd-801216506b9e.xml, F, G, I, L, O, R, S, _, _D3DDDI_COLORFILLFLAGS, d3dumddi/D3DDDI_COLORFILLFLAGS, display.d3dddi_colorfillflags"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDI_COLORFILLFLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_COLORFILLFLAGS
---

# _D3DDDI_COLORFILLFLAGS structure


## -description


The D3DDDI_COLORFILLFLAGS structure describes how to color-fill a rectangle on a surface.


## -syntax


````
typedef struct _D3DDDI_COLORFILLFLAGS {
  union {
    struct {
      UINT PresentToDwm  :1;
      UINT Reserved  :31;
    };
    UINT   Value;
  };
} D3DDDI_COLORFILLFLAGS;
````


## -struct-fields




### -field PresentToDwm

A UINT value that specifies whether the Microsoft Direct3D runtime begins and ends a desktop window manager (DWM) present operation during the color-fill operation. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that is contained in D3DDDI_COLORFILLFLAGS that can hold one 32-bit value that identifies how to color-fill a rectangle on a surface.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_colorfill.md">D3DDDIARG_COLORFILL</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_colorfill.md">ColorFill</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_COLORFILLFLAGS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

