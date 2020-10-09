---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_ASSIGNSOURCEMODESET
title: DXGKDDI_VIDPN_ASSIGNSOURCEMODESET (d3dkmddi.h)
description: The pfnAssignSourceModeSet function assigns a source mode set to a particular source in a specified VidPN.
old-location: display\dxgk_vidpn_interface_pfnassignsourcemodeset.htm
ms.assetid: e1a2ca9e-9035-4656-bcb8-4ad956a8501d
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPN_ASSIGNSOURCEMODESET callback function"]
ms.keywords: DXGKDDI_VIDPN_ASSIGNSOURCEMODESET, DXGKDDI_VIDPN_ASSIGNSOURCEMODESET callback, VidPnFunctions_558924ab-3dd4-43e9-84ed-4e28feae91c5.xml, d3dkmddi/pfnAssignSourceModeSet, display.dxgk_vidpn_interface_pfnassignsourcemodeset, pfnAssignSourceModeSet, pfnAssignSourceModeSet callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_VIDPN_ASSIGNSOURCEMODESET
 - d3dkmddi/DXGKDDI_VIDPN_ASSIGNSOURCEMODESET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnAssignSourceModeSet
product:
 - Windows
---

# DXGKDDI_VIDPN_ASSIGNSOURCEMODESET callback function


## -description

The <b>pfnAssignSourceModeSet</b> function assigns a source mode set to a particular source in a specified VidPN.

## -parameters

### -param hVidPn

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a> or <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a>.

### -param VidPnSourceId

[in] An integer that identifies one of the video present sources associated with the VidPN object.

### -param hVidPnSourceModeSet

[in] A handle to the source mode set object that is to be assigned to the source identified by <i>VidPnSourceId</i>. The display miniport driver previously obtained this handle by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_createnewsourcemodeset">pfnCreateNewSourceModeSet</a>.

## -returns

The <b>pfnAssignSourceModeSet</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN|The handle supplied in hVidPn was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE|The identifier supplied in VidPnSourceId was invalid.|
|STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET|The handle supplied in hVidPnSourceModeSet was invalid.|
|STATUS_GRAPHICS_PINNED_MODE_MUST_REMAIN_IN_SET|The source mode set you are attempting to assign does not contain the mode that was already pinned on the source.|

## -remarks

VidPN source identifiers are assigned by the operating system. <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

If you obtain a handle by calling <b>pfnCreateNewSourceModeSet</b> and then pass that handle to <b>pfnAssignSourceModeSet</b>, you do not need to release  the handle by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_releasesourcemodeset">pfnReleaseSourceModeSet</a>.

If you obtain a handle by calling <b>pfnCreateNewSourceModeSet</b> and then you decide not to assign the new source mode set to a source, you must release the newly obtained handle by calling <b>pfnReleaseSourceModeSet</b>.  

<div class="alert"><b>Note</b>    The <b>pfnAssignSourceModeSet</b> function releases or does not release the source mode set object that is identified by the <i>hVidPnSourceModeSet</i> parameter depending on the reason that caused <b>pfnAssignSourceModeSet</b> to fail. <p class="note"><b>pfnAssignSourceModeSet</b> does not release the source mode set object if <b>pfnAssignSourceModeSet</b> fails with an invalid input parameter (that is, fails with the STATUS_GRAPHICS_INVALID_VIDPN, STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE, or STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET error code) because the parameters that were specified were not sufficient for the operating system to determine which mode set object to release. Such invalid parameter situations indicate a gross coding error in the driver. You can fix this error by specifying the correct VidPN handle, source identifier, or VidPN source mode set handle. 

<p class="note"><b>pfnAssignSourceModeSet</b> will release the source mode set object after successfully validating all of the input parameters if <b>pfnAssignSourceModeSet</b> fails because of one of the following reasons:

<ul>
<li>
The source mode set is empty.

</li>
<li>
The source mode set does not contain a mode that is pinned in the previous mode set, if any.

</li>
<li>
The source mode set was not created for the source that is identified by <i>VidPnSourceId</i>.

</li>
</ul>
</div>
<div> </div>
The D3DDDI_VIDEO_PRESENT_SOURCE_ID data type is defined in <i>D3dukmdt.h</i>.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNSOURCEMODESET data types are defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/index">VidPN Source Mode Set Interface</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_createnewsourcemodeset">pfnCreateNewSourceModeSet</a>