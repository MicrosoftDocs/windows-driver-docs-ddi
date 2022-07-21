---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYVIDEOENCODERHEAP_0080
tech.root: display
title: PFND3D12DDI_DESTROYVIDEOENCODERHEAP_0080
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the PFND3D12DDI_DESTROYVIDEOENCODERHEAP_0080 callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_DESTROYVIDEOENCODERHEAP_0080
f1_keywords:
 - PFND3D12DDI_DESTROYVIDEOENCODERHEAP_0080
 - d3d12umddi/PFND3D12DDI_DESTROYVIDEOENCODERHEAP_0080
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3D12DDI_DESTROYVIDEOENCODERHEAP_0080
---

## -description

A client driver's **PFND3D12DDI_DESTROYVIDEOENCODERHEAP_0080** callback function destroys a video encoder heap object.

## -parameters

### -param hDrvDevice [in]

Handle to the D3D12 device.

### -param hDrvVideoEncoderHeap [in]

Handle to the D3D12 video encoder heap object created in a call to [**PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2**](nc-d3d12umddi-pfnd3d12ddi_createvideoencoderheap_0080_2.md).

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**PFND3D12DDI_CREATEVIDEOENCODERHEAP_0080_2**](nc-d3d12umddi-pfnd3d12ddi_createvideoencoderheap_0080_2.md)
