---
UID: NC:d3dumddi.PFND3DDDI_SETOVERLAYCOLORCONTROLS
title: PFND3DDDI_SETOVERLAYCOLORCONTROLS
author: windows-driver-content
description: The SetOverlayColorControls function changes color-control settings for the given overlay.
old-location: display\setoverlaycolorcontrols.htm
old-project: display
ms.assetid: c2723c57-44eb-4866-9381-a3a341996989
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3DDDI_SETOVERLAYCOLORCONTROLS, PFND3DDDI_SETOVERLAYCOLORCONTROLS callback, SetOverlayColorControls, SetOverlayColorControls callback function [Display Devices], UserModeDisplayDriver_Functions_3164b9ba-d03c-473d-b067-2fc5b2756594.xml, d3dumddi/SetOverlayColorControls, display.setoverlaycolorcontrols
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
-	SetOverlayColorControls
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETOVERLAYCOLORCONTROLS callback function


## -description


The <i>SetOverlayColorControls</i> function changes color-control settings for the given overlay.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543323">D3DDDIARG_SETOVERLAYCOLORCONTROLS</a> structure that describes parameters for changing an overlay's color-control settings.


## -returns



<i>SetOverlayColorControls</i> returns one of the following values:

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
The color-control settings were successfully changed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>SetOverlayColorControls</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



The Microsoft Direct3D runtime calls the <i>SetOverlayColorControls</i> function to change the brightness, contrast, hue, saturation, sharpness, gamma, and color-enable settings that are associated with a specific overlay. 

The runtime can also call <i>SetOverlayColorControls</i> for an overlay that is not yet visible. In this situation, when the <b>hOverlay</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543323">D3DDDIARG_SETOVERLAYCOLORCONTROLS</a> structure pointed to by <i>pData</i> is set to <b>NULL</b>, the driver should store the supplied color-control settings and use them when an overlay that references the specified resource is created.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543323">D3DDDIARG_SETOVERLAYCOLORCONTROLS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

