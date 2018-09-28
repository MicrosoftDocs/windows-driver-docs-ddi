---
UID: NC:d3dumddi.PFND3DDDI_DEPTHFILL
title: PFND3DDDI_DEPTHFILL
author: windows-driver-content
description: The DepthFill function fills a depth buffer with a pixel value that is specified in native format.
old-location: display\depthfill.htm
tech.root: display
ms.assetid: fc889cc0-d71d-4a81-8fa5-894c676ac110
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DepthFill, DepthFill callback function [Display Devices], PFND3DDDI_DEPTHFILL, PFND3DDDI_DEPTHFILL callback, UserModeDisplayDriver_Functions_4f8a5911-1ed4-439f-b629-d267161c4ea9.xml, d3dumddi/DepthFill, display.depthfill
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
-	d3dumddi.h
api_name:
-	DepthFill
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DEPTHFILL callback function


## -description


The <b>DepthFill</b> function fills a depth buffer with a pixel value that is specified in native format.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543018">D3DDDIARG_DEPTHFILL</a> structure that describes the parameters of the depth-fill operation.


## -returns



<b>DepthFill</b> returns one of the following values:

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
The depth-fill operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/fc889cc0-d71d-4a81-8fa5-894c676ac110">DepthFill</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



DirectX version 7.0 and earlier runtimes call the <b>DepthFill</b> function to fill a depth buffer (z-buffer and stencil buffer) with a pixel value that is specified in native format.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543018">D3DDDIARG_DEPTHFILL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

