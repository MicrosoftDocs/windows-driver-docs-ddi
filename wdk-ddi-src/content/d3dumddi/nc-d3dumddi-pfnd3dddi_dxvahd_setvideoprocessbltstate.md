---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_SETVIDEOPROCESSBLTSTATE
title: PFND3DDDI_DXVAHD_SETVIDEOPROCESSBLTSTATE
author: windows-driver-content
description: The SetVideoProcessBltState function sets the state of a bit-block transfer (bitblt) for a video processor.
old-location: display\setvideoprocessbltstate.htm
tech.root: display
ms.assetid: 6796372c-279d-427c-a2a4-9b7c99494f53
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3DDDI_DXVAHD_SETVIDEOPROCESSBLTSTATE, PFND3DDDI_DXVAHD_SETVIDEOPROCESSBLTSTATE callback, SetVideoProcessBltState, SetVideoProcessBltState callback function [Display Devices], UserModeDisplayDriver_Functions_58620a09-f079-4bd2-8eb9-ac619d83f20d.xml, d3dumddi/SetVideoProcessBltState, display.setvideoprocessbltstate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: SetVideoProcessBltState is supported beginning with the Windows 7 operating system.
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
-	SetVideoProcessBltState
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DXVAHD_SETVIDEOPROCESSBLTSTATE callback function


## -description


The <i>SetVideoProcessBltState</i> function sets the state of a bit-block transfer (bitblt) for a video processor. 


## -parameters




### -param Arg1


### -param *








*hDevice* [in]

A handle to the display device (graphics context).


*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543093">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a> structure that describes how to change the bitblt state. 


## -returns



<i>SetVideoProcessBltState</i> returns one of the following values:

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
The bitblt state is successfully set. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>SetVideoProcessBltState</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543093">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a>
 

 

