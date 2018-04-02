---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEOPROCESSOR
title: PFND3D11_1DDI_CREATEVIDEOPROCESSOR
author: windows-driver-content
description: Creates a video processor object.
old-location: display\createvideoprocessor1.htm
old-project: display
ms.assetid: 741045a2-0a91-490a-907d-5f4900a4a0ae
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CreateVideoProcessor, CreateVideoProcessor callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEOPROCESSOR, d3d10umddi/CreateVideoProcessor, display.createvideoprocessor1, display.pfncreatevideoprocessor1
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
-	CreateVideoProcessor
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CREATEVIDEOPROCESSOR callback


## -description


Creates a video processor object.


## -parameters




### -param Arg1


### -param *


### -param Arg2


### -param Arg3








#### - hDevice [in]

A handle to the display device (graphics context).




#### - hRTVideoProcessor [in]

A handle to the video processor object that the driver should use when it calls back into the Direct3D runtime.


#### - hVideoProcessor [in]

A handle to the driver's private data for the video processor object. For more information, see the Remarks section.


#### - pCreateData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406314">D3D11_1DDIARG_CREATEVIDEOPROCESSOR</a> structure. This structure specifies the attributes of the video processor object to be created.


## -returns



<b>CreateVideoProcessor</b> returns one of the following values:

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
The video processor object was created successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was removed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.

</td>
</tr>
</table>
 




## -remarks



The <i>CreateVideoProcessor</i> function creates a video processor object that contains specific capabilities and state.  Multiple video processor objects can exist at the same time, each with its own unique state.

The Direct3D runtime calls <i>CreateVideoProcessor</i> after it has called the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451614">CalcPrivateVideoProcessorSize</a>   to determine the size in bytes for the private data that the driver requires for the video processor object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video processor object.

When the runtime  calls <i>CreateVideoProcessor</i>, it passes the handle to the private data memory in the <i>hProcessor</i> parameter. This handle is actually a pointer to the memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451614">CalcPrivateVideoProcessorSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406314">D3D11_1DDIARG_CREATEVIDEOPROCESSOR</a>
 

 

