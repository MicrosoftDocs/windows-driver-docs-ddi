---
UID: NS:d3dumddi._D3DDDIARG_DISCARD
title: _D3DDDIARG_DISCARD (d3dumddi.h)
description: Defines video display memory that can be discarded because the contents are no longer needed.
old-location: display\d3dddiarg_discard.htm
tech.root: display
ms.assetid: 6efee74e-9e82-4631-8360-19061b0c015d
ms.date: 05/10/2018
keywords: ["_D3DDDIARG_DISCARD structure"]
ms.keywords: D3DDDIARG_DISCARD, D3DDDIARG_DISCARD structure [Display Devices], _D3DDDIARG_DISCARD, d3dumddi/D3DDDIARG_DISCARD, display.d3dddiarg_discard
f1_keywords:
 - "d3dumddi/D3DDDIARG_DISCARD"
 - "D3DDDIARG_DISCARD"
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
- D3DDDIARG_DISCARD
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DISCARD
---

# _D3DDDIARG_DISCARD structure


## -description


Defines video display memory that can be discarded because the contents are no longer needed.


## -struct-fields




### -field hResource

A handle to the resource in which subresources are to be discarded.


### -field FirstSubResource

The index of the first subresource to be discarded.


### -field NumSubResources

The number of subresources to be discarded.


### -field pRects

An array of <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a> structures for the rectangles in the resource view to discard. If <b>NULL</b>, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_discard">Discard</a> function discards the entire surface.


### -field NumRects

The number of rectangles in the array that the  <b>pRects</b> member specifies.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_discard">Discard</a>



<a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>
 

 

