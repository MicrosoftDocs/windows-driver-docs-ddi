---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE
title: PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE
author: windows-driver-content
description: The SetVideoProcessStreamState function sets the stream state for a video processor.
old-location: display\setvideoprocessstreamstate.htm
tech.root: display
ms.assetid: b48fbe58-056a-4c3b-8e1e-c65515c21ee4
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE, PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE callback, SetVideoProcessStreamState, SetVideoProcessStreamState callback function [Display Devices], UserModeDisplayDriver_Functions_3860b09d-ba06-4b9e-bf6d-65e7b90135fd.xml, d3dumddi/SetVideoProcessStreamState, display.setvideoprocessstreamstate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: SetVideoProcessStreamState is supported beginning with the Windows 7 operating system.
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
-	SetVideoProcessStreamState
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE callback function


## -description


The <i>SetVideoProcessStreamState</i> function sets the stream state for a video processor. 


## -parameters




### -param Arg1


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543098">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a> structure that describes how to change the stream state. 


## -returns



The <i>SetVideoProcessStreamState</i> function returns one of the following values:

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
The stream state is successfully set. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>SetVideoProcessStreamState</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543098">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a>
 

 

