---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEODECODER
title: PFND3D11_1DDI_CREATEVIDEODECODER
description: Creates a video decoder object.
old-location: display\createvideodecoder.htm
ms.assetid: 41254f99-1806-428c-8bf3-7e736dbeec84
ms.date: 05/10/2018
ms.keywords: CreateVideoDecoder, CreateVideoDecoder callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEODECODER, PFND3D11_1DDI_CREATEVIDEODECODER callback, d3d10umddi/CreateVideoDecoder, display.createvideodecoder
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	CreateVideoDecoder
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_CREATEVIDEODECODER callback function


## -description


Creates a video decoder object.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*pCreateData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406310">D3D11_1DDIARG_CREATEVIDEODECODER</a> structure. This structure specifies the attributes of the video decoder object to be created.

### -param Arg2

*hDecoder* [in]

A handle to the driver's private data for the video decoder object. For more information, see the Remarks section.

### -param Arg3

*hRTDecode* [in]

A handle to the video decoder object that the driver should use when it calls back into the runtime.



## -returns



<b>CreateVideoDecoder</b> returns one of the following values:

| Return code | Description | 
|:--|:--|
| S_OK | The video decoder object was created successfully. | 
| D3DDDIERR_DEVICEREMOVED | The graphics adapter was removed. | 
| E_OUTOFMEMORY |     Memory was not available to complete the operation. | 


## -remarks



The Microsoft Direct3D runtime calls <i>CreateVideoDecoder</i> after it has called the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451610">CalcPrivateVideoDecoderSize</a> to determine the size in bytes for the private data that the driver requires for the video decoder object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video decoder object.

When the runtime  calls <i>CreateVideoDecoder</i>, it passes the handle to the private data memory in the <i>hDecoder</i> parameter. This handle is actually a pointer to the memory. 

The driver must keep track of the handle to the display device that was used to create the cryptographic session. The driver should fail all subsequent calls that use this created cryptographic session, such as <a href="https://msdn.microsoft.com/library/windows/hardware/hh451697">VideoDecoderBeginFrame</a>, if the display device that is specified in those calls is different from the display device that was used to create the video decoder. 






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451610">CalcPrivateVideoDecoderSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406310">D3D11_1DDIARG_CREATEVIDEODECODER</a>



<a href="https://msdn.microsoft.com/a48dcbae-3236-4523-bc14-4be694da9a7b">NegotiateCryptoSessionKeyExchange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451697">VideoDecoderBeginFrame</a>
 

 

