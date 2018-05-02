---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_CREATENEWSOURCEMODESET
title: DXGKDDI_VIDPN_CREATENEWSOURCEMODESET
author: windows-driver-content
description: The pfnCreateNewSourceModeSet function creates a new source mode set object within a specified VidPN object.
old-location: display\dxgk_vidpn_interface_pfncreatenewsourcemodeset.htm
old-project: display
ms.assetid: d46ffa49-6e75-4cd4-9d14-aa2c9fa671be
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKDDI_VIDPN_CREATENEWSOURCEMODESET, DXGKDDI_VIDPN_CREATENEWSOURCEMODESET callback, VidPnFunctions_13c4227c-f1d3-4191-a085-5ed298fe11e7.xml, d3dkmddi/pfnCreateNewSourceModeSet, display.dxgk_vidpn_interface_pfncreatenewsourcemodeset, pfnCreateNewSourceModeSet, pfnCreateNewSourceModeSet callback function [Display Devices]
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	pfnCreateNewSourceModeSet
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_VIDPN_CREATENEWSOURCEMODESET callback function


## -description


The <b>pfnCreateNewSourceModeSet</b> function creates a new source mode set object within a specified VidPN object.


## -parameters




### -param hVidPn [in]

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a>, <a href="https://msdn.microsoft.com/96e96366-6306-4d20-8752-e942f2ed4069">DxgkDdiIsSupportedVidPn</a>, or <a href="https://msdn.microsoft.com/320a77a7-d7d4-47b9-8a40-2b6e12819e4b">DxgkDdiRecommendFunctionalVidPn</a>.


### -param VidPnSourceId [in]

[in] An integer that identifies one of the video present sources associated with the VidPN object.


### -param phNewVidPnSourceModeSet [out]

[out] A pointer to a variable that receives a handle to the newly created source mode set object.


### -param ppVidPnSourceModeSetInterface [out]

[out] A pointer to a variable that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562073">DXGK_VIDPNSOURCEMODESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the source mode set object.


## -returns



The <b>pfnCreateNewSourceModeSet</b> function returns one of the following values:

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
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
The VidPN manager was unable to allocate the memory required to create the new source mode set object.

</td>
</tr>
</table>
 




## -remarks



To assign a new source mode set to a particular source in a VidPN, perform the following steps:

<ol>
<li>
Call <b>pfnCreateNewSourceModeSet</b> to get a handle to a new source mode set object. That source mode set object belongs to a particular VidPN object that you specify.

</li>
<li>
Use the functions of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562073">DXGK_VIDPNSOURCEMODESET_INTERFACE</a> interface to add modes to the source mode set object.

</li>
<li>
Call <a href="https://msdn.microsoft.com/e1a2ca9e-9035-4656-bcb8-4ad956a8501d">pfnAssignSourceModeSet</a> to assign the new source mode set to a particular source.

</li>
</ol>
If you obtain a handle by calling <b>pfnCreateNewSourceModeSet</b> and then pass that handle to <b>pfnAssignSourceModeSet</b>, you do not need to release the handle by calling <a href="https://msdn.microsoft.com/f1ee8761-f36e-4a39-a78e-95975442f7d3">pfnReleaseSourceModeSet</a>.

If you obtain a handle by calling <b>pfnCreateNewSourceModeSet</b> and then you decide not to assign the new source mode set to a source, you must release the newly obtained handle by calling <b>pfnReleaseSourceModeSet</b>.

The lifetime of the DXGK_VIDPNSOURCEMODESET_INTERFACE structure returned in <i>ppVidPnSourceModeSetInterface</i> is owned by the operating system. Using this ownership scheme, the operating system can switch to newer implementations at run time without breaking clients of the interface.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNSOURCEMODESET data types are defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570558">VidPN Source Mode Set Interface</a>



<a href="https://msdn.microsoft.com/e1a2ca9e-9035-4656-bcb8-4ad956a8501d">pfnAssignSourceModeSet</a>



<a href="https://msdn.microsoft.com/f1ee8761-f36e-4a39-a78e-95975442f7d3">pfnReleaseSourceModeSet</a>
 

 

