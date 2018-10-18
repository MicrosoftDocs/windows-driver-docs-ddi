---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_ACQUIRESOURCEMODESET
title: DXGKDDI_VIDPN_ACQUIRESOURCEMODESET
author: windows-driver-content
description: The pfnAcquireSourceModeSet function returns a handle to a particular source mode set object that is contained by a specified VidPN object.
old-location: display\dxgk_vidpn_interface_pfnacquiresourcemodeset.htm
ms.assetid: cf19f468-86c1-4cc9-8945-e23f73a85c91
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPN_ACQUIRESOURCEMODESET, DXGKDDI_VIDPN_ACQUIRESOURCEMODESET callback, VidPnFunctions_1ef2f7d1-cdea-4b0d-a8b5-76b5013afba3.xml, d3dkmddi/pfnAcquireSourceModeSet, display.dxgk_vidpn_interface_pfnacquiresourcemodeset, pfnAcquireSourceModeSet, pfnAcquireSourceModeSet callback function [Display Devices]
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
-	pfnAcquireSourceModeSet
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPN_ACQUIRESOURCEMODESET callback function


## -description


The <b>pfnAcquireSourceModeSet</b> function returns a handle to a particular source mode set object that is contained by a specified VidPN object.


## -parameters




### -param hVidPn [in]

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a>, <a href="https://msdn.microsoft.com/96e96366-6306-4d20-8752-e942f2ed4069">DxgkDdiIsSupportedVidPn</a>, or <a href="https://msdn.microsoft.com/320a77a7-d7d4-47b9-8a40-2b6e12819e4b">DxgkDdiRecommendFunctionalVidPn</a>.


### -param VidPnSourceId [in]

[in] An integer that identifies one of the video present sources associated with the VidPN object.


### -param phVidPnSourceModeSet [out]

[out] A pointer to a variable that receives a handle to the requested source mode set object.


### -param ppVidPnSourceModeSetInterface [out]

[out] A pointer to a variable that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562073">DXGK_VIDPNSOURCEMODESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the source mode set object.


## -returns



The <b>pfnAcquireSourceModeSet</b> function returns one of the following values:

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
The function succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPn</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE</b></dt>
</dl>
</td>
<td width="60%">
The identifier supplied in <i>VidPnSourceId</i> was invalid.

</td>
</tr>
</table>
 




## -remarks



VidPN source identifiers are assigned by the operating system. <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

When you have finished using the source mode set object handle, you must release the handle by calling <a href="https://msdn.microsoft.com/f1ee8761-f36e-4a39-a78e-95975442f7d3">pfnReleaseSourceModeSet</a>. Source mode set objects are reference counted, so if you acquire a handle several times, you must release it that same number of times.

The lifetime of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562073">DXGK_VIDPNSOURCEMODESET_INTERFACE</a> structure returned in <i>ppVidPnSourceModeSetInterface</i> is owned by the operating system. Using this ownership scheme, the operating system can switch to newer implementations at run time without breaking clients of the interface.

The D3DDDI_VIDEO_PRESENT_SOURCE_ID data type is defined in <i>D3dukmdt.h</i>.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNSOURCEMODESET data types are defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570558">VidPN Source Mode Set Interface</a>



<a href="https://msdn.microsoft.com/846c6dd5-d4f8-4835-83a2-994725deaf36">pfnAssignTargetModeSet</a>



<a href="https://msdn.microsoft.com/d46ffa49-6e75-4cd4-9d14-aa2c9fa671be">pfnCreateNewSourceModeSet</a>



<a href="https://msdn.microsoft.com/bd369651-57d4-406f-ba51-9632362de15d">pfnReleaseTargetModeSet</a>
 

 

