---
UID: NC:d3d10umddi.PFND3DWDDM2_1DDI_VIDEOPROCESSORSETOUTPUTHDRMETADATA
title: PFND3DWDDM2_1DDI_VIDEOPROCESSORSETOUTPUTHDRMETADATA
author: windows-driver-content
description: Includes HDR metadata to allow the video processor to optimize video for display.
ms.assetid: c7a687ae-1877-4565-9dd7-618e8cec81ff
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
topic_type:
-	apiref
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	PFND3DWDDM2_1DDI_VIDEOPROCESSORSETOUTPUTHDRMETADATA
product:
- Windows
targetos: Windows
tech.root: display
---

# PFND3DWDDM2_1DDI_VIDEOPROCESSORSETOUTPUTHDRMETADATA callback function

## -description

Implemented by the client driver to include HDR metadata to allow the video processor to optimize video for display. This callback sets the maximum brightness capability (in nits) of the display on which the content will be presented.

## -prototype

```cpp
//Declaration

PFND3DWDDM2_1DDI_VIDEOPROCESSORSETOUTPUTHDRMETADATA Pfnd3dwddm21DdiVideoprocessorsetoutputhdrmetadata;

// Definition

VOID Pfnd3dwddm21DdiVideoprocessorsetoutputhdrmetadata
(
	D3D10DDI_HDEVICE hDevice
	D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor
	D3DDDI_HDR_METADATA_TYPE Type
	UINT Size
	CONST VOID *pMetaData
)
{...}

```

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hVideoProcessor

A handle to the video processor object.

### -param Type

Indicates the type of the HDR metadata provided.

### -param Size

Indicates the type of the HDR metadata provided.

* For D3DDDI_HDR_METADATA_TYPE_NONE, the size should be 0.
* For D3DDDI_HDR_METADATA_TYPE_HDR10, the size is sizeof(D3DDDI_HDR_METADATA_HDR10).

### -param *pMetaData

Points to a structure containing the HDR metadata.

* For D3DDDI_HDR_METADATA_TYPE_NONE, this should be NULL.
* For D3DDDI_HDR_METADATA_TYPE_HDR10, this is a pointer to a DD3DDDI_HDR_METADATA_HDR10 structure.


## -returns

Returns VOID.

## -remarks

When processing an HDR stream, the driver may use this brightness information to tone map the video content to optimize it for the output display.

## -see-also

[D3DWDDM2_1DDI_VIDEODEVICEFUNCS structure](ns-d3d10umddi-d3dwddm2_1ddi_videodevicefuncs.md)
