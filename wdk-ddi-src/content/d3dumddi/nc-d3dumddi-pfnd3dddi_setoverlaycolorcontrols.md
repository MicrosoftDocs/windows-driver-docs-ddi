---
UID: NC:d3dumddi.PFND3DDDI_SETOVERLAYCOLORCONTROLS
title: PFND3DDDI_SETOVERLAYCOLORCONTROLS
author: windows-driver-content
description: The SetOverlayColorControls function changes color-control settings for the given overlay.
old-location: display\setoverlaycolorcontrols.htm
old-project: display
ms.assetid: c2723c57-44eb-4866-9381-a3a341996989
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.setoverlaycolorcontrols, SetOverlayColorControls callback function [Display Devices], SetOverlayColorControls, PFND3DDDI_SETOVERLAYCOLORCONTROLS, PFND3DDDI_SETOVERLAYCOLORCONTROLS, d3dumddi/SetOverlayColorControls, UserModeDisplayDriver_Functions_3164b9ba-d03c-473d-b067-2fc5b2756594.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	SetOverlayColorControls
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETOVERLAYCOLORCONTROLS callback


## -description


The <i>SetOverlayColorControls</i> function changes color-control settings for the given overlay.


## -prototype


````
PFND3DDDI_SETOVERLAYCOLORCONTROLS SetOverlayColorControls;

__checkReturn HRESULT APIENTRY SetOverlayColorControls(
  _In_       HANDLE                            hDevice,
  _In_ const D3DDDIARG_SETOVERLAYCOLORCONTROLS *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *






#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setoverlaycolorcontrols.md">D3DDDIARG_SETOVERLAYCOLORCONTROLS</a> structure that describes parameters for changing an overlay's color-control settings.


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

The runtime can also call <i>SetOverlayColorControls</i> for an overlay that is not yet visible. In this situation, when the <b>hOverlay</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setoverlaycolorcontrols.md">D3DDDIARG_SETOVERLAYCOLORCONTROLS</a> structure pointed to by <i>pData</i> is set to <b>NULL</b>, the driver should store the supplied color-control settings and use them when an overlay that references the specified resource is created.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setoverlaycolorcontrols.md">D3DDDIARG_SETOVERLAYCOLORCONTROLS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETOVERLAYCOLORCONTROLS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

