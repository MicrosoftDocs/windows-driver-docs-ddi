---
UID: NC:d3dumddi.PFND3DDDI_GETOVERLAYCOLORCONTROLS
title: PFND3DDDI_GETOVERLAYCOLORCONTROLS
author: windows-driver-content
description: The GetOverlayColorControls function retrieves color-control settings for the given overlay.
old-location: display\getoverlaycolorcontrols.htm
old-project: display
ms.assetid: 23b15bb5-4394-406b-8869-f9d1e4e2b539
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetOverlayColorControls, GetOverlayColorControls callback function [Display Devices], PFND3DDDI_GETOVERLAYCOLORCONTROLS, UserModeDisplayDriver_Functions_b50c3637-892b-4cc9-ad9a-97feeeb649fc.xml, d3dumddi/GetOverlayColorControls, display.getoverlaycolorcontrols
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
-	GetOverlayColorControls
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_GETOVERLAYCOLORCONTROLS callback


## -description


The <i>GetOverlayColorControls</i> function retrieves color-control settings for the given overlay.


## -prototype


````
PFND3DDDI_GETOVERLAYCOLORCONTROLS GetOverlayColorControls;

__checkReturn HRESULT APIENTRY GetOverlayColorControls(
  _In_    HANDLE                            hDevice,
  _Inout_ D3DDDIARG_GETOVERLAYCOLORCONTROLS *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getoverlaycolorcontrols.md">D3DDDIARG_GETOVERLAYCOLORCONTROLS</a> structure that describes parameters for retrieving an overlay's color-control settings.


## -returns



<i>GetOverlayColorControls</i> returns one of the following values:

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
The color-control settings were successfully retrieved.

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
<i>GetOverlayColorControls</i> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -remarks



The Microsoft Direct3D runtime calls the <i>GetOverlayColorControls</i> function to return the current brightness, contrast, hue, saturation, sharpness, gamma, and color-enable settings that are associated with a specific overlay. 

The runtime can also call <i>GetOverlayColorControls</i> for an overlay that is not yet visible. In this situation, when the <b>hOverlay</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getoverlaycolorcontrols.md">D3DDDIARG_GETOVERLAYCOLORCONTROLS</a> structure pointed to by <i>pData</i> is set to <b>NULL</b>, the driver should return the default color-control settings of the overlay hardware.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getoverlaycolorcontrols.md">D3DDDIARG_GETOVERLAYCOLORCONTROLS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_GETOVERLAYCOLORCONTROLS callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

