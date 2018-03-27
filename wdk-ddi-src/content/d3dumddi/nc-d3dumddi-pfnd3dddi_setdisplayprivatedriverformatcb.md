---
UID: NC:d3dumddi.PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB
title: PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB
author: windows-driver-content
description: The pfnSetDisplayPrivateDriverFormatCb function changes the private-format attribute of a video present source.
old-location: display\pfnsetdisplayprivatedriverformatcb.htm
old-project: display
ms.assetid: 499e6de7-67cc-4834-bcec-4f3907b180f7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3Druntime_Functions_36bd86e3-96bb-4c68-85a1-a678a54daed4.xml, PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB, d3dumddi/pfnSetDisplayPrivateDriverFormatCb, display.pfnsetdisplayprivatedriverformatcb, pfnSetDisplayPrivateDriverFormatCb, pfnSetDisplayPrivateDriverFormatCb callback function [Display Devices]
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
-	pfnSetDisplayPrivateDriverFormatCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB callback


## -description


The <b>pfnSetDisplayPrivateDriverFormatCb</b> function changes the private-format attribute of a video present source.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544261">D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT</a> structure that describes how to format a video present source. 


## -returns



<b>pfnSetDisplayPrivateDriverFormatCb</b> returns one of the following values:

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
The video present source was successfully changed.

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
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
<b>pfnSetDisplayPrivateDriverFormatCb</b> could not change the private-format attribute of the video present source. 

</td>
</tr>
</table>
 

This function might also return other HRESULT values.






## -remarks



Changing the private-format attribute of a video present source is useful to accommodate a full-screen DirectX application that creates its flipping change when the shared GDI primary surface is in a non-optimal private format for the full-screen DirectX application. For example, suppose the display miniport driver always creates the GDI shared primary surface as un-swizzled. However, for performance reasons, the user-mode display driver requires that all the surfaces in a full-screen flipping chain are swizzled. The user-mode display driver could then create the back buffers as swizzled and call <b>pfnSetDisplayPrivateDriverFormatCb</b> to change the shared GDI primary surface to swizzled.

If the call to <b>pfnSetDisplayPrivateDriverFormatCb</b> fails, the user-mode display driver should continue without changing the private-format attribute of the video present source. In the preceding example, the driver can either leave the shared primary as un-swizzled and have the back buffers swizzled or the driver can change the back buffers to the un-swizzled format.

If the user-mode display driver receives the D3DDDIERR_INCOMPATIBLEPRIVATEFORMAT error from a call to the <a href="https://msdn.microsoft.com/a1f58757-809d-4351-8b1a-fd4420981c24">pfnSetDisplayModeCb</a> function, the driver can do one of the following:

<ul>
<li>
Change the private-format attribute of the primary surface and call <b>pfnSetDisplayModeCb</b> again.

</li>
<li>
Call <b>pfnSetDisplayPrivateDriverFormatCb</b> and attempt to change the private-format attribute of the video present source. The driver can then call <b>pfnSetDisplayModeCb</b> again. 

</li>
</ul>
The user-mode display driver can call <b>pfnSetDisplayPrivateDriverFormatCb</b> only if the <b>Version</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a> structure was set to greater than seven when the display device (specified by the <i>hDevice</i> parameter) was created in a call to the driver's <a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a> function. 




## -see-also




<a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544261">D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/a1f58757-809d-4351-8b1a-fd4420981c24">pfnSetDisplayModeCb</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

