---
UID: NC:d3dumddi.PFND3DDDI_RECLAIMALLOCATIONS3CB
title: PFND3DDDI_RECLAIMALLOCATIONS3CB
author: windows-driver-content
description: pfnReclaimAllocations3Cb is called by the user mode driver to reclaim video memory allocations that were previously offered for reuse.
old-location: display\pfnreclaimallocations3cb.htm
old-project: display
ms.assetid: BA0A8BF0-39C2-4641-9952-05512B1B1662
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3DDDI_RECLAIMALLOCATIONS3CB, PFND3DDDI_RECLAIMALLOCATIONS3CB callback, d3dumddi/pfnReclaimAllocations3Cb, display.pfnreclaimallocations3cb, pfnReclaimAllocations3Cb, pfnReclaimAllocations3Cb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	pfnReclaimAllocations3Cb
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_RECLAIMALLOCATIONS3CB callback function


## -description


<b>pfnReclaimAllocations3Cb</b> is called by the user mode driver   to reclaim video memory allocations that were previously offered  for reuse.


## -parameters




### -param hDevice [in]

 A handle to the display device.


### -param *








#### - pData [in, out]

 A pointer to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt761970">D3DDDICB_RECLAIMALLOCATIONS3</a> structure that defines the allocations to reclaim. The previously used discarded array is replaced by a pResults member in this iteration.


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




<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt761970">D3DDDICB_RECLAIMALLOCATIONS3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a>
 

 

