---
UID: NC:d3dumddi.PFND3DDDI_FLIPOVERLAYCB
title: PFND3DDDI_FLIPOVERLAYCB
author: windows-driver-content
description: The pfnFlipOverlayCb function changes the allocation to display on the overlay or indicates to display the other field of the currently displaying allocation, when deinterlacing an interleaved resource.
old-location: display\pfnflipoverlaycb.htm
old-project: display
ms.assetid: 91e4876a-82c0-4e74-84c8-4b7a6abe0756
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3Druntime_Functions_68f39dc6-3dd7-4742-81c9-f23874c6c38f.xml, PFND3DDDI_FLIPOVERLAYCB, d3dumddi/pfnFlipOverlayCb, display.pfnflipoverlaycb, pfnFlipOverlayCb, pfnFlipOverlayCb callback function [Display Devices]
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
-	pfnFlipOverlayCb
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_FLIPOVERLAYCB callback


## -description


The <b>pfnFlipOverlayCb</b> function changes the allocation to display on the overlay or indicates to display the other field of the currently displaying allocation, when deinterlacing an interleaved resource.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544198">D3DDDICB_FLIPOVERLAY</a> structure that describes how to change the display on the overlay.


## -returns



<b>pfnFlipOverlayCb</b> returns one of the following values:

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
The display on the overlay object was successfully changed.

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
<b>pfnFlipOverlayCb</b> could not allocate memory that was required for it to complete.

</td>
</tr>
</table>
 

This function might also return other HRESULT values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544198">D3DDDICB_FLIPOVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>
 

 

