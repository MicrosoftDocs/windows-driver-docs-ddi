---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_ACQUIRETARGETMODESET
title: DXGKDDI_VIDPN_ACQUIRETARGETMODESET (d3dkmddi.h)
description: The pfnAcquireTargetModeSet function returns a handle to a particular target mode set object that is contained by a specified VidPN object.
old-location: display\dxgk_vidpn_interface_pfnacquiretargetmodeset.htm
ms.assetid: 1b91c472-21eb-4aa8-91e3-c9eb70556d9f
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPN_ACQUIRETARGETMODESET, DXGKDDI_VIDPN_ACQUIRETARGETMODESET callback, VidPnFunctions_e7b058c8-0f02-4456-8938-9182a35826f9.xml, d3dkmddi/pfnAcquireTargetModeSet, display.dxgk_vidpn_interface_pfnacquiretargetmodeset, pfnAcquireTargetModeSet, pfnAcquireTargetModeSet callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/pfnAcquireTargetModeSet"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnAcquireTargetModeSet
product:
 - Windows
---

# DXGKDDI_VIDPN_ACQUIRETARGETMODESET callback function

## -description

The <b>pfnAcquireTargetModeSet</b> function returns a handle to a particular target mode set object that is contained by a specified VidPN object.

## -parameters

### -param hVidPn

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_issupportedvidpn">DxgkDdiIsSupportedVidPn</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a>.

### -param VidPnTargetId

[in] An integer that identifies one of the video present targets associated with the VidPN object.

### -param phVidPnTargetModeSet

[out] A pointer to a variable that receives a handle to the requested target mode set object.

### -param ppVidPnTargetModeSetInterface

[out] A pointer to a variable that receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpntargetmodeset_interface">DXGK_VIDPNTARGETMODESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the target mode set object.

## -returns

The <b>pfnAcquireTargetModeSet</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN|The handle supplied in hVidPn was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET|The identifier supplied in VidPnTargetId was invalid.|

## -remarks

VidPN target identifiers are assigned by the display miniport driver. <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>, implemented by the display miniport driver, returns an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

When you have finished using the target mode set object handle, you must release the handle by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_releasetargetmodeset">pfnReleaseTargetModeSet</a>. Target mode set objects are reference counted, so if you acquire a handle several times, you must release it that same number of times.

The lifetime of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpntargetmodeset_interface">DXGK_VIDPNTARGETMODESET_INTERFACE</a> structure returned in <i>ppVidPnTargetModeSetInterface</i> is owned by the operating system. Using this ownership scheme, the operating system can switch to newer implementations at run time without breaking clients of the interface.

The D3DDDI_VIDEO_PRESENT_TARGET_ID data type is defined in <i>D3dukmdt.h</i>.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNTARGETMODESET data types are defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">VidPN Target Mode Set Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_assigntargetmodeset">pfnAssignTargetModeSet</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_createnewtargetmodeset">pfnCreateNewTargetModeSet</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_releasetargetmodeset">pfnReleaseTargetModeSet</a>

