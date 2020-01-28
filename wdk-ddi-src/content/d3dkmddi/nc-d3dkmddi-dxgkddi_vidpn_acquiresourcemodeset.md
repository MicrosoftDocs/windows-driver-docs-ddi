---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_ACQUIRESOURCEMODESET
title: DXGKDDI_VIDPN_ACQUIRESOURCEMODESET (d3dkmddi.h)
description: The pfnAcquireSourceModeSet function returns a handle to a particular source mode set object that is contained by a specified VidPN object.
old-location: display\dxgk_vidpn_interface_pfnacquiresourcemodeset.htm
ms.assetid: cf19f468-86c1-4cc9-8945-e23f73a85c91
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPN_ACQUIRESOURCEMODESET, DXGKDDI_VIDPN_ACQUIRESOURCEMODESET callback, VidPnFunctions_1ef2f7d1-cdea-4b0d-a8b5-76b5013afba3.xml, d3dkmddi/pfnAcquireSourceModeSet, display.dxgk_vidpn_interface_pfnacquiresourcemodeset, pfnAcquireSourceModeSet, pfnAcquireSourceModeSet callback function [Display Devices]
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
 - "d3dkmddi/pfnAcquireSourceModeSet"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnAcquireSourceModeSet
product:
 - Windows
---

# DXGKDDI_VIDPN_ACQUIRESOURCEMODESET callback function

## -description

The <b>pfnAcquireSourceModeSet</b> function returns a handle to a particular source mode set object that is contained by a specified VidPN object.

## -parameters

### -param hVidPn

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_issupportedvidpn">DxgkDdiIsSupportedVidPn</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a>.

### -param VidPnSourceId

[in] An integer that identifies one of the video present sources associated with the VidPN object.

### -param phVidPnSourceModeSet

[out] A pointer to a variable that receives a handle to the requested source mode set object.

### -param ppVidPnSourceModeSetInterface

[out] A pointer to a variable that receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpnsourcemodeset_interface">DXGK_VIDPNSOURCEMODESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the source mode set object.

## -returns

The <b>pfnAcquireSourceModeSet</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN|The handle supplied in hVidPn was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE|The identifier supplied in VidPnSourceId was invalid.|

## -remarks

VidPN source identifiers are assigned by the operating system. <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

When you have finished using the source mode set object handle, you must release the handle by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_releasesourcemodeset">pfnReleaseSourceModeSet</a>. Source mode set objects are reference counted, so if you acquire a handle several times, you must release it that same number of times.

The lifetime of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpnsourcemodeset_interface">DXGK_VIDPNSOURCEMODESET_INTERFACE</a> structure returned in <i>ppVidPnSourceModeSetInterface</i> is owned by the operating system. Using this ownership scheme, the operating system can switch to newer implementations at run time without breaking clients of the interface.

The D3DDDI_VIDEO_PRESENT_SOURCE_ID data type is defined in <i>D3dukmdt.h</i>.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNSOURCEMODESET data types are defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">VidPN Source Mode Set Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_assigntargetmodeset">pfnAssignTargetModeSet</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_createnewsourcemodeset">pfnCreateNewSourceModeSet</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_releasetargetmodeset">pfnReleaseTargetModeSet</a>

