---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD
title: PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD
author: windows-driver-content
description: The VideoProcessBltHD function processes video input streams and composes to an output surface.
old-location: display\videoprocessblthd.htm
old-project: display
ms.assetid: 62451fc4-92cc-4553-80cc-0843cf734a62
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.videoprocessblthd, VideoProcessBltHD callback function [Display Devices], VideoProcessBltHD, PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD, PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD, d3dumddi/VideoProcessBltHD, UserModeDisplayDriver_Functions_72b2babe-fc93-4960-93d3-6bc2022227c8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: VideoProcessBltHD is supported beginning with the Windows 7 operating system.
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
-	VideoProcessBltHD
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD callback


## -description


The <i>VideoProcessBltHD</i> function processes video input streams and composes to an output surface.


## -prototype


````
PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD VideoProcessBltHD;

__checkReturn HRESULT APIENTRY VideoProcessBltHD(
  _In_       HANDLE                             hDevice,
  _In_ const D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD *pData
)
{ ... }
````


## -parameters




### -param HANDLE


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_videoprocessblthd.md">D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD</a> structure that describes the DirectX VA video processing operation to perform. 


## -returns



<i>VideoProcessBltHD</i> returns one of the following values:

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
<i>VideoProcessBltHD</i> could not allocate memory that was required for it to complete.

</td>
</tr>
</table>
 




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_videoprocessblthd.md">D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

