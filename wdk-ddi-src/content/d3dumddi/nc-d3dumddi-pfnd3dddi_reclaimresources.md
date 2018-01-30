---
UID: NC:d3dumddi.PFND3DDDI_RECLAIMRESOURCES
title: PFND3DDDI_RECLAIMRESOURCES
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to reclaim video memory resources that it previously offered for reuse.
old-location: display\reclaimresources.htm
old-project: display
ms.assetid: F0533DBB-CB18-4556-9871-2DF4CA719172
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.reclaimresources, ReclaimResources callback function [Display Devices], ReclaimResources, PFND3DDDI_RECLAIMRESOURCES, PFND3DDDI_RECLAIMRESOURCES, d3dumddi/ReclaimResources
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	ReclaimResources
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_RECLAIMRESOURCES callback


## -description


Called by the Microsoft Direct3D runtime to reclaim video memory resources that it  previously offered  for reuse.


## -prototype


````
PFND3DDDI_RECLAIMRESOURCES ReclaimResources;

__checkReturn HRESULT APIENTRY* ReclaimResources(
  _In_       HANDLE                     hDevice,
  _In_ const D3DDDIARG_RECLAIMRESOURCES *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *






#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_reclaimresources.md">D3DDDIARG_RECLAIMRESOURCES</a> structure that defines the video memory resources to reclaim.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_reclaimresources.md">D3DDDIARG_RECLAIMRESOURCES</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439828">ReclaimResourcesDXGI</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_offerresources.md">OfferResources</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_RECLAIMRESOURCES callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

