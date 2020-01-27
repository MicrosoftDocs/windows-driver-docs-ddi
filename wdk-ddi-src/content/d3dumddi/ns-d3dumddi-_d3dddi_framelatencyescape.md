---
UID: NS:d3dumddi._D3DDDI_FRAMELATENCYESCAPE
title: _D3DDDI_FRAMELATENCYESCAPE (d3dumddi.h)
description: Specifies an app's maximum frame latency.
old-location: display\d3dddi_framelatencyescape.htm
tech.root: display
ms.assetid: 19395349-375E-46AF-BCCF-FF5C92B374C4
ms.date: 05/10/2018
ms.keywords: D3DDDI_FRAMELATENCYESCAPE, D3DDDI_FRAMELATENCYESCAPE structure [Display Devices], _D3DDDI_FRAMELATENCYESCAPE, d3dumddi/D3DDDI_FRAMELATENCYESCAPE, display.d3dddi_framelatencyescape
f1_keywords:
 - "d3dumddi/D3DDDI_FRAMELATENCYESCAPE"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
- D3DDDI_FRAMELATENCYESCAPE
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_FRAMELATENCYESCAPE
---

# _D3DDDI_FRAMELATENCYESCAPE structure


## -description


Specifies an app's maximum frame latency.


## -struct-fields




### -field RequestedLatency

[in] The frame latency requested by the driver, specified as the number of frames that are allowed to be stored in a queue, before submission for rendering.

