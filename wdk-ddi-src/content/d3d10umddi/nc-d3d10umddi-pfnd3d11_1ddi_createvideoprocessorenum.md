---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM
title: PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM (d3d10umddi.h)
description: Creates an enumeration object for the video processor capabilities of the driver.
old-location: display\createvideoprocessorenum.htm
ms.assetid: 38c27502-7e8a-45a1-8a7c-315300502480
ms.date: 05/10/2018
ms.keywords: CreateVideoProcessorEnum, CreateVideoProcessorEnum callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM, PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM callback, d3d10umddi/CreateVideoProcessorEnum, display.createvideoprocessorenum
ms.topic: callback
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- CreateVideoProcessorEnum
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM callback function


## -description


Creates an enumeration object for the video processor capabilities of the driver.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

pCreateData [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessorenum">D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM</a> structure. This structure specifies the attributes of the video processor enumeration object to be created.

### -param Arg2

hVideoProcessorEnum [in]

A handle to the driver's private data for the video processor enumeration object. For more information, see the Remarks section.

### -param Arg3

hRTVideoProcessorEnum [in]

A handle to the video processor enumeration object that the driver should use when it calls back into the Direct3D runtime.


## -returns



<b>CreateVideoProcessorEnum</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The video processor enumeration object was created successfully.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|

## -remarks



The Direct3D runtime calls <i>CreateVideoProcessorEnum</i> after it has called the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorsize">CalcPrivateVideoProcessorEnumSize </a>   to determine the size in bytes for the private data that the driver requires for the video processor enumeration object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video processor enumeration object.

When the runtime  calls <i>CreateVideoProcessorEnum</i>, it passes the handle to the private data memory in the <i>hVideoProcessorEnum</i> parameter. This handle is actually a pointer to the memory. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorsize">CalcPrivateVideoProcessorEnumSize </a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessorenum">D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM</a>
 

 

