---
UID: NS:d3dumddi._D3DDDI_FRAMELATENCYESCAPE
title: "_D3DDDI_FRAMELATENCYESCAPE"
author: windows-driver-content
description: Specifies an app's maximum frame latency.
old-location: display\d3dddi_framelatencyescape.htm
old-project: display
ms.assetid: 19395349-375E-46AF-BCCF-FF5C92B374C4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDI_FRAMELATENCYESCAPE, display.d3dddi_framelatencyescape, _D3DDDI_FRAMELATENCYESCAPE, D3DDDI_FRAMELATENCYESCAPE structure [Display Devices], d3dumddi/D3DDDI_FRAMELATENCYESCAPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dumddi.h
apiname:
-	D3DDDI_FRAMELATENCYESCAPE
product: Windows
targetos: Windows
req.typenames: D3DDDI_FRAMELATENCYESCAPE
---

# _D3DDDI_FRAMELATENCYESCAPE structure


## -description


Specifies an app's maximum frame latency.


## -syntax


````
typedef struct _D3DDDI_FRAMELATENCYESCAPE {
  UINT RequestedLatency;
} D3DDDI_FRAMELATENCYESCAPE;
````


## -struct-fields




### -field RequestedLatency

[in] The frame latency requested by the driver, specified as the number of frames that are allowed to be stored in a queue, before submission for rendering.

