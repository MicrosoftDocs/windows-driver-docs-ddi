---
UID: NC:d3dkmddi.DXGKCB_GETCAPTUREADDRESS
title: DXGKCB_GETCAPTUREADDRESS
author: windows-driver-content
description: The DxgkCbGetCaptureAddress function retrieves the physical address and segment identifier of a capture buffer that is associated with the given allocation handle.
old-location: display\dxgkcbgetcaptureaddress.htm
old-project: display
ms.assetid: f87a5a5f-20d3-48cb-93f0-114eafe7238b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKCB_GETCAPTUREADDRESS, DpFunctions_a8e4882c-a196-4cdf-826f-fa4cf44ba8f8.xml, DxgkCbGetCaptureAddress, DxgkCbGetCaptureAddress callback function [Display Devices], d3dkmddi/DxgkCbGetCaptureAddress, display.dxgkcbgetcaptureaddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkCbGetCaptureAddress
product:
- Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKCB_GETCAPTUREADDRESS callback


## -description


The <b>DxgkCbGetCaptureAddress</b> function retrieves the physical address and segment identifier of a capture buffer that is associated with the given allocation handle.


## -parameters










#### - pData [in, out]

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557531">DXGKARGCB_GETCAPTUREADDRESS</a> structure that describes parameters for retrieving information about a capture buffer.


## -returns



<b>DxgkCbGetCaptureAddress</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
<b>DxgkCbGetCaptureAddress</b> successfully retrieved the capture buffer information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The allocation handle that is specified in the <b>hAllocation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557531">DXGKARGCB_GETCAPTUREADDRESS</a> structure that the <i>pData</i> parameter pointed to was either invalid or did not represent a capture buffer. 

</td>
</tr>
</table>
 

<i>DxgkCbGetCaptureAddress</i> might also return other error codes that are defined in Ntstatus.h.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557531">DXGKARGCB_GETCAPTUREADDRESS</a>
 

 

