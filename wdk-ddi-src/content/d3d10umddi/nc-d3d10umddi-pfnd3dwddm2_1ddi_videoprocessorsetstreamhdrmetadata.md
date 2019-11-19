---
UID: NC:d3d10umddi.PFND3DWDDM2_1DDI_VIDEOPROCESSORSETSTREAMHDRMETADATA
title: PFND3DWDDM2_1DDI_VIDEOPROCESSORSETSTREAMHDRMETADATA (d3d10umddi.h)
description: Sets stream HDR metadata to optimize video for display.
ms.assetid: 7f8e5e1b-ba6a-4ac7-b1c4-6d3ee54bc822
ms.date: 10/19/2018
ms.topic: callback
req.header: d3d10umddi.h
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d10umddi/PFND3DWDDM2_1DDI_VIDEOPROCESSORSETSTREAMHDRMETADATA"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3DWDDM2_1DDI_VIDEOPROCESSORSETSTREAMHDRMETADATA
product:
 - Windows
dev_langs:
 - c++
---

# PFND3DWDDM2_1DDI_VIDEOPROCESSORSETSTREAMHDRMETADATA callback function

## -description

Implemented by the client driver to set stream HDR metadata to optimize video for display. This callback sets the maximum number of nits for which the content was authored.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hVideoProcessor

A handle to the video processor object.

### -param StreamIndex

Indicates the input stream.

### -param Type

Indicates the type of the HDR metadata provided.

### -param Size

Indicates the type of the HDR metadata provided.

* For D3DDDI_HDR_METADATA_TYPE_NONE, the size should be 0.
* For D3DDDI_HDR_METADATA_TYPE_HDR10, the size is sizeof(D3DDDI_HDR_METADATA_HDR10).

### -param pMetaData

Points to a structure containing the HDR metadata.

* For D3DDDI_HDR_METADATA_TYPE_NONE, this should be NULL.
* For D3DDDI_HDR_METADATA_TYPE_HDR10, this is a pointer to a DD3DDDI_HDR_METADATA_HDR10 structure.

## -prototype

```cpp
//Declaration

PFND3DWDDM2_1DDI_VIDEOPROCESSORSETSTREAMHDRMETADATA Pfnd3dwddm21DdiVideoprocessorsetstreamhdrmetadata;

// Definition

VOID Pfnd3dwddm21DdiVideoprocessorsetstreamhdrmetadata
(
	D3D10DDI_HDEVICE hDevice
	D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor
	UINT StreamIndex
	D3DDDI_HDR_METADATA_TYPE Type
	UINT Size
	CONST VOID *pMetaData
)
{...}

```

## -remarks

When processing an HDR stream, the driver may use this brightness information to tone map the video content to optimize it for the output display.

## -see-also

[D3DWDDM2_1DDI_VIDEODEVICEFUNCS structure](ns-d3d10umddi-d3dwddm2_1ddi_videodevicefuncs.md)

