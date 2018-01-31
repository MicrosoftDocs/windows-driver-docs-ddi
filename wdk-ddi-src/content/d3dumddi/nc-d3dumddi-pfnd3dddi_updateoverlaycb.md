---
UID: NC:d3dumddi.PFND3DDDI_UPDATEOVERLAYCB
title: PFND3DDDI_UPDATEOVERLAYCB
author: windows-driver-content
description: The pfnUpdateOverlayCb function modifies a kernel-mode overlay object.
old-location: display\pfnupdateoverlaycb.htm
old-project: display
ms.assetid: 17f89cea-350c-43f6-a60d-32fc2d299dd7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnupdateoverlaycb, pfnUpdateOverlayCb callback function [Display Devices], pfnUpdateOverlayCb, PFND3DDDI_UPDATEOVERLAYCB, PFND3DDDI_UPDATEOVERLAYCB, d3dumddi/pfnUpdateOverlayCb, D3Druntime_Functions_9a6ce628-61ad-4c22-9fa7-aa2c83e680b6.xml
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
-	pfnUpdateOverlayCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_UPDATEOVERLAYCB callback


## -description


The <b>pfnUpdateOverlayCb</b> function modifies a kernel-mode overlay object.


## -prototype


````
PFND3DDDI_UPDATEOVERLAYCB pfnUpdateOverlayCb;

__checkReturn HRESULT APIENTRY CALLBACK pfnUpdateOverlayCb(
  _In_       HANDLE                 hDevice,
  _In_ const D3DDDICB_UPDATEOVERLAY *pData
)
{ ... }
````


## -parameters




#### - hDevice [in]

A handle to the display device (graphics context).


### -param *






#### - pData [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_updateoverlay.md">D3DDDICB_UPDATEOVERLAY</a> structure that describes how to modify the overlay.


## -returns


<b>pfnUpdateOverlayCb</b> returns one of the following values:
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
The overlay object was successfully modified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>
</td>
<td width="60%">
<b>pfnUpdateOverlayCb</b> failed because of a lack of overlay hardware or bandwidth.

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
<b>pfnUpdateOverlayCb</b> could not allocate memory that was required for it to complete.

</td>
</tr>
</table> 

This function might also return other HRESULT values.



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_updateoverlay.md">D3DDDICB_UPDATEOVERLAY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_UPDATEOVERLAYCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

