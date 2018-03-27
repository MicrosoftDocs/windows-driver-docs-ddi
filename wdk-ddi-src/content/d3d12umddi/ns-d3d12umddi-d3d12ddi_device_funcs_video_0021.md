---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0021
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0021
author: windows-driver-content
description: Contains video functions.
old-location: display\d3d12ddi_device_funcs_video.htm
old-project: display
ms.assetid: F4C385C8-00A2-44AB-A7E6-4C9AA19CFFB0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_DEVICE_FUNCS_VIDEO_0021, D3D12DDI_DEVICE_FUNCS_VIDEO_0021 structure [Display Devices], d3d12umddi/D3D12DDI_DEVICE_FUNCS_VIDEO, display.d3d12ddi_device_funcs_video
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_DEVICE_FUNCS_VIDEO_0021
product: Windows
targetos: Windows
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




<a href="https://msdn.microsoft.com/87B4873E-DD44-47E9-8E6A-5BA91218188F">D3D12DDI_DEVICE_FUNCS_CORE_0010</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_DEVICE_FUNCS_VIDEO_0021 structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

