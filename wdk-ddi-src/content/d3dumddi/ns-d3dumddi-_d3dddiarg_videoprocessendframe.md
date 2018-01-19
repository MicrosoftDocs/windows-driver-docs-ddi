---
UID: NS:d3dumddi._D3DDDIARG_VIDEOPROCESSENDFRAME
title: _D3DDDIARG_VIDEOPROCESSENDFRAME
author: windows-driver-content
description: The D3DDDIARG_VIDEOPROCESSENDFRAME structure specifies the Microsoft DirectX Video Accelerator (VA) video process that should stop processing a frame.
old-location: display\d3dddiarg_videoprocessendframe.htm
old-project: display
ms.assetid: 948f10cb-215c-4a21-a275-ffdbf0ee1593
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIARG_VIDEOPROCESSENDFRAME, D3DDDIARG_VIDEOPROCESSENDFRAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_VIDEOPROCESSENDFRAME
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
req.typenames: D3DDDIARG_VIDEOPROCESSENDFRAME
---

# _D3DDDIARG_VIDEOPROCESSENDFRAME structure



## -description
The D3DDDIARG_VIDEOPROCESSENDFRAME structure specifies the Microsoft DirectX Video Accelerator (VA) video process that should stop processing a frame. 



## -syntax

````
typedef struct _D3DDDIARG_VIDEOPROCESSENDFRAME {
  HANDLE hVideoProcess;
  HANDLE *pHandleComplete;
} D3DDDIARG_VIDEOPROCESSENDFRAME;
````


## -struct-fields

### -field hVideoProcess

A handle to the DirectX VA video process device. The user-mode display driver returns this handle in a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvideoprocessdevice.md">CreateVideoProcessDevice</a> function.


### -field pHandleComplete

This member is reserved and should be set to <b>NULL</b>. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvideoprocessdevice.md">CreateVideoProcessDevice</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_videoprocessendframe.md">VideoProcessEndFrame</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_VIDEOPROCESSENDFRAME structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

