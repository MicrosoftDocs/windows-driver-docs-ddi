---
UID: NC:d3dumddi.PFND3DDDI_RECLAIMALLOCATIONS3CB
title: PFND3DDDI_RECLAIMALLOCATIONS3CB
author: windows-driver-content
description: pfnReclaimAllocations3Cb is called by the user mode driver to reclaim video memory allocations that were previously offered for reuse.
old-location: display\pfnreclaimallocations3cb.htm
old-project: display
ms.assetid: BA0A8BF0-39C2-4641-9952-05512B1B1662
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnreclaimallocations3cb, pfnReclaimAllocations3Cb callback function [Display Devices], pfnReclaimAllocations3Cb, PFND3DDDI_RECLAIMALLOCATIONS3CB, PFND3DDDI_RECLAIMALLOCATIONS3CB, d3dumddi/pfnReclaimAllocations3Cb
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	pfnReclaimAllocations3Cb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_RECLAIMALLOCATIONS3CB callback


## -description


<b>pfnReclaimAllocations3Cb</b> is called by the user mode driver   to reclaim video memory allocations that were previously offered  for reuse.


## -prototype


````
PFND3DDDI_RECLAIMALLOCATIONS3CB pfnReclaimAllocations3Cb;

_Check_return_ HRESULT CALLBACK pfnReclaimAllocations3Cb(
  _In_    HANDLE                       hDevice,
  _Inout_ D3DDDICB_RECLAIMALLOCATIONS3 *pData
)
{ ... }
````


## -parameters




#### - hDevice [in]

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

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>

<a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt761970">D3DDDICB_RECLAIMALLOCATIONS3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_RECLAIMALLOCATIONS3CB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

