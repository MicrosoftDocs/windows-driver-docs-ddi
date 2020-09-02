---
UID: NC:d3d10umddi.PFND3D10DDI_RETRIEVESUBOBJECT
title: PFND3D10DDI_RETRIEVESUBOBJECT (d3d10umddi.h)
description: Retrieves subparts of the Microsoft Direct3D driver device object.
old-location: display\retrievesubobject_d3d11_1_.htm
ms.assetid: 9029ec8d-102f-4d83-8ab5-fc208d8b5249
ms.date: 05/10/2018
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
 - RetrieveSubObject(D3D11_1)
product:
 - Windows
---

# PFND3D10DDI_RETRIEVESUBOBJECT callback function


## -description

Retrieves subparts of the Microsoft Direct3D driver device object.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param SubDeviceID

The function table being retrieved, with the following possible values.

| **Value** | **Meaning** | 
|:--|:--|
| 1 | A video function table that is described as a structure. The function returns a [D3D11_1DDI_VIDEODEVICEFUNCS](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_videodevicefuncs)  structure in the buffer referenced by the pOutputParamsBuffer parameter. | 
| 3 | A WDDM 2.0 and later video function table that is described as a structure. The function returns a [D3DWDDM2_0DDI_VIDEODEVICEFUNCS](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_videodevicefuncs) structure in the buffer referenced by the pOutputParamsBuffer parameter.
Supported starting with WDDM 2.0. |

### -param ParamSize

The size, in bytes, of an input parameter structure that is described by the <i>SubDeviceID</i> parameter.

### -param pParams

A pointer to an input parameter structure that is described by the <i>SubDeviceID</i> parameter.

### -param OutputParamSize

The size, in bytes, of an output parameter structure that is described by the <i>SubDeviceID</i> parameter.

### -param pOutputParamsBuffer

A pointer to an output parameter structure that is described by the <i>SubDeviceID</i> parameter.

## -returns

Returns S_OK if the operation succeeds. Otherwise, this function returns an appropriate error result.

## -remarks

The Direct3D runtime considers the retrieved subparts to be appended to the Direct3D driver device object and expects  them to be destroyed along with the rest of the device when <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydevice">DestroyDevice</a> is called.

Subdevices are retrieved from the root device object independently. The DDI interface version is provided implicitly within the subdevice ID.

This function is free-threaded.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_videodevicefuncs">D3D11_1DDI_VIDEODEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_videodevicefuncs">D3DWDDM2_0DDI_VIDEODEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydevice">DestroyDevice</a>

