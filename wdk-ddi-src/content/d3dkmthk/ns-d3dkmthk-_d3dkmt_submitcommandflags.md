---
UID: NS:d3dkmthk._D3DKMT_SUBMITCOMMANDFLAGS
title: _D3DKMT_SUBMITCOMMANDFLAGS (d3dkmthk.h)
description: Structure that identifies, in bit-field flags, information about a direct memory access (DMA) buffer to submit to the graphics processing unit (GPU).
ms.date: 10/19/2018
keywords: ["D3DKMT_SUBMITCOMMANDFLAGS structure"]
ms.keywords: _D3DKMT_SUBMITCOMMANDFLAGS, D3DKMT_SUBMITCOMMANDFLAGS,
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_SUBMITCOMMANDFLAGS
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_SUBMITCOMMANDFLAGS
 - d3dkmthk/_D3DKMT_SUBMITCOMMANDFLAGS
 - D3DKMT_SUBMITCOMMANDFLAGS
 - d3dkmthk/D3DKMT_SUBMITCOMMANDFLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_SUBMITCOMMANDFLAGS
dev_langs:
 - c++
---

# _D3DKMT_SUBMITCOMMANDFLAGS structure


## -description

Structure that identifies, in bit-field flags, information about a direct memory access (DMA) buffer to submit to the graphics processing unit (GPU).

## -struct-fields

### -field NullRendering

[in] A UINT value that specifies whether the driver should simulate the insertion of the DMA buffer into the ring (that is, whether the driver should generate the fence interrupt at the end of the DMA buffer); however, the driver should not actually run (render) the DMA buffer.

### -field PresentRedirected

[in] A UINT value that specifies whether the DMA buffer contains a redirected present operation, which is a present to a shared allocation that belongs to the Display Windows Manager.

### -field Reserved

Reserved for internal use.

## -remarks

## -see-also

