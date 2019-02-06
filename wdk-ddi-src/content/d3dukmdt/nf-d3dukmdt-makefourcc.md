---
UID: NF:d3dukmdt.MAKEFOURCC
title: MAKEFOURCC macro (d3dukmdt.h)
description: A macro to format and load texture.
ms.assetid: c87722a0-3f6d-4d67-a303-d5fef4405daf
ms.date: 10/19/2018
ms.topic: macro
ms.keywords: MAKEFOURCC
req.header: d3dukmdt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3dukmdt.h
api_name: 
-	MAKEFOURCC
product:
-	Windows
targetos: Windows


ms.custom: RS5
tech.root: display
---

# MAKEFOURCC macro


## -description

A macro to format and load texture.

Each parameter can represent one of the following naming conventions:

* A = Alpha
* R = Red
* G = Green
* B = Blue
* X = Unused Bits
* P = Palette
* L = Luminance
* U = dU coordinate for BumpMap
* V = dV coordinate for BumpMap
* S = Stencil
* D = Depth (e.g. Z or W buffer)
* C = Computed from other channels (typically on certain read operations)


Furthermore, the order of the pieces are from MSB first; hence D3DFMT_A8L8 indicates that the high byte of this two byte format is alpha.

D16 indicates:

* An integer 16-bit value.
* An app-lockable surface.

All Depth/Stencil formats except D3DFMT_D16_LOCKABLE indicate:

* No particular bit ordering per pixel, and
* Are not app lockable, and
* The driver is allowed to consume more than the indicated number of bits per Depth channel (but not Stencil channel).

## -parameters

### -param ch0

Any of the defined naming conventions.

### -param ch1

Any of the defined naming conventions.

### -param ch2

Any of the defined naming conventions.

### -param ch3

Any of the defined naming conventions.


## -remarks

## -see-also
