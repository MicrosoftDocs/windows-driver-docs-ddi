---
UID: NC:d3dumddi.PFND3DDDI_RECLAIMALLOCATIONS2CB
title: PFND3DDDI_RECLAIMALLOCATIONS2CB
author: windows-driver-content
description: pfnReclaimAllocations2Cb is called by the user mode driver to reclaim video memory allocations that were previously offered for reuse.
old-location: display\pfnreclaimallocations2cb.htm
tech.root: display
ms.assetid: 1D3439BA-AB3D-4D94-B4C8-91BE9B3349A1
ms.date: 5/10/2018
ms.keywords: PFND3DDDI_RECLAIMALLOCATIONS2CB, d3dumddi/pfnReclaimAllocations2Cb, display.pfnreclaimallocations2cb, pfnReclaimAllocations2Cb, pfnReclaimAllocations2Cb callback, pfnReclaimAllocations2Cb callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	pfnReclaimAllocations2Cb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_RECLAIMALLOCATIONS2CB callback function


## -description


<b>pfnReclaimAllocations2Cb</b> is called by the user mode driver   to reclaim video memory allocations that were previously offered  for reuse.


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *








*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906764">D3DDDICB_RECLAIMALLOCATIONS2</a> structure that defines the allocations to reclaim.


## -returns




      Returns one of the following values.

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
The allocations were successfully reclaimed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was supplied.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">
The video memory manager or display miniport driver could not complete the operation because either a Plug and Play (PnP) Stop event or a Timeout Detection and Recovery (TDR) event occurred.

<div class="alert"><b>Note</b>  If this error code is returned, the driver's calling function (typically the <a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a> routine) must return this error code to the  Direct3D runtime.</div>
<div> </div>
</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906764">D3DDDICB_RECLAIMALLOCATIONS2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a>
 

 

