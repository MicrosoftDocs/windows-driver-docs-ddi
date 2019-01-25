---
UID: NC:d3dkmddi.DXGKCB_GETCAPTUREADDRESS
title: DXGKCB_GETCAPTUREADDRESS (d3dkmddi.h)
description: The DxgkCbGetCaptureAddress function retrieves the physical address and segment identifier of a capture buffer that is associated with the given allocation handle.
old-location: display\dxgkcbgetcaptureaddress.htm
ms.assetid: f87a5a5f-20d3-48cb-93f0-114eafe7238b
ms.date: 05/10/2018
ms.keywords: DXGKCB_GETCAPTUREADDRESS, DXGKCB_GETCAPTUREADDRESS callback, DpFunctions_a8e4882c-a196-4cdf-826f-fa4cf44ba8f8.xml, DxgkCbGetCaptureAddress, DxgkCbGetCaptureAddress callback function [Display Devices], d3dkmddi/DxgkCbGetCaptureAddress, display.dxgkcbgetcaptureaddress
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
req.irql: PASSIVE_LEVEL
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
tech.root: display
req.typenames: 
---

# DXGKCB_GETCAPTUREADDRESS callback function


## -description


The <b>DxgkCbGetCaptureAddress</b> function retrieves the physical address and segment identifier of a capture buffer that is associated with the given allocation handle.


## -parameters


### -param 

*pData*

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557531">DXGKARGCB_GETCAPTUREADDRESS</a> structure that describes parameters for retrieving information about a capture buffer.


## -returns



<b>DxgkCbGetCaptureAddress</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | DxgkCbGetCaptureAddress successfully retrieved the capture buffer information. | 
| **STATUS_INVALID_PARAMETER** | The allocation handle that is specified in the hAllocation member of the [DXGKARGCB_GETCAPTUREADDRESS](https://msdn.microsoft.com/library/windows/hardware/ff557531) structure that the pData parameter pointed to was either invalid or did not represent a capture buffer. | 

 

<i>DxgkCbGetCaptureAddress</i> might also return other error codes that are defined in Ntstatus.h.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557531">DXGKARGCB_GETCAPTUREADDRESS</a>
 

 

