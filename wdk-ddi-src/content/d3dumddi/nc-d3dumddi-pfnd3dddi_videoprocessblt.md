---
UID: NC:d3dumddi.PFND3DDDI_VIDEOPROCESSBLT
title: PFND3DDDI_VIDEOPROCESSBLT
author: windows-driver-content
description: The VideoProcessBlt function processes a video frame by using the specified Microsoft DirectX Video Accelerator (VA) video processing device.
old-location: display\videoprocessblt.htm
old-project: display
ms.assetid: 719465dd-4547-491c-ab30-ae63bba1b72c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videoprocessblt, VideoProcessBlt callback function [Display Devices], VideoProcessBlt, PFND3DDDI_VIDEOPROCESSBLT, PFND3DDDI_VIDEOPROCESSBLT, d3dumddi/VideoProcessBlt, UserModeDisplayDriver_Functions_23e47fd3-a838-4b56-82c3-7894d2b173a1.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Vista.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	VideoProcessBlt
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_VIDEOPROCESSBLT callback


## -description


The <i>VideoProcessBlt</i> function processes a video frame by using the specified Microsoft DirectX Video Accelerator (VA) video processing device.


## -prototype


````
PFND3DDDI_VIDEOPROCESSBLT VideoProcessBlt;

__checkReturn HRESULT APIENTRY VideoProcessBlt(
  _In_       HANDLE                    hDevice,
  _In_ const D3DDDIARG_VIDEOPROCESSBLT *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *






#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_videoprocessblt.md">D3DDDIARG_VIDEOPROCESSBLT</a> structure that describes the DirectX VA video processing operation to perform.


## -returns


<i>VideoProcessBlt</i> returns one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The DirectX VA video processing operation is successfully performed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>VideoProcessBlt</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table> 



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_videoprocessblt.md">D3DDDIARG_VIDEOPROCESSBLT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_VIDEOPROCESSBLT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

