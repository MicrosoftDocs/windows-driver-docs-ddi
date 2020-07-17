---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_ACQUIREFIRSTMODEINFO
title: DXGKDDI_VIDPNTARGETMODESET_ACQUIREFIRSTMODEINFO (d3dkmddi.h)
description: The pfnAcquireFirstModeInfo function returns a descriptor of the first mode in a specified VidPN target mode set.
old-location: display\dxgk_vidpntargetmodeset_interface_pfnacquirefirstmodeinfo.htm
ms.assetid: 64a1a8f4-afbc-4337-b809-9346c1171e0b
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPNTARGETMODESET_ACQUIREFIRSTMODEINFO callback function"]
ms.keywords: DXGKDDI_VIDPNTARGETMODESET_ACQUIREFIRSTMODEINFO, DXGKDDI_VIDPNTARGETMODESET_ACQUIREFIRSTMODEINFO callback, VidPnFunctions_b0ab2e5f-a78b-499a-9dac-528c5c847f02.xml, d3dkmddi/pfnAcquireFirstModeInfo, display.dxgk_vidpntargetmodeset_interface_pfnacquirefirstmodeinfo, pfnAcquireFirstModeInfo, pfnAcquireFirstModeInfo callback function [Display Devices]
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
 - "d3dkmddi/pfnAcquireFirstModeInfo"
 - "pfnAcquireFirstModeInfo"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnAcquireFirstModeInfo
product:
 - Windows
---

# DXGKDDI_VIDPNTARGETMODESET_ACQUIREFIRSTMODEINFO callback function

## -description

The <b>pfnAcquireFirstModeInfo</b> function returns a descriptor of the first mode in a specified VidPN target mode set.

## -parameters

### -param hVidPnTargetModeSet

[in] A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset">pfnAcquireTargetModeSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param ppFirstVidPnTargetModeInfo

[out] A pointer to a variable that receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a> structure. The structure contains a variety of information about the target mode, including its ID and video signal characteristics.

## -returns

The <b>pfnAcquireFirstModeInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET|The handle supplied in hVidPnTargetModeSet was invalid.|

## -remarks

When you have finished using the D3DKMDT_VIDPN_TARGET_MODE structure, you must release the structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_releasemodeinfo">pfnReleaseModeInfo</a>.

You can enumerate all the modes that belong to a VidPN target mode set object by calling <b>pfnAcquireFirstModeInfo</b> and then making a sequence of calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirenextmodeinfo">pfnAcquireNextModeInfo</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirenextmodeinfo">pfnAcquireNextModeInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_releasemodeinfo">pfnReleaseModeInfo</a>

