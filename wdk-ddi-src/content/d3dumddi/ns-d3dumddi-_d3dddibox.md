---
UID: NS:d3dumddi._D3DDDIBOX
title: _D3DDDIBOX (d3dumddi.h)
description: Describes the bounds of a volume texture.
old-location: display\d3dddibox.htm
tech.root: display
ms.assetid: 3CE49C9F-EFFC-4F43-A939-623B28FD5EFB
ms.date: 05/10/2018
ms.keywords: D3DDDIBOX, D3DDDIBOX structure [Display Devices], _D3DDDIBOX, d3dumddi/D3DDDIBOX, display.d3dddibox
f1_keywords:
 - "d3dumddi/D3DDDIBOX"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3dumddi.h
api_name:
- D3DDDIBOX
product:
- Windows
targetos: Windows
req.typenames: D3DDDIBOX
---

# _D3DDDIBOX structure


## -description


Describes the bounds of a volume texture.


## -struct-fields




### -field Left

[in] The position of the left side of the box on the x-axis.


### -field Top

[in] The position of the top of the box on the y-axis.


### -field Right

[in] The position of the right side of the box on the x-axis.


### -field Bottom

[in] The position of the bottom of the box on the y-axis.


### -field Front


      [in] The position of the front of the box on the z-axis.


### -field Back

[in] The position of the back of the box on the z-axis.


## -remarks



The height of the volume equals the value in the <b>Bottom</b> member minus the value in the <b>Top</b> member (that is, height = bottom – top). 

The width of the volume equals the value in the <b>Right</b> member minus the value in the <b>Left</b> member (that is, width = right – left). 

The depth of the volume equals the value in the <b>Back</b> member minus the value in the <b>Front</b> member (that is, depth = back – front). 



