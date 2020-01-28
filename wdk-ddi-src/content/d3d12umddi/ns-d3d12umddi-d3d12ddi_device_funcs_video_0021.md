---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0021
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0021 (d3d12umddi.h)
description: Contains video functions.
old-location: display\d3d12ddi_device_funcs_video.htm
ms.assetid: F4C385C8-00A2-44AB-A7E6-4C9AA19CFFB0
ms.date: 05/10/2018
ms.keywords: D3D12DDI_DEVICE_FUNCS_VIDEO_0021, D3D12DDI_DEVICE_FUNCS_VIDEO_0021 structure [Display Devices], d3d12umddi/D3D12DDI_DEVICE_FUNCS_VIDEO, display.d3d12ddi_device_funcs_video
f1_keywords:
 - "d3d12umddi/D3D12DDI_DEVICE_FUNCS_VIDEO_0021"
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Windows 10, version 1709
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
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDI_DEVICE_FUNCS_VIDEO_0021
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_DEVICE_FUNCS_VIDEO_0021
---

# D3D12DDI_DEVICE_FUNCS_VIDEO_0021 structure


## -description


Contains video functions.


## -struct-fields




### -field pfnGetCaps

A function that gets video capabilities.


### -field pfnCalcPrivateVideoDecoderSize

A function that calculates the size of a private decoder.


### -field pfnCreateVideoDecoder

A function that creates a video decoder.


### -field pfnDestroyVideoDecoder

A function that destroys a video decoder.


### -field pfnCalcPrivateVideoProcessorSize

A function that calculates the size of a private video processor.


### -field pfnCreateVideoProcessor

A function that creates a video processor.


### -field pfnDestroyVideoProcessor

A function that destroys a video processor.


### -field pfnCalcPrivateContentProtectionSessionSize

A function that calculates the size of a private content protection session.


### -field pfnCreateContentProtectionSession

A function that creates a content protection system.


### -field pfnDestroyContentProtectionSession

A function that destroys a content protection system.


### -field pfnContentProtectionSessionInvokeFunction

A function that invokes a function in a content protection session.


### -field pfnContentProtectionSessionSetupHardwareKey

A function that sets up a hardware key for a content protection session.


### -field pfnContentProtectionSessionGetStatus

A function that gets the status of a content protection session.


### -field pfnGetDecodeProfileCount

A function that gets the decode profile count.


### -field pfnGetDecodeFormatCount

A function that gets the decode format count.


### -field pfnGetBitstreamEncryptionSchemeCount

A function that gets the count of bitstream encryption schemes.


### -field pfnDecoderTrimAllocations

A function that trims decoder allocations.


### -field pfnProcessorTrimAllocations

A function that trims processor allocations.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_device_funcs_core_0010">D3D12DDI_DEVICE_FUNCS_CORE_0010</a>
 

 

