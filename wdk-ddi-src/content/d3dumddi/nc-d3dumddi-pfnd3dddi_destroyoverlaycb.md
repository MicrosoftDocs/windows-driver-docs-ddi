---
UID: NC:d3dumddi.PFND3DDDI_DESTROYOVERLAYCB
title: PFND3DDDI_DESTROYOVERLAYCB
author: windows-driver-content
description: The pfnDestroyOverlayCb function disables the overlay hardware and destroys the kernel-mode overlay object.
old-location: display\pfndestroyoverlaycb.htm
tech.root: display
ms.assetid: 9fc83bad-c183-4cba-9514-bfe1c676cba5
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3Druntime_Functions_57512079-654f-4858-bd66-984935adec15.xml, PFND3DDDI_DESTROYOVERLAYCB, PFND3DDDI_DESTROYOVERLAYCB callback, d3dumddi/pfnDestroyOverlayCb, display.pfndestroyoverlaycb, pfnDestroyOverlayCb, pfnDestroyOverlayCb callback function [Display Devices]
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
-	pfnDestroyOverlayCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DESTROYOVERLAYCB callback function


## -description


The <b>pfnDestroyOverlayCb</b> function disables the overlay hardware and destroys the kernel-mode overlay object.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544178">D3DDDICB_DESTROYOVERLAY</a> structure that contains a handle to the overlay object to be disabled.


## -returns



<b>pfnDestroyOverlayCb</b> returns one of the following values:

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
The overlay object was successfully disabled.

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
</table>
 

This function might also return other HRESULT values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544178">D3DDDICB_DESTROYOVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>
 

 

