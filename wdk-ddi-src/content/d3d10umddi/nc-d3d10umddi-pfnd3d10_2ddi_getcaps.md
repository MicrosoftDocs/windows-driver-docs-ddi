---
UID: NC:d3d10umddi.PFND3D10_2DDI_GETCAPS
title: PFND3D10_2DDI_GETCAPS
author: windows-driver-content
description: The GetCaps(D3D10_2) function queries for capabilities of the graphics adapter.
old-location: display\getcaps_d3d10_2_.htm
ms.assetid: 83cd5f34-5f12-4ead-ad33-366fc3c6e804
ms.date: 05/10/2018
ms.keywords: GetCaps, GetCaps callback function [Display Devices], PFND3D10_2DDI_GETCAPS, PFND3D10_2DDI_GETCAPS callback, UserModeDisplayDriverDx11_Functions_b0f0ebe4-205d-4eb5-ad35-e91dbcb21a1c.xml, d3d10umddi/GetCaps, display.getcaps_d3d10_2_
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: GetCaps(D3D10_2) is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
api_name:
-	GetCaps
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10_2DDI_GETCAPS callback function


## -description


The <i>GetCaps(D3D10_2)</i> function queries for capabilities of the graphics adapter. 


## -parameters




### -param Arg1

*hAdapter* [in]

A handle that identifies the graphics adapter.

### -param *

*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541887">D3D10_2DDIARG_GETCAPS</a> structure that describes the capabilities to retrieve.


## -returns



<i>GetCaps(D3D10_2)</i> returns one of the following values:

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
The capabilities are successfully retrieved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>GetCaps(D3D10_2)</i> could not allocate memory that is required for it to complete.

</td>
</tr>
</table>
 




## -remarks



The data that is returned by the <i>GetCaps(D3D10_2)</i> function in the <b>pData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541887">D3D10_2DDIARG_GETCAPS</a> structure depends on the type of data that is requested (that is, the data depends on the <b>Type</b> member of D3D10_2DDIARG_GETCAPS and sometimes on the <b>pInfo</b> member). 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541887">D3D10_2DDIARG_GETCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541900">D3D10_2DDI_ADAPTERFUNCS</a>
 

 

