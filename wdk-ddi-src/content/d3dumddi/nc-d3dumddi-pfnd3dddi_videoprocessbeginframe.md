---
UID: NC:d3dumddi.PFND3DDDI_VIDEOPROCESSBEGINFRAME
title: PFND3DDDI_VIDEOPROCESSBEGINFRAME
author: windows-driver-content
description: The VideoProcessBeginFrame function notifies the user-mode display driver that processing of a video frame can begin on the specified Microsoft DirectX Video Accelerator (VA) video processing device.
old-location: display\videoprocessbeginframe.htm
old-project: display
ms.assetid: 1b7b1774-3144-4929-83d8-c52a7de6936d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoProcessBeginFrame
req.alt-loc: d3dumddi.h
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_VIDEOPROCESSBEGINFRAME callback



## -description
The <i>VideoProcessBeginFrame</i> function notifies the user-mode display driver that processing of a video frame can begin on the specified Microsoft DirectX Video Accelerator (VA) video processing device.



## -prototype

````
PFND3DDDI_VIDEOPROCESSBEGINFRAME VideoProcessBeginFrame;

__checkReturn HRESULT APIENTRY VideoProcessBeginFrame(
  _In_ HANDLE hDevice,
  _In_ HANDLE hVideoProcessor
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param hVideoProcessor [in]

 The handle to the DirectX VA video processing device that should start processing the video frame. The <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvideoprocessdevice.md">CreateVideoProcessDevice</a> function created this handle.


## -returns
<i>VideoProcessBeginFrame</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>Video frame processing successfully began.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><i>VideoProcessBeginFrame</i> could not allocate the required memory for it to complete.

 


## -remarks
The <i>VideoProcessBeginFrame</i> function notifies the user-mode display driver that its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessblt.md">VideoProcessBlt</a> function can be called on the specified video processing device.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvideoprocessdevice.md">CreateVideoProcessDevice</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessblt.md">VideoProcessBlt</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_VIDEOPROCESSBEGINFRAME callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

