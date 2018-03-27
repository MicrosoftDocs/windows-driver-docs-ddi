---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEOPROCESSORFILTERRANGE
title: PFND3D11_1DDI_GETVIDEOPROCESSORFILTERRANGE
author: windows-driver-content
description: Queries the range of values that the display miniport driver supports for a specified video processor filter.
old-location: display\getvideoprocessorfilterrange.htm
old-project: display
ms.assetid: ab3f8abb-4735-42c1-9664-8f2f5f7d5da7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11_1DDI_GETVIDEOPROCESSORFILTERRANGE, d3d10umddi/pfnGetVideoProcessorFilterRange, display.getvideoprocessorfilterrange, pfnGetVideoProcessorFilterRange, pfnGetVideoProcessorFilterRange callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	pfnGetVideoProcessorFilterRange
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_GETVIDEOPROCESSORFILTERRANGE callback


## -description


Queries the range of values that the display miniport driver supports for a specified video processor filter.


## -parameters




### -param Arg1


### -param Arg2


### -param Arg3


### -param *








#### - Filter [in]

The type of the video processor filter, specified as a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450982">D3D11_1DDI_VIDEO_PROCESSOR_FILTER</a> value.




#### - hDevice [in]

A handle to the display device (graphics context).




#### - hProcessorEnum [in]

A handle to a video processor enumeration object that was created through a call to the <a href="https://msdn.microsoft.com/38c27502-7e8a-45a1-8a7c-315300502480">CreateVideoProcessorEnum</a> function.




#### - pFilterRange [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450985">D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE</a> structure that specifies the range of values for the specified filter.




## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/38c27502-7e8a-45a1-8a7c-315300502480">CreateVideoProcessorEnum</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450982">D3D11_1DDI_VIDEO_PROCESSOR_FILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450985">D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_GETVIDEOPROCESSORFILTERRANGE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

