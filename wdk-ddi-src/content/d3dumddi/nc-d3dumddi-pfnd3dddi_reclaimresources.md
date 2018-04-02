---
UID: NC:d3dumddi.PFND3DDDI_RECLAIMRESOURCES
title: PFND3DDDI_RECLAIMRESOURCES
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to reclaim video memory resources that it previously offered for reuse.
old-location: display\reclaimresources.htm
old-project: display
ms.assetid: F0533DBB-CB18-4556-9871-2DF4CA719172
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_RECLAIMRESOURCES, ReclaimResources, ReclaimResources callback function [Display Devices], d3dumddi/ReclaimResources, display.reclaimresources
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	ReclaimResources
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_RECLAIMRESOURCES callback


## -description


Called by the Microsoft Direct3D runtime to reclaim video memory resources that it  previously offered  for reuse.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451080">D3DDDIARG_RECLAIMRESOURCES</a> structure that defines the video memory resources to reclaim.


## -returns




       Returns one of the following values:

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
The video memory resources were successfully reclaimed.

This error code is returned if the driver does not need to call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a> function.

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

This error code is returned if the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a> function and that function returns <b>E_INVALIDARG</b>.

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

This error code is returned if the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a> function and that function returns <b>D3DDDIERR_DEVICEREMOVED</b>.

<div class="alert"><b>Note</b>  If this error code is returned, the driver's calling function (typically the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439828">ReclaimResourcesDXGI</a> routine) must return this error code to the  Direct3D runtime.</div>
<div> </div>
</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451080">D3DDDIARG_RECLAIMRESOURCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/68551AD7-AC0C-4138-948F-33773F02DA41">OfferResources</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439828">ReclaimResourcesDXGI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a>
 

 

