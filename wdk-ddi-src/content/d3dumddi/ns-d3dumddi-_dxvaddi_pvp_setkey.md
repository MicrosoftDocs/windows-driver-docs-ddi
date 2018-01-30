---
UID: NS:d3dumddi._DXVADDI_PVP_SETKEY
title: "_DXVADDI_PVP_SETKEY"
author: windows-driver-content
description: The DXVADDI_PVP_SETKEY structure describes a key that the decode device uses to start decoding a frame.
old-location: display\dxvaddi_pvp_setkey.htm
old-project: display
ms.assetid: 3707f9c9-109e-4ac2-bc34-c9f4f7651306
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVA2_Structs_fbd26ed2-13ce-4f15-a7de-544f6f5fac33.xml, _DXVADDI_PVP_SETKEY, display.dxvaddi_pvp_setkey, DXVADDI_PVP_SETKEY structure [Display Devices], d3dumddi/DXVADDI_PVP_SETKEY, DXVADDI_PVP_SETKEY
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
-	DXVADDI_PVP_SETKEY
product: Windows
targetos: Windows
req.typenames: DXVADDI_PVP_SETKEY
---

# _DXVADDI_PVP_SETKEY structure


## -description


The DXVADDI_PVP_SETKEY structure describes a key that the decode device uses to start decoding a frame. 


## -syntax


````
typedef struct _DXVADDI_PVP_SETKEY {
  DXVADDI_PVP_KEY128 ContentKey;
} DXVADDI_PVP_SETKEY;
````


## -struct-fields




### -field ContentKey

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_pvp_block128.md">DXVADDI_PVP_KEY128</a> structure that contains the 128-bit key.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_pvp_block128.md">DXVADDI_PVP_KEY128</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodebeginframe.md">D3DDDIARG_DECODEBEGINFRAME</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodebeginframe.md">DecodeBeginFrame</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_PVP_SETKEY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

