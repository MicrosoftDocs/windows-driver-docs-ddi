---
UID: NS:d3d10umddi.D3DWDDM2_4DDIARG_VIDEODECODERBEGINFRAME_RS4_0
title: D3DWDDM2_4DDIARG_VIDEODECODERBEGINFRAME_RS4_0 (d3d10umddi.h)
description: A collection of histogram output buffers.
ms.assetid: ce36a841-b614-4b23-b6a4-7c4afe1adf57
ms.date: 10/19/2018
keywords: ["D3DWDDM2_4DDIARG_VIDEODECODERBEGINFRAME_RS4_0 structure"]
ms.keywords: D3DWDDM2_4DDIARG_VIDEODECODERBEGINFRAME_RS4_0, D3DWDDM2_4DDIARG_VIDEODECODERBEGINFRAME_RS4_0,
req.header: d3d10umddi.h
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
req.typenames: D3DWDDM2_4DDIARG_VIDEODECODERBEGINFRAME_RS4_0
targetos: Windows
tech.root: display
f1_keywords:
 - D3DWDDM2_4DDIARG_VIDEODECODERBEGINFRAME_RS4_0
 - d3d10umddi/D3DWDDM2_4DDIARG_VIDEODECODERBEGINFRAME_RS4_0
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3DWDDM2_4DDIARG_VIDEODECODERBEGINFRAME_RS4_0
product:
 - Windows
---

# D3DWDDM2_4DDIARG_VIDEODECODERBEGINFRAME_RS4_0 structure


## -description

A collection of histogram output buffers.

## -struct-fields

### -field hOutputView

A handle to the driver's private data for the video decoder output view. This handle was created through a call to the CreateVideoProcessorOutputView function.

### -field pContentKey

A pointer to a content key that was used to encrypt the video frame data. If no content key was used, set this member to NULL. If the caller provides a content key, the caller must use the session key to encrypt the content key.

### -field ContentKeySize

The size, in bytes, of the content key that is specified in the pContentKey member.

### -field Histograms

The array of component histograms.  A disabled component has it’s struct members set to zero.

## -remarks

## -see-also

