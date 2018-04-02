---
UID: NC:d3d10umddi.PFND3D11_1DDI_DISCARD
title: PFND3D11_1DDI_DISCARD
author: windows-driver-content
description: Discards (evicts) an allocation from video display memory. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\discard_d3d11_1_.htm
old-project: display
ms.assetid: d94234ab-712b-4449-96de-16b9e310d250
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: Discard(D3D11_1), Discard(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_DISCARD, d3d10umddi/Discard(D3D11_1), display.discard_d3d11_1_, display.pfndiscard
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
-	Discard(D3D11_1)
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_DISCARD callback


## -description


Discards (evicts) an allocation from video display memory. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.


## -parameters




### -param Arg1


### -param HandleType

A value, of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff542152">D3D11DDI_HANDLETYPE</a>, that identifies the context handle type.


### -param *hResourceOrView

A pointer to a handle to the resource or to the view that is to be discarded.


### -param *


### -param NumRects

The number of rectangles in the array that the  <i>pRects</i> parameter specifies.


#### - hDevice

A handle to the display device (graphics context).


#### - pRects [in, optional]

An optional array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structures for the rectangles in the resource view to discard. If <b>NULL</b>, the <i>Discard(D3D11_1)</i> function discards the entire surface.


## -returns



This callback function does not return a value.




## -remarks



The D3D10_DDI_RECT structure is defined as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef RECT D3D10_DDI_RECT;</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542152">D3D11DDI_HANDLETYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406443">D3D11_1DDI_DEVICEFUNCS</a>
 

 

