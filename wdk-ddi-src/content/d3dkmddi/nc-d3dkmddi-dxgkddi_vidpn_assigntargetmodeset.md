---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_ASSIGNTARGETMODESET
title: DXGKDDI_VIDPN_ASSIGNTARGETMODESET (d3dkmddi.h)
description: The pfnAssignTargetModeSet function assigns a target mode set to a particular target in a specified VidPN.
old-location: display\dxgk_vidpn_interface_pfnassigntargetmodeset.htm
ms.assetid: 846c6dd5-d4f8-4835-83a2-994725deaf36
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPN_ASSIGNTARGETMODESET callback function"]
ms.keywords: DXGKDDI_VIDPN_ASSIGNTARGETMODESET, DXGKDDI_VIDPN_ASSIGNTARGETMODESET callback, VidPnFunctions_7051492a-0560-4898-8532-60e66ebcb001.xml, d3dkmddi/pfnAssignTargetModeSet, display.dxgk_vidpn_interface_pfnassigntargetmodeset, pfnAssignTargetModeSet, pfnAssignTargetModeSet callback function [Display Devices]
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
 - "d3dkmddi/pfnAssignTargetModeSet"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnAssignTargetModeSet
product:
 - Windows
---

# DXGKDDI_VIDPN_ASSIGNTARGETMODESET callback function

## -description

The <b>pfnAssignTargetModeSet</b> function assigns a target mode set to a particular target in a specified VidPN.

## -parameters

### -param hVidPn

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a>.

### -param VidPnTargetId

[in] An integer that identifies one of the video present targets associated with the VidPN object.

### -param hVidPnTargetModeSet

[in] A handle to the target mode set object that is to be assigned to the target identified by <i>VidPnTargetId</i>. The display miniport driver previously obtained this handle by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_createnewtargetmodeset">pfnCreateNewTargetModeSet</a>.

## -returns

The <b>pfnAssignTargetModeSet</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN|The handle supplied in hVidPn was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET|The identifier supplied in VidPnTargetId was invalid.|
|STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET|The handle supplied in hVidPnTargetModeSet was invalid.|
|STATUS_GRAPHICS_PINNED_MODE_MUST_REMAIN_IN_SET|The target mode set you are attempting to assign does not contain the mode that was already pinned on the target.|

## -remarks

VidPN target identifiers are assigned by the display miniport driver. <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>, implemented by the display miniport driver, returns an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

If you obtain a handle by calling <b>pfnCreateNewTargetModeSet</b> and then pass that handle to <b>pfnAssignTargetModeSet</b>, you do not need to release the handle by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_releasetargetmodeset">pfnReleaseTargetModeSet</a>.

If you obtain a handle by calling <b>pfnCreateNewTargetModeSet</b> and then you decide not to assign the new target mode set to a target, you must release the newly obtained handle by calling <b>pfnReleaseTargetModeSet</b>.  

<div class="alert"><b>Note</b>    The <b>pfnAssignTargetModeSet</b> function releases or does not release the target mode set object that is identified by the <i>hVidPnTargetModeSet</i> parameter depending on the reason that caused <b>pfnAssignTargetModeSet</b> to fail. <p class="note"><b>pfnAssignTargetModeSet</b> does not release the target mode set object if <b>pfnAssignTargetModeSet</b> fails with an invalid input parameter (that is, fails with the STATUS_GRAPHICS_INVALID_VIDPN, STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET, or STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET error code) because the parameters that were specified were not sufficient for the operating system to determine which mode set object to release. Such invalid parameter situations indicate a gross coding error in the driver. You can fix this error by specifying the correct VidPN handle, target identifier, or VidPN target mode set handle. 

<p class="note"><b>pfnAssignTargetModeSet</b> will release the target mode set object after successfully validating all of the input parameters if <b>pfnAssignTargetModeSet</b> fails because of one of the following reasons:

<ul>
<li>
The target mode set is empty.

</li>
<li>
The target mode set does not contain a mode that is pinned in the previous mode set, if any.

</li>
<li>
The target mode set was not created for the target that is identified by <i>VidPnTargetId</i>.

</li>
</ul>
</div>
<div> </div>
The D3DDDI_VIDEO_PRESENT_TARGET_ID data type is defined in <i>D3dukmdt.h</i>.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNTARGETMODESET data types are defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">VidPN Target Mode Set Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_createnewtargetmodeset">pfnCreateNewTargetModeSet</a>

