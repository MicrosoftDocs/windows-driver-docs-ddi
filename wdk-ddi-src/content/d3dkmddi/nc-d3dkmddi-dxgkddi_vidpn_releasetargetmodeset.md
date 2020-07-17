---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_RELEASETARGETMODESET
title: DXGKDDI_VIDPN_RELEASETARGETMODESET (d3dkmddi.h)
description: The pfnReleaseTargetModeSet function releases a handle to a target mode set object.
old-location: display\dxgk_vidpn_interface_pfnreleasetargetmodeset.htm
ms.assetid: bd369651-57d4-406f-ba51-9632362de15d
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPN_RELEASETARGETMODESET callback function"]
ms.keywords: DXGKDDI_VIDPN_RELEASETARGETMODESET, DXGKDDI_VIDPN_RELEASETARGETMODESET callback, VidPnFunctions_c1609a38-53ff-49e0-a11a-26ceb5d64cdb.xml, d3dkmddi/pfnReleaseTargetModeSet, display.dxgk_vidpn_interface_pfnreleasetargetmodeset, pfnReleaseTargetModeSet, pfnReleaseTargetModeSet callback function [Display Devices]
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
 - "d3dkmddi/pfnReleaseTargetModeSet"
 - "pfnReleaseTargetModeSet"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnReleaseTargetModeSet
product:
 - Windows
---

# DXGKDDI_VIDPN_RELEASETARGETMODESET callback function

## -description

The <b>pfnReleaseTargetModeSet</b> function releases a handle to a target mode set object.

## -parameters

### -param hVidPn

[in] A handle to a VidPN object that contains the target mode set object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_issupportedvidpn">DxgkDdiIsSupportedVidPn</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a>.

### -param hVidPnTargetModeSet

[in] The handle to be released.

## -returns

The <b>pfnReleaseTargetModeSet</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN|The handle supplied in hVidPn was invalid.|
|STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET|The handle supplied in hVidPnTargetModeSet was invalid.|
|STATUS_GRAPHICS_RESOURCES_NOT_RELATED|The VidPN identified by hVidPn does not contain the target mode set identified by hVidPnTargetModeSet.|

## -remarks

When you have finished using a handle that you obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset">pfnAcquireTargetModeSet</a>, you must release the handle by calling <b>pfnReleaseTargetModeSet</b>.

If you obtain a handle by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_createnewtargetmodeset">pfnCreateNewTargetModeSet</a> and then pass that handle to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_assigntargetmodeset">pfnAssignTargetModeSet</a>, you do not need to release the handle.

If you obtain a handle by calling <b>pfnCreateNewTargetModeSet</b> and then you decide not to assign the new source mode set to a source, you must release the newly obtained handle by calling <b>pfnReleaseTargetModeSet</b>.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNTARGETMODESET data types are defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset">pfnAcquireTargetModeSet</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_createnewtargetmodeset">pfnCreateNewTargetModeSet</a>

