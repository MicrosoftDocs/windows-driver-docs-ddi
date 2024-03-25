---
UID: NC:d3d10umddi.PFND3D10DDI_RETRIEVESUBOBJECT
title: PFND3D10DDI_RETRIEVESUBOBJECT (d3d10umddi.h)
description: Retrieves subparts of the Direct3D driver device object.
old-location: display\retrievesubobject_d3d11_1_.htm
ms.date: 01/17/2023
keywords: ["PFND3D10DDI_RETRIEVESUBOBJECT callback function"]
ms.keywords: PFND3D10DDI_RETRIEVESUBOBJECT, PFND3D10DDI_RETRIEVESUBOBJECT callback, RetrieveSubObject(D3D11_1), RetrieveSubObject(D3D11_1) callback function [Display Devices], d3d10umddi/RetrieveSubObject(D3D11_1), display.retrievesubobject, display.retrievesubobject_d3d11_1_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D10DDI_RETRIEVESUBOBJECT
 - d3d10umddi/PFND3D10DDI_RETRIEVESUBOBJECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_RETRIEVESUBOBJECT
---

# PFND3D10DDI_RETRIEVESUBOBJECT callback function

## -description

The Direct3D runtime calls the driver's **PFND3D10DDI_RETRIEVESUBOBJECT** function to retrieve subparts of the Direct3D driver device object.

## -parameters

### -param unnamedParam1

*hDevice* [in] A handle to the display device (graphics context).

### -param SubDeviceID

Sub-device ID that identifies the function table being retrieved. See Remarks.

### -param ParamSize

The size, in bytes, of the input parameter structure that **pParams** points to.

### -param pParams

A pointer to an input parameter structure that is described by the **SubDeviceID** parameter. See Remarks.

### -param OutputParamSize

The size, in bytes, of the output parameter structure that **pOutputParamsBuffer** points to.

### -param pOutputParamsBuffer

A pointer to an output parameter structure that is described by the **SubDeviceID** parameter. See Remarks.

## -returns

Returns S_OK if the operation succeeds. Otherwise, this function returns an appropriate error result.

## -remarks

The following table describes the possible values for **SubDeviceID**, the associated input structure pointed to by **pParams**, and the output structure that **PFND3D10DDI_RETRIEVESUBOBJECT** returns in the buffer pointed to by **pOutputParamsBuffer** .

| SubDeviceID | Meaning | pParams | pOutputParamsBuffer |
| ----------- | ------- | ------- | ------------------- |
| 2     | Sub ID for a D3D 11 video function table. | [**D3D11_1DDI_VIDEO_INPUT**](ns-d3d10umddi-d3d11_1ddi_video_input.md) | [**D3D11_1DDI_VIDEODEVICEFUNCS**](ns-d3d10umddi-d3d11_1ddi_videodevicefuncs.md) |
| 3     | Sub ID for a WDDM 2.0 video function table. | [**D3DWDDM2_0DDI_VIDEO_INPUT**](ns-d3d10umddi-d3dwddm2_0ddi_video_input.md) | [**D3DWDDM2_0DDI_VIDEODEVICEFUNCS**](./ns-d3d10umddi-d3dwddm2_0ddi_videodevicefuncs.md) |
| 5     | Sub ID for a WDDM 2.1 video function table. | [**D3DWDDM2_1DDI_VIDEO_INPUT**](ns-d3d10umddi-d3dwddm2_1ddi_video_input.md) | [**D3DWDDM2_1DDI_VIDEODEVICEFUNCS**](./ns-d3d10umddi-d3dwddm2_1ddi_videodevicefuncs.md) .|
| 6     | Sub ID for a WDDM 2.4 and later video function table. Supported starting with WDDM 2.4. | [**D3DWDDM2_4DDI_VIDEO_INPUT**](ns-d3d10umddi-d3dwddm2_4ddi_video_input.md) | [**D3DWDDM2_4DDI_VIDEODEVICEFUNCS**](./ns-d3d10umddi-d3dwddm2_4ddi_videodevicefuncs.md). |
| 7     | Sub ID for a WDDM 2.4 (Windows 10 version 1803 release) video function table. | [**D3DWDDM2_4DDI_VIDEO_INPUT_RS4_0**](ns-d3d10umddi-d3dwddm2_4ddi_video_input_rs4_0.md) | [**D3DWDDM2_4DDI_VIDEODEVICEFUNCS_RS4_0**](ns-d3d10umddi-d3dwddm2_4ddi_videodevicefuncs_rs4_0.md) |

The Direct3D runtime considers the retrieved subparts to be appended to the Direct3D driver device object and expects them to be destroyed along with the rest of the device when [**DestroyDevice**](nc-d3d10umddi-pfnd3d10ddi_destroydevice.md) is called.

Subdevices are retrieved from the root device object independently. The DDI interface version is provided implicitly within the sub-device ID.

This function is free-threaded.

## -see-also

[**DestroyDevice**](nc-d3d10umddi-pfnd3d10ddi_destroydevice.md)
