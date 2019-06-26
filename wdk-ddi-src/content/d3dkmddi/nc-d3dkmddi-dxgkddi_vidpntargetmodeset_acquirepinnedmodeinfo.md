---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_ACQUIREPINNEDMODEINFO
title: DXGKDDI_VIDPNTARGETMODESET_ACQUIREPINNEDMODEINFO (d3dkmddi.h)
description: The pfnAcquirePinnedModeInfo function returns a descriptor of the pinned mode in a specified VidPN target mode set.
old-location: display\dxgk_vidpntargetmodeset_interface_pfnacquirepinnedmodeinfo.htm
ms.assetid: 0a321ee2-f246-498d-b658-a01e275644be
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNTARGETMODESET_ACQUIREPINNEDMODEINFO, DXGKDDI_VIDPNTARGETMODESET_ACQUIREPINNEDMODEINFO callback, VidPnFunctions_81cb0000-6d1d-448f-8e4a-ca5df30d97ea.xml, d3dkmddi/pfnAcquirePinnedModeInfo, display.dxgk_vidpntargetmodeset_interface_pfnacquirepinnedmodeinfo, pfnAcquirePinnedModeInfo, pfnAcquirePinnedModeInfo callback function [Display Devices]
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- pfnAcquirePinnedModeInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNTARGETMODESET_ACQUIREPINNEDMODEINFO callback function


## -description


The <b>pfnAcquirePinnedModeInfo</b> function returns a descriptor of the pinned mode in a specified VidPN target mode set.


## -parameters




### -param hVidPnTargetModeSet [in]

[in] A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset">pfnAcquireTargetModeSet</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.


### -param ppPinnedVidPnTargetModeInfo [out]

[out] A pointer to a variable that receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a> structure. The structure contains a variety of information about the pinned mode, including its ID and video signal characteristics. If the target mode set identified by <i>hVidPnTargetModeSet</i> has no pinned mode, then this variable receives a <b>NULL</b> pointer.


## -returns



The <b>pfnAcquirePinnedModeInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded by doing one of the following:<br/>1. Setting ppPinnedVidPnTargetModeInfo to the address of D3DKMDT_VIDPN_TARGET_MODE structure that describes the pinned mode.<br/>2. Setting ppPinnedVidPnTargetModeInfo to NULL to indicate that the target mode set has no pinned mode.|
|STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET|The handle supplied in hVidPnTargetModeSet was invalid.|


## -remarks



When you have finished using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a> structure, you must release the structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_releasemodeinfo">pfnReleaseModeInfo</a>.

The D3DKMDT_HVIDPNTARGETMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_pinmode">pfnPinMode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_releasemodeinfo">pfnReleaseModeInfo</a>
 

 

